# Aprendizaje de WordPress

## Este manual es una constancia sobre lo que voy avanzando en WordPress

### Estudiante

| Nombre                     | Carnet    |
| -------------------------- | --------- |
| César André Ramírez Dávila | 202010816 |

## Índice

1. [Despliegue en Docker](#despliegue-en-docker)
2. [Instalación de WordPress](#instalación-de-wordpress)
   - [Empezar Instalación](#empezar-instalación)
   - [Crear credenciales](#crear-credenciales)
   - [Finalización](#finalización)
   - [Inicio de sesión](#inicio-de-sesión)
   - [Pantalla Inicio](#pantalla-inicio)
3. [Configuración de Página](#configuración-de-página)
   - [Actualización](#actualización)
   - [Configuración de tema](#configuración-de-tema)
   - [Configuración de plantilla](#configuración-de-plantilla)
4. [Ediciones en la página](#ediciones-en-la-página)
   - [Vista Inicio](#vista-inicio)
   - [Vista Guía](#vista-guía)
   - [Vista Perfil](#vista-perfil)

## Despliegue en Docker

### Para poder usar WordPress en docker se hace uso de un docker-compose, en este caso la base de datos quedó con Mysql para fines de ejemplo.

### Usando el siguiente código, se usó de referencia lo de `WordPress` indicado en `DockerHub`

```yaml
## Usando de guía el proporcionado por docker hub de wordpress
version: "3.1"

# Creación de servicios
services:
  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      # Variables de entorno para la conexión a la base de datos
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb
    volumes:
      # Volumen para guardar los archivos de wordpress
      - wordpress:/var/www/html

  # Servicio de base de datos
  db:
    image: mysql:8.0
    restart: always
    ports:
      - 3306:3306
    environment:
      # Variables de entorno para la creación de la base de datos
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: "1"
    volumes:
      # Volumen para guardar los archivos de la base de datos
      - db:/var/lib/mysql

# Volumenes para guardar los archivos de wordpress y la base de datos
volumes:
  wordpress:
  db:
```

#### Para el despliegue en docker se hace de la siguiente manera

![Despliegue-Docker](IMG/Instalar/Docker_run.png)

## Instalación de WordPress

### Empezar Instalación

Procedemos con la instalación de WordPress, dónde tendremos que elegir el idioma de preferencia

![Empezar-Instalacion](IMG/Instalar/Instalar_wordpress.png)

### Crear credenciales

Necesitamos crear las credenciales de acceso y un nombre del proyecto

![Crear-Credenciales](IMG/Instalar/Credenciales.png)

### Finalización

Después de esto finaliza la instalación de WordPress

![Finalizar-Instalacion](IMG/Instalar/Finalizado.png)

### Inicio de sesión

Podemos hacer inicio de sesión con las credenciales creadas

![Iniciar-Sesion](IMG/Instalar/Iniciar_Sesion.png)

### Pantalla Inicio

Nos carga la pantalla de inicio de WordPress

![Pantalla-Inicio](IMG/Instalar/Bienvenida.png)

## Configuración de Página

En este momento se empieza el curso de WordPress

### Actualización

Antes de empezar nos sale una actualización de WordPress, procedemos con la instalación.

![Mensaje](IMG/Astra/Mensaje_Actualizacion.png)

Nos aparece que hemos actualizado correctamente.

![Actualizado](IMG/Astra/Actualizado.png)

### Configuración de tema

En este curso vamos a hacer uso de plantillas proporcionadas de WordPress, en específico la de `Astra`

Hacemos la busqueda del tema

![Busqueda](IMG/Astra/Buscar_Astra.png)

Antes de usar este tema revisamos como nos aparece la página.

![Antes](IMG/Astra/Antes_del_tema.png)

Aplicamos el tema y volvemos a verificar la página.

![Despues](IMG/Astra/Despues_del_tema.png)

### Configuración de plantilla

Ahora procedemos a ir a la parte de Astra para activar la plantilla

![PlantillaInicio](IMG/Astra/Plantilla_Inicio.png)

A continuación nos aparece que ya podemos empezar la construcción de la plantilla.

![Construccion](IMG/Astra/Empezar_construccion.png)

Seleccionamos el clásico y continuamos.

![Plantillas](IMG/Astra/Seleccion_plantilla.png)

En este caso seleccionamos la plantilla `Nature`.

![Aplicar](IMG/Astra/Aplicar_plantilla.png)

Le damos continuar y la aplicamos, luego nos aparece el siguiente mensaje.

![Finalizado](IMG/Astra/Terminar_plantilla.png)

## Ediciones en la página

En esta parte la edición queda a criterio de la persona, en mi caso las llevo de la siguiente manera:

### Vista Inicio

Se muestra la cabecera.

![Inicio1](IMG/Edicion/Home1.png)

Se muestra el pie de página.

![Inicio2](IMG/Edicion/Home2.png)

Esta vista se está editando con elementor.

![Inicio3](IMG/Edicion/Edit_home.png)

### Vista Guía

Se muestra información de este curso.

![Guia1](IMG/Edicion/guia1.png)

Se muestra información de los tutoriales vistos.

![Guia2](IMG/Edicion/guia2.png)

Esta vista se está editando con el editor de WordPress.

![Guia3](IMG/Edicion/edit_guia.png)

### Vista Perfil

Se muestra un poco de mi información academica.

![Info1](IMG/Edicion/info1.png)

Se muestra información de algunos proyectos de la carrera.

![Info2](IMG/Edicion/info2.png)

Esta vista se está editando con el editor de WordPress.

![Info3](IMG/Edicion/edit_info.png)
