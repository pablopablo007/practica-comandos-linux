# Práctica No. 1 - Comandos de Linux: Creación y Manipulación de Archivos

## 1. Título
**Práctica No. 1:** Creación y Manipulación de Archivos en Linux usando Ubuntu WSL

---

## 2. Tiempo de Duración
Aproximadamente **45 minutos** para desarrollar la práctica completa, incluyendo la comprensión de cada comando y la verificación de resultados.

---

## 3. Fundamentos

Linux es un sistema operativo de código abierto basado en el núcleo (*kernel*) desarrollado por Linus Torvalds en 1991. Es ampliamente utilizado en servidores, sistemas embebidos, supercomputadoras y entornos de desarrollo de software empresarial y académico. Una de sus principales fortalezas radica en su potente interfaz de línea de comandos (CLI - *Command Line Interface*), la cual permite al usuario interactuar directamente con el sistema operativo mediante instrucciones de texto precisas y automatizables.

### Comandos Fundamentales de Linux

#### Gestión de Directorios
- **mkdir** (*Make Directory*): Permite crear uno o varios directorios. La opción -p es esencial para crear rutas completas con directorios anidados sin arrojar errores si las carpetas intermedias no existen.
`ash
mkdir -p proyecto_comandos/documentos proyecto_comandos/imagenes proyecto_comandos/scripts
`

- **ls** (*List*): Muestra los archivos y directorios contenidos en una ruta. Con los parámetros -la proporciona información detallada en formato de lista (permisos de lectura, escritura y ejecución, número de enlaces, usuario propietario, grupo, tamaño en bytes y fecha/hora de modificación), incluyendo archivos ocultos.
`ash
ls -la proyecto_comandos/
`

- **cd** (*Change Directory*): Navega entre directorios del árbol jerárquico.
- **
mdir** (*Remove Directory*): Elimina directorios que se encuentren completamente vacíos, ofreciendo una capa de seguridad para evitar borrados accidentales de información.
`ash
rmdir proyecto_comandos/imagenes
`

#### Gestión y Manipulación de Archivos
- **	ouch**: Crea archivos vacíos en el sistema de archivos o actualiza las marcas temporales de acceso y modificación de archivos preexistentes.
`ash
touch proyecto_comandos/documentos/resumen.txt
`

- **cp** (*Copy*): Realiza duplicados de archivos o estructuras de directorios hacia otra ubicación.
`ash
cp proyecto_comandos/documentos/notas.txt proyecto_comandos/scripts/backup_notas.txt
`

- **mv** (*Move*): Mueve archivos o directorios de una ruta a otra, y se utiliza comúnmente para renombrar elementos.
`ash
mv proyecto_comandos/scripts/backup_notas.txt proyecto_comandos/imagenes/backup_notas.txt
`

- **
m** (*Remove*): Elimina permanentemente archivos del sistema de archivos.
`ash
rm proyecto_comandos/imagenes/backup_notas.txt
`

- **cat** (*Concatenate*): Lee y concatena archivos de texto, mostrando su contenido en la salida estándar de la consola.
`ash
cat proyecto_comandos/documentos/notas.txt
`

#### Redirección de Entrada/Salida y Tuberías
- **Operador >** (Redirección simple de salida): Redirige la salida estándar de un comando a un archivo, sobreescribiendo completamente su contenido si el archivo ya existía.
- **Operador >>** (Redirección acumulativa): Agrega la salida de un comando al final del archivo destino sin alterar los datos preexistentes.
- **Operador |** (*Pipe* o Tubería): Conecta directamente la salida estándar (*stdout*) de un comando con la entrada estándar (*stdin*) de otro, permitiendo encadenar operaciones complejas de filtrado y procesamiento en una sola línea de ejecución.
`ash
history | tail -50 > tarea-s1-pablo_mora.txt
`

---

## 4. Conocimientos Previos

Para realizar esta práctica el estudiante necesita tener claro los siguientes temas:
- Conceptos fundamentales de sistemas operativos (procesos, hilos, archivos y directorios).
- Diferencia entre entornos de interfaz gráfica de usuario (GUI) e interfaces de consola por línea de comandos (CLI).
- Jerarquía y organización del sistema de archivos tipo Unix (raíz /, directorio personal ~, rutas absolutas y relativas).
- Manejo básico de terminales y emuladores (WSL, Git Bash o consolas nativas de Linux).
- Funcionamiento de flujos estándar: stdin (0), stdout (1) y stderr (2).

