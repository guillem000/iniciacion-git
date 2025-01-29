# Práctica de git y GitHub

\[Las modificaciones del paso 3 van aquí\]

Este es un repositorio muy simple para practicar con git y GitHub. git es una utilidad para el *control de versiones*. Cuando un conjunto de código está bajo seguimiento con git, es fácil ver cómo ha evolucionado el software con el tiempo, revertir cambios cuando sea necesario e incorporar modificaciones de múltiples colaboradores. En esta actividad, nos enfocaremos en los flujos de trabajo esenciales de git para proyectos individuales. Es posible que más adelante realicemos una actividad adicional sobre flujos de trabajo en grupo.

GitHub es un servicio gratuito de alojamiento de código en línea que funciona con git. Usaremos git y GitHub para proyectos con código y para trabajar de forma conjunta.

***Nota***: si ya estás cómodo usando git desde la línea de comandos, puedes seguir estas instrucciones sustituyendo las operaciones de GitHub Desktop por los comandos equivalentes en la terminal. ¡Ambos enfoques son válidos!

## 0. Pasos previos  / Requisitos instalación

Ya deberías haber creado una cuenta en [GitHub](https://github.com/) y descargado la app [GitHub Desktop](https://desktop.github.com/). 

## 1. Crear una rama (Fork)

*Fork o Forking* se refiere al acto de crear tu propia copia personal de un conjunto de código existente, esto en español se le conoce como 'rama'. Luego puedes modificar tu rama a tu gusto. El uso de las ramas es una excelente manera de aprovechar plantillas y otros recursos sobre los que puedes construir. Por ejemplo, pronto harás una rama de una plantilla para tu sitio web, que luego personalizarás.

Adelante, crea una rama de este repositorio usando el botón "Fork" en la esquina superior derecha.

Revisa tu rama. Por ahora, es solo una copia del [repositorio original](https://github.com/victor-educ/iniciacion-git). 

## 2. Clonar (Clone)

Ahora tienes una copia de este repositorio en GitHub. ¿Pero cómo puedes hacer cambios? Es posible editar archivos manualmente en GitHub, pero no es nada conveniente. En su lugar, deberías crear un *clon local* del repositorio. Para hacerlo, presiona el botón verde grande y elige "Abrir en GitHub Desktop". Elige una ubicación donde puedas recordar fácilmente el repositorio.

## 3. Editar un archivo

En tu clon local del repositorio, abre este archivo (`README.md`). En la parte superior del archivo, debajo del título, escribe:

> Me llamo \[tu nombre\] y he editado este archivo 

## 4. Añade los cambios y confirma (Add and Commit)

Ahora ve a GitHub Desktop. Observa que el archivo `README.md` aparece listado como cambiado. Si no hay una marca azul de verificación junto al archivo, haz clic en la casilla para agregarla.

Luego, agrega un *mensaje de commit* en el cuadro debajo. El mensaje debe ser una breve descripción de los cambios que hiciste en el código. Por ejemplo, un buen mensaje de commit aquí podría ser:
> "Se ha añadido el nombre del autor al archivo README.md."

Una vez que hayas ingresado el mensaje, haz clic en el botón azul grande "Commit".

## 5. Crear una carpeta y un fichero

Ahora que hemos aprendido un poco de los básicos vamos a complicarlo más.

Crea una nueva carpeta llamada `carpeta-pruebas` dentro del repositorio clonado. Acto seguido, crea un archivo 'Jupyter Notebook' en esta carpeta. Añade el siguiente código al archivo para obtener un gráfico matemático simple:

```python
from matplotlib import pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 1001)
y = np.sin(x)
f = plt.plot(x,y)
``` 
Asegúrate de guardar el *notebook* resultante.

## 6. Añade los cambios y confirma (Add and Commit)

Ahora, añade el archivo (haz click en el check). Agrega un mensaje de commit informativo y confirma el archivo.

## 7. Subir los cambios (Push)
¡Perfecto! Ya hemos hecho algunos cambios locales. Nuestra tarea principal ahora es hacer push de nuestro código de vuelta a GitHub. Esto nos permitirá compartir nuestro código con otros. Además, hacer push del código a GitHub es la forma recomendada de trabajar con tus proyectos.

Para hacer push de tu código, simplemente haz clic en el botón negro "Push" en la parte superior derecha de GitHub Desktop. Antes de hacer clic, puedes ver que el botón indica el número de commits que has hecho desde tu último push. Después de hacer clic, ya no habrá más commits por subir.

## 8. Inspeccionar el repositorio en GitHub

Ahora ve a la URL de tu fork en GitHub e inspecciona el archivo `README.md` modificado. También puedes ver el Jupyter Notebook que creaste. Observa una función interesante: por defecto, GitHub renderiza el notebook para que puedas ver el gráfico que creaste y el código en un formato atractivo y legible. 

## 9. Actualizar el proyecto (Pull)

Si se realiza un cambio en GitHub que no está presente en tu repositorio local, necesitarás hacer pull para actualizarlo.

Edita nuevamente el archivo `README.md` en GitHub del navegador, agregando otra línea en la parte superior:

> Soy \[tu nombre\] y he editado este fichero en la pagina web de Github! 

Confirma el cambio con un mensaje de commit adecuado.

En GitHub Desktop, el botón "Push" ahora debería decir "Fetch" o "Pull". Si dice "Fetch", haz clic y espera a que cambie a "Pull". Luego, haz clic en "Pull" y espera unos momentos.

Finalmente, revisa el archivo README.md en local. El cambio realizado en la web debería reflejarse ahora en tu archivo local.

## 10. Descartar los cambios y revertir (Discard and Revert)

Un beneficio clave de git es que puedes revertir errores. Hay dos formas principales de hacerlo:

### 10.1 Si aún no has realizado la confirmación: Descartar (Discard)

Así que, estabas haciendo un pequeño ajuste a uno de tus archivos y accidentalmente rompiste el proyecto en el que estabas trabajando. Suele pasar. Si te das cuenta antes de confirmar los cambios, arreglarlo es fácil: todo lo que tienes que hacer es *descartar* tus cambios. 

En el cuaderno Jupyter que has creado en el Paso 5, borra la línea `import numpy as np`. Ahora tu cuaderno no generará correctamente el gráfico (después de reiniciar el kernel). ¡Ups! Finge que no te has dado cuenta y guarda el archivo. 

En GitHub Desktop, observa que hay un cambio registrado en ese archivo. Haz clic con el botón derecho en el cambio y elige «Descartar cambios». Revisa de nuevo tu cuaderno. Deberías observar que la línea `import numpy as np` está de nuevo donde debe estar. ¡Genial!

### 10.2 Si ya has confirmado: Revertir (Revert)

A veces, no nos damos cuenta de un error hasta que ya lo hemos confirmado. Si no tenemos suerte, puede que incluso hayamos creado otros commits desde nuestro error. En estos casos, el primer paso es identificar en qué commit se introdujo el error. Esto requiere una depuración cuidadosa y atención a los detalles. Un enfoque es *retroceder* a una confirmación anterior en la que sepas que tu código funcionaba, y luego repasar los cambios que hiciste. Para ello, utilizamos el comando *revert*. 

Vuelve a tu Jupyter Notebook, y borra `import numpy as np` de nuevo. Esta vez, confirma el cambio, con el mensaje de confirmación «remove numpy import». ¡Ups! Ahora nuestro código confirmado está roto. 

Para *revertir* el commit, ve a la pestaña Historial de GitHub Desktop. Haz clic con el botón derecho en el commit con el mensaje «remove numpy import», y elige «Revert Changes in Commit». Esto tendrá el efecto de crear un *nuevo* commit que deshace los cambios que introdujo el commit con errores. Esto funcionará incluso si has hecho otros commits desde el commit erróneo; sólo se revertirán los cambios del commit erróneo. 

***Nota***: GitHub Desktop no da una opción correspondiente a `git reset`, pero si te sientes cómodo en el terminal y estás familiarizado con este comando, también puedes utilizar `git reset` para realizar una tarea similar, aunque con diferentes consecuencias para tu historial de commits.

### 11. ¡No dupliques archivos! 

Un principio importante del control de versiones es que **NUNCA** dupliques archivos. En lugar de tener `ej1.ipynb`, `ej1_final.ipynb`, `ej1_final_final.ipynb`, solo tienes que trabajar con un documento `ej1.ipynb` en el que tendrás que ir confirmando los cambios según vayas haciendolos. Siempre podrás volver atrás y encontrar las versiones anteriores en el historial de commits. 
