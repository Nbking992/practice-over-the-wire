# 🟢 Bandit Level 2 → 3

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

En este nivel el archivo que contiene la contraseña tiene **espacios en su nombre**:

```
--spaces in this filename--
```

---

## 🔐 Credenciales

* Usuario: `bandit2`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

Los espacios en nombres de archivos generan errores si no se manejan correctamente.

Si intentamos:

```bash
cat ./--spaces in this filename--
```

Linux interpreta cada palabra como un argumento separado.

---

## 🧩 Solución

### 1️⃣ Conectarse al servidor

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

---

### 2️⃣ Listar archivos

```bash
ls
```

Salida:

```
--spaces in this filename--
```

---

### 3️⃣ Leer el archivo correctamente

Hay dos formas correctas de hacerlo:

### ✅ Opción 1: Usar comillas

```bash
cat ./"--spaces in this filename--"
```

### ✅ Opción 2: Escapar espacios con `\`

```bash
cat ./spaces\ in\ this\ filename
```

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

---

## 🧠 Explicación

* Los espacios separan argumentos en la terminal.
* Las comillas (`" "`) indican que todo el texto es un solo argumento.
* El símbolo `\` se usa para escapar caracteres especiales.

Este nivel enseña cómo manejar nombres de archivos con espacios en Linux.

---

## 📌 Conceptos aprendidos

* Manejo de espacios en nombres de archivos
* Uso de comillas en la terminal
* Uso del carácter de escape (`\`)