---

## 5. Objetivos a Alcanzar

- Diseñar y construir una jerarquía estructurada de carpetas mediante el comando mkdir -p.
- Crear, editar y concatenar archivos de texto empleando echo, 	ouch y operadores de redirección.
- Ejecutar operaciones de copia (cp) y traslado/renombrado (mv) de archivos entre subdirectorios.
- Utilizar de manera segura los comandos de eliminación 
m y 
mdir.
- Aplicar tuberías (|) para canalizar y almacenar el historial de comandos ejecutados en la sesión.

---

## 6. Equipo Necesario

- Computador con sistema operativo **Windows 10/11** con subsistema WSL2 habilitado.
- Distribución **Ubuntu Linux** en WSL.
- Herramienta de control de versiones **Git** instalada y configurada.
- Cuenta en **GitHub** para publicación y entrega del repositorio.

---

## 7. Actividades Desarrolladas

### Paso 1: Creación de la Estructura de Carpetas

Se creó la carpeta raíz del proyecto proyecto_comandos junto a las subcarpetas documentos, imagenes y scripts en una única instrucción:

`ash
cd ~
mkdir -p proyecto_comandos/documentos proyecto_comandos/imagenes proyecto_comandos/scripts
ls -la proyecto_comandos/
`

**Salida en consola:**
`	ext
total 20
drwxr-xr-x  5 pablo pablo 4096 Oct 14 07:19 .
drwxr-x--- 11 pablo pablo 4096 Oct 14 07:19 ..
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 documentos
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 imagenes
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 scripts
`

---

### Paso 2: Creación y Edición de 
otas.txt

Se generó el archivo 
otas.txt dentro de documentos agregando tres líneas mediante redirección:

`ash
echo 'Linea 1: Los comandos de Linux permiten gestionar el sistema de manera eficiente.' > proyecto_comandos/documentos/notas.txt
echo 'Linea 2: El comando mkdir crea directorios, y con -p crea subdirectorios anidados.' >> proyecto_comandos/documentos/notas.txt
echo 'Linea 3: El comando echo redirige texto a archivos usando > (sobreescribir) o >> (agregar).' >> proyecto_comandos/documentos/notas.txt
cat proyecto_comandos/documentos/notas.txt
`

**Salida en consola:**
`	ext
Linea 1: Los comandos de Linux permiten gestionar el sistema de manera eficiente.
Linea 2: El comando mkdir crea directorios, y con -p crea subdirectorios anidados.
Linea 3: El comando echo redirige texto a archivos usando > (sobreescribir) o >> (agregar).
`

---

### Paso 3: Copia de Archivo (cp)

Se copió el archivo 
otas.txt hacia scripts con el nuevo nombre ackup_notas.txt:

`ash
cp proyecto_comandos/documentos/notas.txt proyecto_comandos/scripts/backup_notas.txt
ls -la proyecto_comandos/scripts/
`

**Salida en consola:**
`	ext
total 12
drwxr-xr-x 2 pablo pablo 4096 Oct 14 07:19 .
drwxr-xr-x 5 pablo pablo 4096 Oct 14 07:19 ..
-rw-r--r-- 1 pablo pablo  257 Oct 14 07:19 backup_notas.txt
`

---

### Paso 4: Movimiento de Archivo (mv)

Se trasladó ackup_notas.txt desde scripts a la carpeta imagenes:

`ash
mv proyecto_comandos/scripts/backup_notas.txt proyecto_comandos/imagenes/backup_notas.txt
ls -la proyecto_comandos/imagenes/
`

**Salida en consola:**
`	ext
total 12
drwxr-xr-x 2 pablo pablo 4096 Oct 14 07:19 .
drwxr-xr-x 5 pablo pablo 4096 Oct 14 07:19 ..
-rw-r--r-- 1 pablo pablo  257 Oct 14 07:19 backup_notas.txt
`

---

### Paso 5: Redirección y Concatenación (
esumen.txt)

Se creó 
esumen.txt, se redireccionó el contenido de 
otas.txt y se añadió una cuarta línea sin sobreescribir:

