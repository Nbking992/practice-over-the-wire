# 🟢 Bandit Level 1 → 2

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

En este nivel el archivo que contiene la contraseña tiene un nombre especial: `-`

---

## 🔐 Credenciales

* Usuario: `bandit1`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El archivo se llama `-`.

En Linux, el símbolo `-` normalmente representa **stdin (entrada estándar)**, por lo que usar simplemente:

```bash
cat -
```

no funciona como se espera.

---

## 🧩 Solución

###  Leer el archivo correctamente

Para indicarle a `cat` que `-` es un archivo y no stdin, se usa `./`:

```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

## 🧠 Explicación

* `-` puede representar stdin en muchos comandos.
* `./-` indica explícitamente que estamos accediendo a un archivo en el directorio actual.
* `./` significa "directorio actual".

Este nivel enseña cómo manejar nombres de archivos especiales en Linux.

---

## 📌 Conceptos aprendidos

* Manejo de archivos con nombres especiales
* Diferencia entre argumentos y stdin
* Uso correcto de rutas relativas (`./`)
