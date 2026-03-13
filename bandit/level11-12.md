# 🟢 Bandit Level 11 → 12

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

El contenido del archivo `data.txt` ha sido codificado usando **ROT13**.

---

## 🔐 Credenciales

* Usuario: `bandit11`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El texto del archivo está transformado usando **ROT13**, un cifrado simple que rota cada letra **13 posiciones en el alfabeto**.

Ejemplo:

```bash
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
```

---

## 🧩 Solución

```bash 
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

```

---

## 🔎 Explicación del comando

```bash id="hjzwgs"
tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

* `tr` → traduce o reemplaza caracteres
* `'A-Za-z'` → rango completo de letras
* `'N-ZA-Mn-za-m'` → rotación ROT13

Esto rota cada letra **13 posiciones**, revirtiendo la codificación.

---

## 📌 Conceptos aprendidos

* Cifrado ROT13
* Uso del comando `tr`
* Transformación de texto en Linux

---

## 🚀 Siguiente nivel

👉 [Level 12 → 13](./level12-13.md)

---
