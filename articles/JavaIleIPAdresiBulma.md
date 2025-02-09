---
title: Node.js ile Express Uygulaması Geliştirme
date: 2024-03-21
tags: nodejs, express, javascript, web development
---

# Node.js ile Express Uygulaması Geliştirme

## Giriş

Bu yazıda, Node.js ve Express.js kullanarak basit bir web uygulaması nasıl geliştirilir onu anlatacağım. Express.js, Node.js için geliştirilmiş hızlı ve minimalist bir web framework'üdür.

## Gereksinimler

- Node.js (v14 veya üzeri)
- npm (Node Package Manager)
- Temel JavaScript bilgisi

## Kurulum

İlk olarak yeni bir proje oluşturalım:

```javascript
const veriGetir = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const veri = {
                id: 1,
                isim: "Örnek Veri"
            };
            resolve(veri);
        }, 2000);
    });
};
```