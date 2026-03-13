# 🟢 Bandit Level 7 → 8

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

La contraseña está dentro del archivo `data.txt`, junto a la palabra:

```text
millionth
```

---

## 🔐 Credenciales

* Usuario: `bandit7`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El archivo `data.txt` es muy grande, buscar manualmente no es práctico.
A su vez, el archivo contiene letras y consecuentemente posibles contraseñas

```bash 
bandit7@bandit:~$ cat data.txt
manliest	K2CvwUc9YN7xieipCeX5jMKQcMBS8Vws
handcarts	3ljyY4JOZtPsFiDzyd4xmiAeB6VODvZi
proportion	k3zSwB18U81PxyyfoC1vlV8dxiIJvksT
axon's	TNG94b4tUn82OCjsZB2lXSKP0KrrY6Lj
woulds	yyUKnaCW0nB8Yb4mkwyPm8hjuBi9P6Gv
visceral	7qSF6rOuaye4FoVtjg1QCGmfpBsrAqgN
supremacist's	PYFYkdy65DvevcUJabb1TGmDEtfm1Gc8

```
---

## 🧩 Solución

```bash
bandit7@bandit:~$ grep 'millionth' data.txt 
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

## 🧠 Explicación

* `grep` busca patrones de texto dentro de archivos.
* Al buscar `"millionth"` obtenemos directamente la línea que contiene la contraseña.

---

## 📌 Conceptos aprendidos

* Búsqueda eficiente en archivos grandes
* Uso básico de `grep`

---


---
