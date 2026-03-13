# 🟢 Bandit Level 9 → 10

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

La contraseña está dentro del archivo `data.txt`, escondida entre datos binarios y **precedida por varios caracteres `=`**.

---

## 🔐 Credenciales

* Usuario: `bandit9`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El archivo `data.txt` contiene principalmente **datos binarios**, por lo que abrirlo directamente con `cat` no muestra información útil.

---

## 🧩 Solucion

```bash
bandit9@bandit:~$ strings data.txt | grep '==='
========== the
========== password
f\Z'========== is
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

## 🔎 Explicación

* `strings` → extrae texto legible de archivos binarios
* `|` → pipe para pasar el resultado
* `grep "==="` → busca líneas que contengan `=`

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

---

## 🧠 Conceptos aprendidos

* Análisis de archivos binarios
* Uso de `strings`
* Filtrado con `grep`
* pipelines en Linux

---
