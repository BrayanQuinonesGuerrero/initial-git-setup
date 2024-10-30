# Configuración incial de Git

Esta guía cubre algunos comandos esenciales para configurar Git a nivel global en el sistema. Estos comandos definen el comportamiento del editor, el formato del log y otros aspectos importantes.

## Configuración básica de usuario

Establece el nombre y correo electrónico globales para todos los repositorios en este sistema.

```bash
git config --global user.name 'JohnDoe'
git config --global user.email "example@gmail.com"
```

- **`user.name`**: Define el nombre del usuario que aparecerá en los commits.
- **`user.email`**: Especifica el correo electrónico asociado a los commits.
- **Nota:** Recuerda reemplazar `"JohnDoe"` y `"example@gmail.com"` por tu propio nombre y correo electrónico.

## Editor predeterminado

Define el editor de texto para Git. Si deseas usar VSCode como editor, este comando abrirá el editor y esperará que el archivo se cierre antes de continuar.

```bash
git config --global core.editor "code --wait"
```

- **`core.editor`**: Indica el editor de texto que se abrirá para mensajes de commit y otras ediciones.

## Control de fin de línea

Establece cómo Git manejará los saltos de línea, útil para colaborar en proyectos entre sistemas operativos diferentes.

```bash
git config --global core.autocrlf input
```

- **`core.autocrlf`**: Con `input`, convierte CRLF a LF al cargar archivos, pero los deja sin cambios al extraerlos. Esto es ideal para sistemas UNIX/Linux.

## Abreviación de hash

Limita la cantidad de caracteres en los identificadores de commit que muestra Git, lo cual es útil para simplificar la visualización en logs.

```bash
git config --global core.abbrev 12
```

- **`core.abbrev`**: Muestra los hash de commit abreviados a 12 caracteres.

## Colores en Git

Activa los colores en la salida de Git para mejorar la legibilidad en la terminal.

```bash
git config --global color.ui true
```

- **`color.ui`**: Habilita la coloración en las salidas de Git.

## Rama por defecto

Define el nombre de la rama principal al inicializar un repositorio. `main` es una práctica común en lugar de `master`.

```bash
git config --global init.defaultBranch main
```

- **`init.defaultBranch`**: Especifica `main` como la rama inicial predeterminada en nuevos repositorios.

## Alias para el log de Git

Crea un alias para ver el historial de commits en un formato gráfico, con colores y detalles como la fecha relativa y el autor.

```bash
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C()%s%C(reset) %C(white)- %an%C(reset)%C(bold red)%d%C(reset)' --all"
```

- **`alias.lg`**: Muestra un log gráfico con una visualización compacta:
  - `%h`: Hash abreviado del commit.
  - `%ar`: Tiempo relativo del commit (ej. "2 hours ago").
  - `%s`: Mensaje del commit.
  - `%an`: Nombre del autor del commit.
  - `%d`: Referencias del commit (ej. nombres de ramas).

### Ejemplo de uso

Para ver el log de commits usando el alias configurado ejecuta el siguiente comando:

```bash
git lg
```