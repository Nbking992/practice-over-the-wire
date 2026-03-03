# 🟢 Bandit Level 5 → 6

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

Dentro del directorio `inhere` hay muchos subdirectorios y archivos.
El archivo correcto cumple con estas condiciones:

* Tiene **1033 bytes**
* Es **legible por humanos**
* No es ejecutable

---

## 🔐 Credenciales

* Usuario: `bandit5`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El directorio `inhere` contiene múltiples subdirectorios con muchos archivos.

Buscar manualmente no es eficiente.

---

## 🧩 Solución

```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls -lA
total 80
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere00
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere01
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere02
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere03
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere04
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere05
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere06
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere07
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere08
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere09
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere10
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere11
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere12
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere13
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere14
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere15
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere16
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere17
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere18
drwxr-x--- 2 root bandit5 4096 Oct 14 09:26 maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ file ./maybehere07/.file2 
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2 
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

###  Buscar el archivo correcto

Usamos `find` con las condiciones necesarias:

```bash
find . -type f -size 1033c ! -executable
```

Explicación del comando:

* `.` → buscar desde el directorio actual
* `-type f` → solo archivos
* `-size 1033c` → tamaño exacto en bytes
* `! -executable` → excluir archivos ejecutables

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

---

## 🧠 Explicación

El comando `find` permite buscar archivos según múltiples criterios.

Este nivel enseña:

* Uso avanzado de `find`
* Búsqueda por tamaño
* Filtrado por permisos

---

## 📌 Conceptos aprendidos

* `find`
* Filtros por tamaño
* Exclusión con `!`
* Búsqueda recursiva

---
