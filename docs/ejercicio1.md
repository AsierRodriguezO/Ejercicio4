# EJERCICIO 1 — Descripción paso a paso para desplegar el tema Jekyll “minima” en GitHub Pages

Fecha: 13 de noviembre de 2025

## Introducción

En este documento se describen, en detalle y en formato paso a paso, los procesos para:

- Crear, configurar y probar un sitio Jekyll usando el tema oficial `minima`.
- Personalizar páginas y posts (añadir al menos 1 página nueva y 3 publicaciones).
- Desplegar el sitio en GitHub Pages .


## 1) Crear un nuevo sitio Jekyll con tema `minima`

1. Crear el sitio (desde el directorio donde quieras trabajar):

```bash
jekyll new miblog2 
cd miblog2
```
![imagen1](img/ejer1/imagen.png)

  El tema minima ya esta instalado por defecto en jekyll asique no hace falta cambiar nada.


## 2) Configurar `_config.yml`

El archivo `_config.yml` contiene los pares clave/valor que Jekyll usa. A continuación un ejemplo con campos mínimos y cómo personalizarlo con tu nombre.

```yaml
title: "Mi blog - Tema Minima"
email: "tu_email@example.com"
description: "Un blog sobre [temática con sentido] — por Tu Nombre Apellidos"
baseurl: "/mi-blog" # <- para GitHub Pages de proyecto; usar "" si es un site de usuario (username.github.io)
url: "https://tu_cuenta_github.github.io" # Sin baseurl
author:
  name: "Tu Nombre Apellidos"
  email: "tu_email@example.com"
theme: minima
paginate: 5


```
![imagen2](img/ejer1/imagen1.png)


## 3) Personalizar páginas (index.markdown, about.markdown) y crear una página nueva

Para personalizar entramos a los ficheros y los editamos con markdown para que despues se traduzca a html.

>Index.markdown:

![imagen3](img/ejer1/imagen2.png)

>About.markdown:

![imagen4](img/ejer1/imagen3.png)

## 4) Crear al menos 3 posts

Los posts deben ir en `_posts/` y el nombre de archivo debe tener formato `YYYY-MM-DD-titulo.markdown`.

Ejemplo de 3 posts mínimos:

`_posts/2025-11-13-presentacion-blog.markdown`:

En mi caso he creado bastantes post.

![imagen5](img/ejer1/imagen4.png)

![imagen6](img/ejer1/imagen5.png)

Consejos sobre imágenes:

- Añade las imágenes en `assets/imagenes/` (o donde prefieras). GitHub Pages sirve esos archivos estáticos.
- Usa rutas completas con `{{ site.baseurl }}` si `baseurl` no está vacío.

## 5) Git: inicializar, comitear y subir al repositorio de GitHub

1. Inicializar git (si no está):
```bash
git add .
git commit -m "Sitio Jekyll con tema minima - inicial"
git push origin gh-pages (este se hace para subirlo en la rama gh-pages)
```
![imagen7](img/ejer1/imagen6.png)

2. Crear repositorio en GitHub (puedes usar la interfaz web o `gh` CLI). Supondremos que el repo se llama `mi-blog`.

```bash
git remote add origin https://github.com/tu_cuenta_github/mi-blog.git
git branch -M main
git push -u origin main
```

3. En GitHub: ve a Settings → Pages. Selecciona la rama `main` (o `gh-pages` si prefieres publicar contenido estático) y la carpeta `/ (root)` como fuente. Guarda.

Notas sobre ramas y estrategias de despliegue:

![imagen8](img/ejer1/imagen7.png)

## 6) Ajustes finos y ejemplos prácticos para `baseurl` y rutas

- Si `baseurl` = "/mi-blog" entonces en las plantillas y enlaces escribe: `{{ site.baseurl }}{{ post.url }}` o para assets: `{{ site.baseurl }}/assets/imagenes/ejemplo.jpg`.
- Si `baseurl` = "" (sitio de usuario), no uses `{{ site.baseurl }}`.

## 7) Verificación 
![imagen9](img/ejer1/imagen8.png)






