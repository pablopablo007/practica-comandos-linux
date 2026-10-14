# Práctica No. 1 - Comandos de Linux: Creación y Manipulación de Archivos

## 1. Título

**Práctica No. 1:** Creación y Manipulación de Archivos en Linux usando Ubuntu WSL

---

## 2. Tiempo de Duración

Aproximadamente **45 minutos** para desarrollar la práctica completa, incluyendo la comprensión de cada comando y la verificación de resultados.

---

## 3. Fundamentos

Linux es un sistema operativo de código abierto basado en el núcleo (kernel) desarrollado por Linus Torvalds en 1991. Es ampliamente utilizado en servidores, sistemas embebidos, supercomputadoras y entornos de desarrollo de software. Una de sus principales características es la potente interfaz de línea de comandos (CLI - Command Line Interface), que permite al usuario interactuar directamente con el sistema operativo mediante comandos de texto.

### Comandos Fundamentales de Linux

#### Gestión de Directorios

- **mkdir** (Make Directory): Crea nuevos directorios. La opción -p permite crear directorios anidados en un solo comando.

\\ash
mkdir -p proyecto_comandos/documentos proyecto_comandos/imagenes proyecto_comandos/scripts
\
- **ls**: Lista el contenido de un directorio. La opción -la muestra todos los archivos (incluyendo ocultos) en formato largo con permisos, propietario, tamaño y fecha.

\\ash
ls -la proyecto_comandos/
\
- **cd** (Change Directory): Cambia el directorio de trabajo actual.

- **rmdir**: Elimina directorios vacíos.

\\ash
rmdir proyecto_comandos/imagenes
\
#### Gestión de Archivos

- **touch**: Crea un archivo vacío o actualiza la marca de tiempo de un archivo existente.

- **cp** (Copy): Copia archivos o directorios de una ubicación a otra.

\\ash
cp documentos/notas.txt scripts/backup_notas.txt
\
- **mv** (Move): Mueve o renombra archivos y directorios.

\\ash
mv scripts/backup_notas.txt imagenes/backup_notas.txt
\
- **rm** (Remove): Elimina archivos o directorios.

- **cat** (Concatenate): Muestra el contenido de uno o más archivos.

#### Redirección de Entrada/Salida

- **>** : Envía la salida de un comando a un archivo, sobreescribiendo su contenido.
- **>>** : Agrega la salida de un comando al final de un archivo sin sobreescribir.
- **|** (Tubería/Pipe): Conecta la salida de un comando con la entrada de otro.

\\ash
history | tail -50 > tarea-s1-pablo_mora.txt
\
---

## 4. Conocimientos Previos

Para realizar esta práctica el estudiante necesita tener claro los siguientes temas:

- Conceptos básicos de sistemas operativos (qué es un proceso, archivo, directorio).
- Diferencia entre interfaz gráfica (GUI) y línea de comandos (CLI).
- Conocimiento básico del sistema de archivos en Linux (jerarquía de directorios).
- Manejo básico de un emulador de terminal (WSL, Git Bash, Terminal de Linux).
- Comprensión de rutas relativas y absolutas en Linux.
- Instalación y configuración básica de WSL en Windows.

---

## 5. Objetivos a Alcanzar

- Crear una estructura de directorios jerárquica usando el comando mkdir -p.
- Crear y manipular archivos de texto usando echo, touch y redirección.
- Copiar archivos entre directorios con el comando cp.
- Mover y renombrar archivos con el comando mv.
- Aplicar redirección (> y >>) para gestionar el contenido de archivos.
- Eliminar archivos y directorios con rm y rmdir.
- Utilizar tuberías (|) para redirigir la salida del historial de comandos a un archivo.

---

## 6. Equipo Necesario

- Computador con sistema operativo **Windows 10/11** con WSL2 habilitado.
- **Ubuntu** instalado a través de WSL (Windows Subsystem for Linux).
- Acceso a **Git** para subir el proyecto a GitHub.
- Cuenta activa en **GitHub**.

---

## 7. Actividades Desarrolladas

### Paso 1: Creación de la Estructura de Carpetas

\\ash
cd ~
mkdir -p proyecto_comandos/documentos proyecto_comandos/imagenes proyecto_comandos/scripts
ls -la proyecto_comandos/
\
**Resultado:**
\total 20
drwxr-xr-x  5 pablo pablo 4096 Oct 14 07:19 .
drwxr-x--- 11 pablo pablo 4096 Oct 14 07:19 ..
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 documentos
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 imagenes
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 scripts
\
---

### Paso 2: Creación y Edición de notas.txt

\\ash
echo 'Linea 1: Los comandos de Linux permiten gestionar el sistema de manera eficiente.' > proyecto_comandos/documentos/notas.txt
echo 'Linea 2: El comando mkdir crea directorios, y con -p crea subdirectorios anidados.' >> proyecto_comandos/documentos/notas.txt
echo 'Linea 3: El comando echo redirige texto a archivos usando > o >> segun el caso.' >> proyecto_comandos/documentos/notas.txt
cat proyecto_comandos/documentos/notas.txt
\
**Resultado:**
\Linea 1: Los comandos de Linux permiten gestionar el sistema de manera eficiente.
Linea 2: El comando mkdir crea directorios, y con -p crea subdirectorios anidados.
Linea 3: El comando echo redirige texto a archivos usando > o >> segun el caso.
\
---

