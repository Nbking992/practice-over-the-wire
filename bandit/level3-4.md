# 🟢 Bandit Level 3 → 4

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

En este nivel la contraseña se encuentra dentro de un **archivo oculto** en el directorio `inhere`.

---

## 🔐 Credenciales

* Usuario: `bandit3`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

Al listar los archivos normalmente:

```bash
ls
```

Solo vemos:

```bash
inhere
```

Pero dentro de `inhere` aparentemente no hay nada visible:

```bash
cd inhere
ls
```

No muestra archivos.

---

## 🧩 Solución

###  Mostrar archivos ocultos
```bash
ls -a
ls -A
```

Las diferencia con a y A es que no muestran los `.` y `..`

Salida:

```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct 14 09:26 .
drwxr-xr-x 3 root    root    4096 Oct 14 09:26 ..
-rw-r----- 1 bandit4 bandit3   33 Oct 14 09:26 ...Hiding-From-You
bandit3@bandit:~/inhere$ ls -lA
total 4
-rw-r----- 1 bandit4 bandit3 33 Oct 14 09:26 ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You 
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

---

## 🧠 Explicación

* Los archivos que comienzan con `.` son **archivos ocultos** en Linux.
* El comando `ls -a` muestra todos los archivos, incluidos los ocultos.
* `.` representa el directorio actual.
* `..` representa el directorio anterior.

Este nivel enseña cómo trabajar con archivos ocultos en Linux.

---

## 📌 Conceptos aprendidos

* Uso de `ls -a`
* Archivos ocultos en Linux
* Navegación entre directorios
