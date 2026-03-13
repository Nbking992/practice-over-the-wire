# 🟢 Bandit Level 10 → 11

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

La contraseña almacenada en el archivo `data.txt` está **codificada en Base64**.

---

## 🔐 Credenciales

* Usuario: `bandit10`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El contenido del archivo `data.txt` no está en texto plano, sino **codificado usando Base64**.

Base64 es un método común para codificar datos binarios como texto.

---

## 🧩 Solución

### 1️⃣ Conectarse

```bash
bandit10@bandit:~$ base64 -d data.txt 
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
---

## 🔎 Explicación

* `base64` → herramienta para codificar o decodificar datos en Base64
* `-d` → indica que queremos **decodificar**

Este comando transforma el texto codificado en su forma original.

---

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## 📌 Conceptos aprendidos

* Codificación Base64
* Decodificación en Linux
* Uso del comando `base64`

---