### Paso 3: Copia de Archivo (cp)

\\ash
cp proyecto_comandos/documentos/notas.txt proyecto_comandos/scripts/backup_notas.txt
ls -la proyecto_comandos/scripts/
\
**Resultado:**
\total 12
drwxr-xr-x 2 pablo pablo 4096 Oct 14 07:19 .
drwxr-xr-x 5 pablo pablo 4096 Oct 14 07:19 ..
-rw-r--r-- 1 pablo pablo  257 Oct 14 07:19 backup_notas.txt
\
---

### Paso 4: Movimiento de Archivo (mv)

\\ash
mv proyecto_comandos/scripts/backup_notas.txt proyecto_comandos/imagenes/backup_notas.txt
ls -la proyecto_comandos/imagenes/
\
**Resultado:**
\total 12
drwxr-xr-x 2 pablo pablo 4096 Oct 14 07:19 .
drwxr-xr-x 5 pablo pablo 4096 Oct 14 07:19 ..
-rw-r--r-- 1 pablo pablo  257 Oct 14 07:19 backup_notas.txt
\
---

### Paso 5: Redirección y Concatenación (resumen.txt)

\\ash
touch proyecto_comandos/documentos/resumen.txt
cat proyecto_comandos/documentos/notas.txt > proyecto_comandos/documentos/resumen.txt
echo 'Linea 4: La redireccion de contenido es una herramienta poderosa en Linux.' >> proyecto_comandos/documentos/resumen.txt
cat proyecto_comandos/documentos/resumen.txt
\
**Resultado:**
\Linea 1: Los comandos de Linux permiten gestionar el sistema de manera eficiente.
Linea 2: El comando mkdir crea directorios, y con -p crea subdirectorios anidados.
Linea 3: El comando echo redirige texto a archivos usando > o >> segun el caso.
Linea 4: La redireccion de contenido es una herramienta poderosa en Linux.
\
---

### Paso 6: Eliminación de Archivo (rm)

\\ash
rm proyecto_comandos/imagenes/backup_notas.txt
ls -la proyecto_comandos/imagenes/
\
**Resultado:**
\total 8
drwxr-xr-x 2 pablo pablo 4096 Oct 14 07:19 .
drwxr-xr-x 5 pablo pablo 4096 Oct 14 07:19 ..
\
---

### Paso 7: Eliminación de Carpeta Vacía (rmdir)

\\ash
rmdir proyecto_comandos/imagenes
ls -la proyecto_comandos/
\
**Resultado:**
\total 16
drwxr-xr-x  4 pablo pablo 4096 Oct 14 07:19 .
drwxr-x--- 11 pablo pablo 4096 Oct 14 07:19 ..
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 documentos
drwxr-xr-x  2 pablo pablo 4096 Oct 14 07:19 scripts
\
---

### Paso 8: Volcado del Historial de Comandos

\\ash
history | tail -50 > ~/proyecto_comandos/tarea-s1-pablo_mora.txt
\
---

## 8. Resultados Esperados

| Actividad | Comando Principal | Resultado |
|-----------|-----------------|-----------|
| Crear estructura de carpetas | mkdir -p | 3 subcarpetas creadas exitosamente |
| Crear archivo con texto | echo > y echo >> | notas.txt con 3 líneas |
| Copiar archivo | cp | backup_notas.txt creado en scripts/ |
| Mover archivo | mv | backup_notas.txt movido a imagenes/ |
| Redirección y concatenación | cat > y echo >> | resumen.txt con 4 líneas |
| Eliminar archivo | rm | backup_notas.txt eliminado |
| Eliminar carpeta vacía | rmdir | Carpeta imagenes/ eliminada |
| Volcar historial | history pipe tail > | Archivo tarea-s1-pablo_mora.txt generado |

---

## 9. Conclusiones

- Los comandos básicos de Linux como mkdir, cp, mv, rm y rmdir permiten gestionar el sistema de archivos de manera eficiente y rápida desde la terminal.
- La redirección de salida (> y >>) es una herramienta fundamental que permite manipular el contenido de archivos sin necesidad de un editor gráfico.
- El uso de tuberías (|) permite conectar la salida de un comando con la entrada de otro, creando flujos de trabajo potentes y flexibles.
- El uso de WSL permite a los usuarios de Windows trabajar en un entorno Linux real sin necesidad de una máquina virtual o partición separada.
- Dominar la línea de comandos de Linux es una habilidad esencial para cualquier profesional de tecnología.

---

## 10. Bibliografía

- The Linux Documentation Project. (2023). GNU/Linux Command-Line Tools Summary. https://tldp.org/
- Canonical Ltd. (2024). Ubuntu WSL Documentation. https://ubuntu.com/wsl
- GNU Project. (2024). GNU Coreutils Manual. https://www.gnu.org/software/coreutils/manual/
- Microsoft. (2024). Windows Subsystem for Linux Documentation. https://learn.microsoft.com/en-us/windows/wsl/
- Ramey, C., & Fox, B. (2024). Bash Reference Manual. https://www.gnu.org/software/bash/manual/

---

*Informe elaborado por: **Pablo Mora***  
*Asignatura: Tendencias en Tecnología*  
*Fecha: Octubre 2026*
