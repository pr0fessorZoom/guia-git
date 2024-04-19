# Guia Git y GitHub
## Que son Git y GitHub?
- Son un sistema de control de versiones, en palabras simples nos ayuda a gestionar las versiones de nuestros proyectos, tambien permite que varias personas puedan trabajar en el mismo proyecto simultaneamente, ademas de poder ver el historial de cambios y quin hizo cada cambio.
- Git: Este sistema de control de versiones se ejecuta localmente en tu computadora y se utiliza a través de la terminal.
- GitHub: Es un servidor remoto donde se alojan los proyectos en la web, permitiendo que varios usuarios se conecten simultáneamente y colaboren en ellos.

## Por que siempre deberiamos utilzar Git?
- Es esencial y altamente recomendable utilizar un sistema de control de versiones por varias razones clave. En primer lugar, evita la proliferación de archivos al permitirnos gestionar los cambios en un solo lugar, lo que resulta fundamental dado que los proyectos suelen experimentar modificaciones constantes. Además, el sistema registra automáticamente la hora, fecha y el responsable de cada modificación, lo que facilita la identificación de responsabilidades y la colaboración en equipo. Por último, nos proporciona un historial detallado de todos los cambios realizados, lo que nos permite revertir a versiones anteriores en caso necesario, lo que es invaluable para mantener la integridad y la coherencia del proyecto a lo largo del tiempo.

## Que son Staging y los Repositorios?
- El staging y los repositorios son conceptos fundamentales en Git. Al utilizar el comando `git init` dentro de un directorio en la consola de Git, se crea un área en la memoria RAM llamada staging. En esta área, inicialmente se añaden los cambios que deseamos incluir en el próximo commit. Además, se crea el repositorio, representado por una carpeta oculta llamada `.git`. Este repositorio almacena toda la información necesaria para controlar las versiones del proyecto, incluyendo el historial de cambios y configuraciones específicas del repositorio, a menudo referido como 'master' o en nuevas versiones se recomienda renombrar como 'main'.
- Al utilizar el comando `git add`, los cambios que hemos realizado se preparan para ser incluidos en el próximo commit y se envían al área de staging. Posteriormente, al emplear el comando 'git commit -m ...', los archivos con los cambios preparados en el staging se guardan de manera permanente en el repositorio. Esto significa que los cambios se registran oficialmente en la historia del proyecto y se convierten en parte de la versión actual del mismo.
- Para poder revisar todos estos cambios utilizaremos `git checkout`

## Que son las Branches y Merge?
- Por defecto, cuando trabajamos en Git, estamos en una rama (branch) llamada 'master'. Esta rama representa la línea principal de desarrollo del proyecto, donde cada commit que realizamos crea una nueva versión del mismo. La importancia de esto radica en mantener un historial claro y ordenado de las versiones del proyecto. Sin embargo, a veces necesitamos realizar experimentos o trabajar en nuevas funcionalidades sin alterar el proyecto principal. Es aquí donde las ramas (branches) cobran relevancia. Podemos crear una nueva rama, por ejemplo, llamada 'experimental', para llevar a cabo estos experimentos de manera segura, sin correr el riesgo de dañar el proyecto principal.

- Las ramas no solo sirven para experimentar, también son útiles para solucionar errores (bugs) o implementar nuevas características. Cuando hemos finalizado nuestros cambios en una rama y queremos integrarlos de vuelta en la rama principal (master), utilizamos el proceso de 'merge', que consiste en combinar los cambios de una rama con la rama principal. Esto nos permite mantener un flujo de trabajo organizado y colaborativo, donde cada cambio puede ser revisado y fusionado de manera controlada.

## Configuracion de Git
- Aunque es posible utilizar Git localmente sin necesidad de configuración adicional, es altamente recomendable tener todo configurado para trabajar con repositorios remotos. Configurar Git para trabajar con repositorios remotos nos permite aprovechar al máximo las capacidades colaborativas de la herramienta. Esto incluye la posibilidad de compartir nuestro código con otros colaboradores, realizar seguimiento de los cambios realizados por otros miembros del equipo, y sincronizar nuestros repositorios locales con repositorios remotos alojados en plataformas como GitHub, GitLab o Bitbucket. En resumen, la configuración adecuada de Git para trabajar con repositorios remotos facilita la colaboración efectiva y el flujo de trabajo en equipo.
`git config -l`  Revisamos las configuraciones de Git.
`git config --list --show-origin` Nos permite ver donde se alojan las configuraciones.
`git config --global user.name "nombre_usuario"` Configuramos el nombre de usuario de Git.
`git config --global user.email "email"` Configuramos el correo asociado a nuestro usuario de Git.
`ssh-keygen -t rsa -b 4096 -C "email"` Configuramos clave ssh (necesaria para GitHub).
  -> Nos preguntara si queremos guardarla en el directorio /ssh/id_rsa y generara una clave publica y una privada, y como su nombre indica la llave privada NO debes mostrarla a nadie y la llave publica es la que usaremos posteriormente en GitHub.
  -> Luego nos pregunta si queremos darle una clave (recomendado), esto es para el uso de la clave ssh.
`git config --global init.defaultBranch "main"` Con este comando cambiamos la configuracion de las branches iniciales por defecto, a Git no le gusta la configuracion MASTER por defecto, asi que recomienda cambiarla a main.

## Comandos
`git init` Iniciamos nuestro repositorio.
`git status` Permite ver el estado de los cambios del repositorio.
`git add "archivo"` Agregamos un archivo especifico.
`git add .` Agregamos todos los archivos creados/modificados.
NOTA: Agregar todos los archivos no es recomendable posterior a la primera vez, ya que esto puede conllevar a una brecha de seguridad o enviar cosas que no queriamos enviar.