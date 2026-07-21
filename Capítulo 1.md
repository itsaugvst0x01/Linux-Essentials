# Linux desde 0
## Capítulo 1: Los 10 comandos que necesitas para dejar de temerle a la terminal

> Si nunca has abierto una terminal, esto es para ti. No vamos a memorizar 100 comandos. Vamos a entender 10, bien, para que la próxima vez que veas una pantalla negra con texto no sientas que vas a romper la computadora.

La terminal no es magia ni hackeo de película. Es una conversación con el sistema operativo, en texto plano en lugar de clics. Cada comando es una instrucción corta que el shell (el programa que interpreta lo que escribes) traduce en una acción real sobre archivos, carpetas o procesos.

Regla de oro antes de empezar: **ningún comando de esta lista borra nada de forma irreversible si sigues los ejemplos tal cual**. Los que sí pueden borrar algo están marcados con ⚠️ y se explica por qué.

---

### 1. `pwd` — ¿dónde estoy?
**Print Working Directory.** Imprime la ruta completa de la carpeta en la que estás parado ahora mismo.

```bash
pwd
# /home/tu_usuario
```

Analogía: es como preguntar "¿en qué pasillo del supermercado estoy?" antes de empezar a caminar. Úsalo cada vez que te sientas perdido dentro del sistema de archivos.

---

### 2. `ls` — ¿qué hay aquí?
**List.** Muestra el contenido de la carpeta actual.

```bash
ls        # lista simple
ls -l     # lista detallada: permisos, tamaño, fecha
ls -a     # incluye archivos ocultos (los que empiezan con punto)
ls -la    # la combinación que más se usa en el día a día
```

Analogía: es abrir el cajón y ver qué hay adentro antes de meter la mano.

---

### 3. `cd` — muévete entre carpetas
**Change Directory.** Te lleva de una carpeta a otra.

```bash
cd Documentos     # entra a la carpeta Documentos
cd ..              # sube un nivel (a la carpeta padre)
cd ~               # te lleva directo a tu carpeta personal (home)
cd /               # te lleva a la raíz de todo el sistema
cd -               # regresa a la carpeta anterior donde estabas
```

Tres símbolos que vas a usar constantemente: `.` es la carpeta actual, `..` es la carpeta de arriba, `~` es tu home. Si te pierdes, `cd` sin nada más siempre te devuelve a casa.

---

### 4. `mkdir` — crea una carpeta
**Make Directory.**

```bash
mkdir proyectos
mkdir -p proyectos/2026/enero   # crea las 3 carpetas anidadas de una vez
```

La bandera `-p` es la que te ahorra escribir `cd` y `mkdir` tres veces seguidas.

---

### 5. `touch` — crea un archivo vacío
```bash
touch notas.txt
touch a.txt b.txt c.txt   # varios de una vez
```

Sirve para probar comandos sin arriesgar un archivo real, y para inicializar archivos vacíos que luego edita otro programa.

---

### 6. `cat` — muestra el contenido de un archivo
**Concatenate.**

```bash
cat notas.txt
```

Imprime el archivo completo en pantalla. Útil para archivos cortos; para archivos largos existe `less archivo.txt` (se navega con flechas, se sale con `q`).

---

### 7. `cp` — copiar
**Copy.**

```bash
cp original.txt copia.txt        # copia un archivo
cp -r carpeta_origen/ destino/   # -r = recursivo, necesario para carpetas
```

Sin `-r`, `cp` se niega a copiar una carpeta completa. Es una protección, no un error.

---

### 8. `mv` — mover o renombrar
**Move.** Linux no tiene un comando "rename" separado: `mv` cumple las dos funciones según cómo lo uses.

```bash
mv archivo.txt otra_carpeta/     # mover
mv nombre_viejo.txt nombre_nuevo.txt   # renombrar
```

---

### 9. `rm` — eliminar ⚠️
**Remove.** Este es el único de la lista que requiere respeto real.

```bash
rm archivo.txt        # borra un archivo
rm -r carpeta/         # borra una carpeta y todo su contenido
```

**Por qué el cuidado:** a diferencia de borrar en un explorador gráfico, `rm` no manda nada a una papelera de reciclaje. Es un borrado directo. No hay "deshacer". La práctica más segura al empezar: usa `ls` primero para confirmar exactamente qué hay en esa carpeta, y nunca combines `rm -r` con rutas que no verificaste con `pwd`.

---

### 10. `man` — el manual integrado
**Manual.** Si olvidas qué hace un comando o qué opciones acepta, no busques en Google primero: pregúntale al sistema.

```bash
man ls
# se navega con flechas, se sale con "q"
```

Todo comando de Linux documenta sus propias opciones ahí. Es la fuente más confiable porque describe exactamente la versión instalada en tu máquina, no una genérica de internet.

---

## Resumen rápido (para guardar)

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

---

## Próximo capítulo
**Capítulo 2:** permisos de archivos (`chmod`, `chown`) y por qué Linux te pide contraseña para algunas cosas — el concepto de usuario root explicado sin miedo.

---

**Fuentes consultadas:** GNU Coreutils Manual (gnu.org/software/coreutils), documentación de manual pages estándar de Unix/Linux, Iowa State University Research IT — Linux Basic Commands and Concepts.
