# 🟢 Bandit Level 14 → 15

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

La contraseña debe enviarse a un servicio que escucha en el **puerto 30000** en `localhost`.

---

## 🔐 Credenciales

* Usuario: `bandit14`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🧩 Solución

```bash 
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
bandit14@bandit:~$ ls
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

---

### Tip: Tambien se puede lograr de esta manera

Usamos `nc` (netcat):

```bash 
echo "<password>" | nc localhost 30000
```

---

## 🔑 Resultado

El servidor responde con la contraseña del siguiente nivel:

```bash
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

---

## 🧠 Explicación

* `nc` (netcat) permite conectarse a puertos TCP/UDP
* `echo` envía la contraseña como input
* `|` pasa el input a `nc`
* `localhost 30000` indica que el servicio está en el mismo servidor

Este nivel introduce interacción con servicios de red.

---

## 📌 Conceptos aprendidos

* Uso de `nc` (netcat)
* Comunicación con servicios TCP
* Pipes (`|`) para enviar datos
