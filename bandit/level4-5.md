# 🟢 Bandit Level 4 → 5

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

Dentro del directorio `inhere` hay varios archivos.
Solo **uno** contiene texto legible por humanos.

---

## 🔐 Credenciales

* Usuario: `bandit4`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

Dentro del directorio hay múltiples archivos con nombres como:

```bash
-file00
-file01
-file02
...
```

---

## 🧩 Solución

```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls -lA
total 40
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file00
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file01
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file02
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file03
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file04
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file05
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file06
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file07
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file08
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: OpenPGP Public Key
./-file02: OpenPGP Public Key
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

---

###  Identificar el archivo legible

Usamos el comando `file` para analizar el tipo de cada archivo:

```bash
file ./*
```

El archivo que dice `ASCII text` es el que contiene texto legible.

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

---

## 🧠 Explicación

* `file` identifica el tipo de contenido de un archivo.
* `./*` indica todos los archivos del directorio actual.
* `ASCII text` indica que el archivo contiene texto plano.

Este nivel enseña cómo identificar tipos de archivos en Linux.

---

## 📌 Conceptos aprendidos

* Uso del comando `file`
* Identificación de archivos binarios vs texto
* Uso de comodines (`*`)

