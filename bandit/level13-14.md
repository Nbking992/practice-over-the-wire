# 🟢 Bandit Level 13 → 14

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

En este nivel no usamos una contraseña directamente, sino una **clave privada SSH** para acceder al siguiente usuario.

---

## 🔐 Credenciales

* Usuario: `bandit13`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

## 🧩 Solución

```bash 
bandit13@bandit:~$ ls
HINT  sshkey.private
bandit13@bandit:~$ cat HINT 
If you have trouble with this level, note the following:

1) As for all other levels, this level has a website with information:
   https://overthewire.org/wargames/bandit/bandit14.html
2) No, the level is not broken. To verify, see:
   https://status.overthewire.org/
3) The current version of OverTheWire prevents logging in from one
   level to another via localhost. Log out, and see 1)
4) If you get errors, read the error message on your screen.
   We mean it!
bandit13@bandit:~$ exit
user@antix1:~/Desktop/practice-over-the-wire/bandit$ scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
user@antix1:~/Desktop/practice-over-the-wire/bandit$ chmod 600 sshkey.private
user@antix1:~/Desktop/practice-over-the-wire/bandit$ ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
bandit13@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

```

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

---

## 🧠 Explicación

* `ssh -i` permite autenticarse usando una clave privada
* `chmod 600` restringe permisos del archivo (requisito de SSH)

Este nivel enseña autenticación basada en claves.

---

## 📌 Conceptos aprendidos

* Autenticación SSH con claves
* Permisos de archivos (`chmod`)

