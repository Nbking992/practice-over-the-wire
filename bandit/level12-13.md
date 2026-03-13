# 🟢 Bandit Level 12 → 13

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

El archivo `data.txt` contiene un **hexdump** de un archivo que ha sido comprimido varias veces utilizando diferentes formatos.

---

## 🔐 Credenciales

* Usuario: `bandit12`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El archivo `data.txt` no es directamente utilizable porque contiene un **hexdump**.

Primero debemos convertirlo nuevamente a un archivo binario y luego ir **descomprimiendo las diferentes capas**.

---

## 🧩 Solución

### 1️⃣ Conectarse

Es recomendable trabajar en `/tmp`:

```bash
bandit12@bandit:~$ mkdir /tmp/bandit12
bandit12@bandit:~$ cd /tmp/bandit12
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ cp ~/data.txt .

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ xxd -r data.txt data.bin
```
---

## Explicacion

* `xxd` → herramienta para crear o revertir hexdumps
* `-r` → revierte el hexdump

---

### 5️⃣ Identificar el tipo de archivo

```bash
file data.bin
```

Esto nos indicará el tipo de compresión.

---

### 6️⃣ Descomprimir las capas

Dependiendo del resultado de `file`, usamos diferentes herramientas:

Ejemplos:

```bash
mv data.bin data.gz
gunzip data.gz
```

```bash
mv data data.bz2
bunzip2 data.bz2
```

```bash
mv data data.tar
tar -xf data.tar
```

Repetimos el proceso:

1. identificar tipo de archivo (`file`)
2. renombrar si es necesario
3. descomprimir

---

### 7️⃣ Leer el archivo final

Al final obtendremos un archivo que contiene la contraseña.

```bash
cat data
```

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

---

## 🧠 Conceptos aprendidos

* Revertir hexdumps (`xxd -r`)
* Identificación de tipos de archivo (`file`)
* Manejo de compresiones (`gzip`, `bzip2`, `tar`)
* Análisis de archivos en múltiples capas

---

