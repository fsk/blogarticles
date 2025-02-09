---
title: Java ile IP İşlemleri
tags: kendime, java, ip
date: 2024-03-21
---

## Java İle IP Bulmak

Javada 2 farklı IP adresi bulunabiliyor. `InetAddress class` ve `NetworkInterface` class. Ama NetworkInterface class
`Enumeration` kullandığı için onu burada es geçeceğim.

```java
try {
    InetAddress address = InetAddress.getLocalHost();
    System.out.println("Get Host Address ==> " + address.getHostAddress());
    System.out.println("Get Host Name ==> " + address.getHostName());
} catch (UnknownHostException e) {
    throw new RuntimeException(e);
}
```


```java
try {
    Enumeration<NetworkInterface> interfaces = NetworkInterface.getNetworkInterfaces();
    while (interfaces.hasMoreElements()) {
        NetworkInterface networkInterface = interfaces.nextElement();
        Enumeration<InetAddress> addresses = networkInterface.getInetAddresses();
        while (addresses.hasMoreElements()) {
            InetAddress inetAddress = addresses.nextElement();
            if (!inetAddress.isLoopbackAddress() && inetAddress instanceof Inet4Address) {
                System.out.println("Network Interface: " + networkInterface.getDisplayName() + " -> IP: " + inetAddress.getHostAddress());
            }
        }
    }
} catch (SocketException e) {
    throw new RuntimeException(e);
}

```


