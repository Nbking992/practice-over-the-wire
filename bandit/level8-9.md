# 🟢 Bandit Level 8 → 9

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

La contraseña es **la única línea del archivo `data.txt` que aparece una sola vez**.

---

## 🔐 Credenciales

* Usuario: `bandit8`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El archivo `data.txt` contiene muchas líneas repetidas.
Solo **una línea aparece exactamente una vez**.

---

## 🧩 Solución

```bash
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

* `sort` → ordena el contenido del archivo
* `|` → pipe, pasa la salida al siguiente comando
* `uniq -u` → muestra solo las líneas únicas

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

---

## 🧠 Explicación

El comando `uniq` solo funciona correctamente cuando las líneas repetidas están juntas.
Por eso es necesario usar primero `sort`.

Este pipeline permite encontrar la única línea que no se repite.

---

## 📌 Conceptos aprendidos

* `sort`
* `uniq`
* pipelines (`|`)
* análisis de texto en Linux

---

---
