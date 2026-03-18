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

Es recomendable trabajar en `/tmp` o descargar el archivo con `scp`:

### Metodo SCP
```bash
user@antix1:~/Desktop/practice-over-the-wire/bandit$ scp -P 2220 bandit12@bandit.labs.overthewire.org:/home/bandit12/data.txt .
```

### Metodo carpeta tmp
```bash
bandit12@bandit:~$ mkdir /tmp/bandit12
bandit12@bandit:~$ cd /tmp/bandit12
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ cp ~/data.txt .
```

### Para esta prueba se uso el segundo:

```bash
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ xxd -r data.txt > data.hexdump
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file data.gz 
data.gzip: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 564

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ xxd -r data.txt > data.gz
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ gzip -d gzip.gz
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file gzip 
gzip: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv gzip bzip2.bz2
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ bzip2 -d bzip2.bz2
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file bzip2 
bzip2: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 20480

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv bzip2 gzip.gz
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file gzip 
gzip: POSIX tar archive (GNU)

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv gzip tar.tar
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ tar -xf tar.tar
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file data5.bin 
data5.bin: POSIX tar archive (GNU)

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv data5.bin tarbin.tar
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ tar -xf tarbin.tar 
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv data6.bin bzip2.bz2
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ bzip2 -d bzip2.bz2
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file bzip2 
bzip2: POSIX tar archive (GNU)

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv bzip2 tar.tar
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ tar -xf tar.tar
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 49

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ mv data8.bin gzip.gz
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ gzip -d gzip.gz
bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ file gzip 
gzip: ASCII text

bandit12@bandit:/tmp/tmp.3rsCFnqtOS$ cat gzip 
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
---

## Explicacion

* `xxd` → herramienta para crear o revertir hexdumps
* `-r` → revierte el hexdump
* `gzip, bzip2, tar` → herramientas para comprimir, descomprimir, etc archivos
* `-d` → descomprimir

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

