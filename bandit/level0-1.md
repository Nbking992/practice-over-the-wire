# 🟢 Bandit Level 0 → 1

## 🎯 Objetivo

El objetivo de este nivel es conectarse al servidor usando SSH y encontrar la contraseña para el siguiente nivel.

---

## 🔐 Credenciales

* Usuario: `bandit0`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`
* Password: `bandit0`

---

## 🛠️ Solución

### 1. Conectarse por SSH

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

---

### 2. Listar archivos

```bash
ls
```

Salida:

```bash
readme
```

---

### 3. Leer el archivo

```bash
cat readme
```

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
<password>
```

---

## 🧠 Explicación

* `ssh`: se utiliza para conectarse a un servidor remoto
* `ls`: lista los archivos en el directorio actual
* `cat`: muestra el contenido de un archivo

En este nivel se aprende lo básico de navegación en Linux y conexión remota.

---

## 📌 Notas

* Este es el nivel introductorio
* No requiere conocimientos avanzados

