---
layout: post
title: Creando tu propio blog fácil y rápido
subtitle: Hoy aprenderemos a crear un blog con Jekyll... Y en español.
bigimg: /img/path.jpg
category: blog
tags: [Programación]
comments: true
css:
  - '/css/extend-home.css'
---

Buenas a todos, espero que anden bien y que puedan tomarse un tiempo para leer ésta entrada:

Hoy aprenderemos a usar Jekyll, ya que a mi gusto como plataforma bloggin es excelente. Voy a comentar primero que nada las cosas buenas, las malas, y todo lo que he aprendido en esta semana sobre Jekyll. Comentar que tal fue y bueno, dar mi opinión personal y subjetiva.

## Qué es Jekyll?

Jekyll es una herramienta que permite crear blogs estáticos. Parecido a html5. La diferencia es que está basado en Ruby. El creador ha sido **Tom Preston-Werner** quien fue o es, uno de los creadores de Github. Por lo tanto, está herramienta se integra perfectamente con Github.
Algunos usuarios o bloggers, dirán que no es muy flexible pero yo creo que con un poco de conocimiento esta herramienta se transforma en un amigo para toda tu vida.

## Lo Bueno y lo Malo:

Lo bueno de esta plataforma Jekyll:

- Se puede tranquilamente alojar en github.
- Es muy fácil de publicar contenido
- Es absolutamente mucho más rápido que otros sitios webs
- Se puede trabajar tranquilamente con JS y CSS, y además html5
- se aprende mucho código en el camino!

Ahora, lo que a mi punto de vista es negativo:

- Es difícil de configurar para alguien inexperto
- No hay mucha información en español acerca de todas las funciones
- No hay una gran cantidad de templates o plantillas
- Si da el caso de que te aparezca un error, te vuelves loco buscando que es!

## Preparando tu ordenador para Jekyll:

 - Es necesario una cuenta GitHub Obviamente.
Si aún no posees una cuenta, te dejamos el link aquí para que puedas crear una:
[Github](http://github.com/).

<center><img src="/img/posts/github.png" height="500" width="900"></center>

## Instalación de Jekyll:

 En Debian/Ubuntu y derivados:
 
```console
$ sudo apt-get install git ruby jekyll
```

## Configuración básica:
 
 ```console
 $ git config --global user.name "nombre_usuario"
 $ git config --global user.email email_id
 ```
 
 *Presten atención el que usuario va dentro de las comillas, y el email no*
 
## Luego, procedemos a crear el repositorio:
 Para crear el repositorio es necesario que exista previamente en github.
 
<center><img src="/img/posts/github1.png" height="500" width="900"></center>
 
 Hacerlo es sencillo, solo hace falta crear la cuenta y luego ir a New Repository. 
 Seguido solo creas tu github de una manera sencilla: "tuusuario".github.io
 
<center><img src="/img/posts/github2.png" height="500" width="900"></center>
 
## Creamos el repositorio en nuestro ordenador:

 ```console
 $ git init tuusuario.github.io
  ```
## Ahora viene lo importante:

Ahora tenemos dos opciones: Si son ciertamente hábiles o saben programar eh HTML5, éste paso deberían saltarlo. Sin embargo, como esto es para noobs:
 - [Nos dirijimos a éste sitio web](http://jekyllthemes.org/) y descargamos algún template o plantilla que nos guste o nos convenga.
 
 Están todas en formatos .zip, así que extraigan la carpeta en el directorio de su git: /User/Home/usuario.github.io/
 
 Una vez dentro del directorio verán unas carpetas y no entenderán nada. Así que lo explicaré de la mejor manera posible:
 
<center><img src="/img/posts/jekyll.png" height="500" width="900"></center>
 
- **/_includes** Directorio del cuerpo de la pagina
- **/_layouts** Directorio del cuerpo de la pagina
- **/_posts** Directorio en donde van las entradas
- **/_css o /scss** Directorio donde están los css
- **/_img o /images** Directorio donde van las imágenes
- **/_config.yml** El archivo de configuración
- **/404.md** La pagina del error 404
- **/CNAME** Enlace a un dominio
- **/about.md** La pagina “acerca de”
- **/index.html** La pagina de inicio

*Ahora vamos a lo importante y lo que nos gusta*

## Editar el blog:

Aquí lo importante es LEER. Es necesario leer mucho

**Abrimos nuestro archivo _config.yml**
Y editan con lo necesario. Esta sección es bastante intuitiva, así que no será difícil configurarla.

*En este momento no voy a explicar todo sobre Jekyll, pero sí voy a aprovechar a aclarar algo. Cuando estén editando el archivo _config.yml... No vayan directo a abrir el servidor local. Más bien, traten de editar todos los archivos que terminen en .md (estos son archivos Markdown, los cuales si editas simplemente los html o index, los .md modifican automáticamente los otros, y no veras cambios hasta editas los -.md)*

Ahora, cuando hayas terminado todo. Vamos a subir el blog a Github:

  ```console
  $ git add --all
  $ git commit -m "Mensaje que quieras mostrar"
  $ git push -u origin master
  ```
  
  Te pedira el usuario y la contraseña, y si todo sale bien... Ya tendrás tu sitio web alojado en github:
  
  Ahora solo irás a **tuusuario.github.io** y listo. 
  
  ***¿Te parece algo complicado usar Jekyll? Espera que pronto subiré la segunda parte sobre cómo editar los archivos y tener tu blog personal con un poco de programación***
