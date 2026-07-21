# Capítulo 2: Permisos, chmod, chown y por qué Linux te pide contraseña

> En el capítulo 1 aprendiste a moverte y manipular archivos. Ahora toca la pregunta que asusta a todo principiante: ¿por qué a veces Linux se niega a hacer lo que le pides? La respuesta casi siempre es permisos, no un error del sistema.

Cada archivo y carpeta en Linux tiene un dueño y una regla de acceso. No es una restricción arbitraria: es el mecanismo que evita que un programa cualquiera lea tu historial de navegador o que un usuario borre archivos de otro. Entender esto elimina la mitad de los mensajes de "Permission denied" que verás en tu vida con Linux.

```bash

ls -l
# -rwxr-xr-- 1 ana ana 220 ene 20 10:02 script.sh

```

```bash

-  rwx  r-x  r--
│   │    │    │
│   │    │    └── otros
│   │    └─────── grupo
│   └──────────── dueño
└──────────────── tipo: "-" archivo, "d" carpeta, "l" enlace simbólico

```

`r`, `w`, `x` significan algo distinto en carpetas:

| Comando | Qué hace |
|---|---|
| `pwd` | dónde estoy |
| `ls` | qué hay aquí |
| `cd` | moverme |
| `mkdir` | crear carpeta |
| `touch` | crear archivo vacío |
| `cat` | ver contenido de archivo |
| `cp` | copiar |
| `mv` | mover / renombrar |
| `rm` ⚠️ | eliminar (sin papelera) |
| `man` | manual de cada comando |
