# Lineamientos Para El Equipo De Desarrollo

Este documento presenta algunas buenas practicas que se aplican a discrecion a cualquier proyecto desarrollado. al igual que la tecnologia evoluciona estos lineamientos tambien lo pueden y deberian hacerlo por tanto esta abierto a debate o proposicion. 

## Reglas de Codificacion


### Generales

Cada proyecto debe autodescribirse en un archivo readme bajo formato markdown en la raiz del mismo definiendo objetivo alcance y tecnologias a usar asi como hiperenlaces a su documentacion.

Cada Proyecto debe respatar los lineamientos sugeridos por el lenguaje y sus librerias y/o frameworks.

Cada proyecto debera definir 2 reglas para la codificacion que deben ser plasmadas en el archivo readme de dicho proyecto:

* Lenguaje a utilizar
  * este aplica tanto para variables y funciones como para comentarios y commits.
* tamaño de identacion

El codigo independientemente del lenguaje debe seguir una identacion apropiada apegandose a los estandares que el lenguaje proponga para sus tokens especificos y de no acordar algun estandar se usara la identacion de 1 tab equivalente a 4 espacios.

Se debe prescidir de usar abreviaturas o contracciones para la definicion de funciones, clases, variables etc, para priorizar la legibilidad y autodescripcion del codigo.

No se debe pensar en optimizacion de codigo hasta que este no demuestre requerirlo, se debe priorizar la simplicidad del codigo y evitar la optimizacion prematura.

Cada archivo debe contener a el inicio del mismo un comentario multilinea siguiendo las especificaciones del lenguaje que contenga el autor, fecha en que se creo, fecha de ultima actualizacion y descripcion de el objetivo general del archivo, ejemplo en javascript:

```javascript
/**
 * @Author Marco A. Gallegos
 * @Date 2020/11/30
 * @Update 2020/12/01
 * @Description
 *  Este archivo gestiona la respuesta a los endpoints utilizando la logica de los servicios
 */
```

Cada funcion y metodo debe tener un comentario multilinea respetando los estandares del lenguaje que explique su objetivo general, sus variables de parametro y su retorno, ejemplo en javascript:

```javascript
/**
 * Esta funcion crea una notificacion de ticket basado en el 
 * UUID (_id) de un ticket previamente creado.
 * 
 * @param {uuid} ticketId id del ticket del cual se creara notificacion
 * @return {bool} status
 */
```

Cada clase, interfaz, clase abstracta, modelo etc, debe tener, en caso de archivos con mas de una definicion, un comentario multilinea respetando los estandares del lenguaje que describa su objetivo general, ejemplo javascript:

```javascript
/**
 * Clase para representar cada imagen del servidor remoto
 */
```

Cada archivo, funcion, metodo etc, que se edite debe actualizar su campo update.

No se deben editar archivos originarios en local, es decir dependencias de npm, composer, docker images etc. Si se requiere implementar una funcion perzonalida en alguna dependencia el proceso correcto puede ser de 2 formas:

- Crear un pull request al proyecto respetando sus lineamientos y esperar su integracion
- crear un fork del proyecto e implementarlo mediante el host por defecto del lenguaje (ej: npmjs, packagist, pypi) o integrarlo como un modulo local independiente.

### WEB

##### Frontend y Diseño

No se debe usar css embedido salvo en casos donde la definicion del lenguaje o framework provean metodologias que aislen el codigo y solo si este solo aplica para ese elemento, se debe usar sass en archivo de estilos general del proyecto.



##### Backend


## flujo git/github

se consideraran 2 repositorios para trabajar :

- produccion y testing (PaulinaNeo)
- fork personal para desarrollo


### produccion y testing (PaulinaNeo)

Este repositorio es el codigo que se desplegara en los servidores de pruebas y produccion y por tanto no debe ser modificado de forma directa salvo que la situacion asi lo requiera, este repo debe ser actualizado por medio de pull requests de alguno de sus repositorios hijos.


### Fork Personal

El fork personal es de libre administracion el objetivo es tener un ambiente seguro para realizar los merges necesarios para probar integraciones.

### Descripcion del flujo

![flujo de trabajo](./img/workflow%20git.png)

### Herramientas

una valiosa herramienta para automatizar algunas tareas de branching es [gitflow](https://danielkummer.github.io/git-flow-cheatsheet/)


## Git

### Formato de commit

Ya que los commits nos ayudan a saber que se a hecho a traves de la historia del proyecto es necesario que sean claros y explicativos, por tanto nos apegaremoa a algun estandar para realizar esta tarea, en este caso usaremos la metodologia propuesta en los [guidelines oficiales de odoo v14.0](https://www.odoo.com/documentation/14.0/reference/guidelines.html#commit-message-structure)  :

```shell
[TAG] (modulo):(Descripcion del commit menor a 51 caracteres).

Descripcion ampliada
```

Lista de Tags:

* [FIX] for bug fixes: mostly used in stable version but also valid if you are fixing a recent bug in development version;
* [REF] for refactoring: when a feature is heavily rewritten;
* [ADD] for adding new modules;
* [REM] for removing resources: removing dead code, removing views, removing modules, …;
* [REV] for reverting commits: if a commit causes issues or is not wanted reverting it is done using this tag;
* [MOV] for moving files: use git move and do not change content of moved file otherwise Git may loose track and history of the file; also used when moving code from one file to another;
* [REL] for release commits: new major or minor stable versions;
* [IMP] for improvements: most of the changes done in development version are incremental improvements not related to another tag;
* [MERGE] for merge commits: used in forward port of bug fixes but also as main commit for feature involving several separated commits;


## Arquitectura de codigo

Es muy importante a pesar del tamaño de lo desarrollado utilizar un estandar para asegurar la calidad del codigo por tanto deberemos utilizar alguna estrategia para diseñar el software, la arquitectura o metodologia a utilizar sera [SOLID](https://profile.es/blog/principios-solid-desarrollo-software-calidad/).


## Documentacion

Todo proyecto debera tener documentacion de los siguientes tipos:

* manuales de usuario
* Documentacion tecnica
* Documentacion de codigo


[guia](https://www.linuxito.com/programacion/1402-guia-para-la-documentacion-de-proyectos-de-software)

## Unit testing


## extensiones utiles

### multiples editores

### vscode


## referencias

https://es.wikipedia.org/wiki/Optimizaci%C3%B3n_prematura