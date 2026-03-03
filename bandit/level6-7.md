# 🟢 Bandit Level 6 → 7

## 🎯 Objetivo

Encontrar la contraseña para el siguiente nivel.

El archivo correcto cumple estas condiciones:

* Es propiedad del usuario **bandit7**
* Pertenece al grupo **bandit6**
* Tiene tamaño **33 bytes**

La búsqueda debe hacerse en todo el sistema.

---

## 🔐 Credenciales

* Usuario: `bandit6`
* Host: `bandit.labs.overthewire.org`
* Puerto: `2220`

---

## 🛠️ Problema

El archivo no está en el directorio actual.
Debe buscarse en todo el sistema de archivos.

Además, muchos directorios generan errores de permisos.

---

## 🧩 Solución

```bash id="k0q1rm"
bandit6@bandit:~$ ls
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

###  Buscar el archivo en todo el sistema

```bash 
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
find / -type f -user bandit7 -group bandit6 -size 33c  -exec cat {} + 2>/dev/null
```

---

## 🔎 Explicación del comando

* `/` → buscar desde la raíz del sistema
* `-type f` → solo archivos
* `-user bandit7` → propiedad del usuario bandit7
* `-group bandit6` → grupo bandit6
* `-size 33c` → tamaño exacto en bytes
* `2>/dev/null` → ocultar errores de permisos
* `-exec cat {}` → ejectuar `cat` y leer las salidas del find

---

## 🔑 Resultado

La contraseña para el siguiente nivel es:

```bash id="v8p3rn"
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

## 🧠 Conceptos aprendidos

* Búsqueda global con `find`
* Filtrado por usuario y grupo
* Redirección de errores (`2>/dev/null`)
* Manejo de permisos en Linux
* Tip aprendido, ejecutar comandos dentro de `find`.

---

