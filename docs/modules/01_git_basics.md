
# 🧑‍💻 Git Basics — First Steps

## 🎯 Objetivo
Aprender a usar Git para rastrear cambios en archivos. Al final de la sesión podrás:
- Clonar un repositorio de GitHub.
- Crear y modificar archivos.
- Rastrear cambios con Git.
- Realizar commits y subir cambios a GitHub.

---

## ✅ Ejercicio

En este ejercicio practicarás los comandos básicos de Git, siguiendo estos pasos:

1. Clona el repositorio.
2. Crea una carpeta con tu nombre (`student_name/`).
3. Dentro, crea un archivo `.txt`, uno `.tsv` y uno `.csv`.
4. Agrega y haz commit de tus archivos.
5. Modifica el archivo `.txt` y haz commit nuevamente.
6. Sube todo a GitHub.

Vamos a hacerlo juntos paso a paso.
---

## 1. Configuración Inicial

Configura tu entorno de Git (solo una vez por computadora):

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu_email@example.com"
git config --list
```

---

## 2. Clonar el Repositorio

Elige una carpeta de trabajo y clona el repositorio de la clase:

```bash
git clone https://github.com/ae-tafur/bioinfo-from-scratch.git
cd bioinfo-from-scratch
```

---

## 3. Crear Archivos Nuevos

Dentro de la carpeta del repositorio, crea tres tipos de archivos:

```bash
echo "Hello Bioinformatics" > example.txt
echo -e "name\tage\nAlice\t22\nBob\t25" > example.tsv
echo -e "name,age\nAlice,22\nBob,25" > example.csv
ls
```

---


## 4. Rastrear Cambios

Consulta los cambios detectados por Git:

```bash
git status
```

## 4.1 ¿Qué es un Commit?

Un commit en Git es una "foto" de los cambios realizados en tu proyecto en un momento específico. Permite guardar el estado actual de los archivos y dejar un registro de lo que se hizo y por qué.

Cada commit debe tener un mensaje claro que explique el propósito del cambio. Escribir buenos mensajes ayuda a otros (y a ti mismo en el futuro) a entender la historia del proyecto.

### Mensajes de Commit Convencionales

Una práctica recomendada es usar el formato de Conventional Commits, que facilita la lectura y automatización de los cambios. El formato básico es:

```
<tipo>[opcional alcance]: <descripción>

[opcional cuerpo]
[opcional pie de página]
```

**Ejemplos:**

- `feat: agrega función para procesar datos`
- `fix: corrige error de validación de usuario (login)`
- `docs: actualiza documentación del README`

**Tipos comunes:**
- `feat`: Nueva funcionalidad
- `fix`: Corrección de errores
- `docs`: Cambios en la documentación
- `style`: Formato, estilos, sin cambios en el código
- `refactor`: Refactorización del código
- `test`: Añade o corrige pruebas
- `chore`: Tareas de mantenimiento

**Recomendaciones:**
- Usa el imperativo: "agrega", "corrige", "actualiza".
- Sé breve y específico.
- Si el cambio es complejo, agrega un cuerpo explicativo.

Más información: [Conventional Commits](https://www.conventionalcommits.org/es/v1.0.0/)


Ahora que sabes qué es un commit y cómo escribir buenos mensajes, hagamos nuestro primer commit.

Agrega los archivos nuevos:

```bash
git add example.txt example.tsv example.csv
git commit -m "feat: Added example files (.txt, .tsv, .csv)"
```

---

## 5. Editar un Archivo

Edita `example.txt` con un editor de texto y agrega tu nombre. Luego:

```bash
git status
git diff
```

Guarda la nueva versión:

```bash
git add example.txt
git commit -m "chore: updated example.txt with my name"
```

---


## 6. Subir Cambios a GitHub

Sube tus cambios. Antes de hacer push, es buena práctica traer los últimos cambios del repositorio remoto. Si hay conflictos, podrás resolverlos localmente. Además, revisa las recomendaciones para autenticarse en computadores públicos que están al final de esta página.

```bash
git push origin main
```

---

## 7. Autenticación en Computadores Públicos

Si usas computadores públicos (por ejemplo, en la universidad), sigue estas recomendaciones para autenticarse y proteger tu cuenta de GitHub:

### ¿Qué ocurre al hacer push?
Al ejecutar `git push`, GitHub pedirá tu usuario y contraseña. Desde 2021, no puedes usar tu contraseña de GitHub directamente, sino un "Personal Access Token" (PAT).

### ¿Cómo obtener y usar tu token?
1. Ingresa a https://github.com/settings/tokens y genera un nuevo token personal (PAT).
2. Copia el token y guárdalo temporalmente (no lo compartas ni lo dejes guardado en el computador público).
3. Cuando Git pida la contraseña, pega el token en vez de tu contraseña.

### Usar VS Code para hacer push
Al hacer push desde VS Code, aparecerá una ventana para ingresar usuario y contraseña. Ingresa tu usuario de GitHub y pega el token como contraseña.

### Cerrar sesión y limpiar credenciales
- En VS Code, haz clic en el icono de usuario (abajo a la izquierda) y cierra sesión de GitHub.
- En la terminal, puedes limpiar las credenciales guardadas ejecutando:
	```bash
	git credential-cache exit
	```
- En macOS, abre "Keychain Access" y elimina las credenciales de GitHub si quedaron guardadas.

### Recomendaciones de seguridad
- No guardes el token en el computador público.
- Usa el modo incógnito del navegador para generar el token y bórralo después de usarlo.
- Cierra sesión de GitHub en VS Code y en el navegador al terminar.

Más información: [GitHub Docs - Authenticating to GitHub](https://docs.github.com/en/get-started/getting-started-with-git/authenticating-to-github)

---