`ash
touch proyecto_comandos/documentos/resumen.txt
cat proyecto_comandos/documentos/notas.txt > proyecto_comandos/documentos/resumen.txt
echo 'Linea 4: La redireccion de contenido es una herramienta poderosa en Linux.' >> proyecto_comandos/documentos/resumen.txt
cat proyecto_comandos/documentos/resumen.txt
`

**Salida en consola:**
`	ext
Linea 1: Los comandos de Linux permiten gestionar el sistema de manera eficiente.
Linea 2: El comando mkdir crea directorios, y con -p crea subdirectorios anidados.
Linea 3: El comando echo redirige texto a archivos usando > (sobreescribir) o >> (agregar).
Linea 4: La redireccion de contenido es una herramienta poderosa en Linux.
`

---

### Paso 6: Eliminación de Archivo (
m)

Se eliminó el archivo ackup_notas.txt de la carpeta imagenes:

`ash
rm proyecto_comandos/imagenes/backup_notas.txt
ls -la proyecto_comandos/imagenes/
`

**Salida en consola:**
`	ext
total 8
drwxr-xr-x 2 pablo pablo 4096 Oct 14 07:19 .
drwxr-xr-x 5 pablo pablo 4096 Oct 14 07:19 ..
`

---

### Paso 7: Eliminación de Carpeta Vacía (
mdir)

Se eliminó la carpeta imagenes aprovechando que se encontraba vacía:

`ash
rmdir proyecto_comandos/imagenes
ls -la proyecto_comandos/
`

**Salida en consola:**
`	ext
total 16
drwxr-xr-x  4 pablo pablo 4096 Oct 14 07:19 .
drwxr-x--- 11 pablo pablo 4096 Oct 14 07:19 ..
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 documentos
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 scripts
`

---

### Paso 8: Volcado del Historial de Comandos

Se utilizó el comando history en combinación con la tubería (|) y 	ail para exportar los comandos al archivo de entrega:

`ash
history | tail -50 > ~/proyecto_comandos/tarea-s1-pablo_mora.txt
`

---

## 8. Resultados Esperados

| Actividad | Comando Principal | Resultado Obtenido |
| :--- | :--- | :--- |
| Crear estructura de carpetas | mkdir -p | 3 subcarpetas creadas exitosamente |
| Crear archivo con texto | echo > y echo >> | 
otas.txt generado con 3 líneas |
| Copiar archivo | cp | ackup_notas.txt creado en scripts/ |
| Mover archivo | mv | ackup_notas.txt reubicado en imagenes/ |
| Redirección y concatenación | cat > y echo >> | 
esumen.txt con 4 líneas completas |
| Eliminar archivo | 
m | ackup_notas.txt suprimido de imagenes/ |
| Eliminar carpeta vacía | 
mdir | Carpeta imagenes/ eliminada limpiamente |
| Volcar historial | history | tail -50 > | Archivo 	area-s1-pablo_mora.txt generado |

---

## 9. Conclusiones

- Los comandos básicos del sistema de archivos (mkdir, cp, mv, 
m y 
mdir) constituyen el núcleo esencial para administrar de manera ágil cualquier entorno Linux.
- La distinción entre los operadores de redirección > (sobrescritura) y >> (adición) es crítica para evitar la pérdida no intencionada de información en archivos de configuración y datos.
- El uso de tuberías (|) es una de las mayores ventajas de los sistemas Unix, ya que permite encadenar comandos sencillos para resolver tareas complejas sin crear archivos temporales innecesarios.
- El subsistema WSL2 ofrece un entorno nativo y confiable de Linux directamente en Windows, facilitando la ejecución de prácticas y flujos de desarrollo modernos.

---

## 10. Bibliografía

- The Linux Documentation Project. (2023). *GNU/Linux Command-Line Tools Summary*. https://tldp.org/
- Canonical Ltd. (2024). *Ubuntu WSL Documentation*. https://ubuntu.com/wsl
- GNU Project. (2024). *GNU Coreutils Manual*. https://www.gnu.org/software/coreutils/manual/
- Microsoft. (2024). *Windows Subsystem for Linux Documentation*. https://learn.microsoft.com/en-us/windows/wsl/
- Ramey, C., & Fox, B. (2024). *Bash Reference Manual*. https://www.gnu.org/software/bash/manual/

---

*Informe elaborado por: **Pablo Mora***  
*Asignatura: Tendencias en Tecnología*  
*Fecha: Octubre 2026*
