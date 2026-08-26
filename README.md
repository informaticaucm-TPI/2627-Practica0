# Práctica 0: Primera aproximación a Java

## Fecha de entrega: semana del 14 de septiembre de 2026

En esta primera práctica vamos a tomar contacto con el entorno que usaremos para realizar las prácticas de la asignatura *Tecnología de la Programación I*.

 Se trata de una práctica guiada en cuyo enunciado vamos detallando, uno a uno, los pasos a seguir. La mayoría de los pasos que se describen serán necesarios también para el resto de prácticas, pues se enseña tanto la construcción de la estructura de directorios que utilizaremos como la creación de los proyectos de Eclipse y el mecanismo de entrega.

En este curso utilizaremos [*Java25*](https://www.oracle.com/java/technologies/downloads/#java25) y [*Eclipse 26.06*](https://www.eclipse.org/downloads/packages/release/2026-06/) ya que éstas son las versiones de las herramientas que están instaladas en los laboratorios de la Facultad.

## Estructura de directorios

Antes de comenzar, describiremos brevemente la estructura de directorios que vamos a utilizar durante todas las prácticas. Utilizar una estructura de directorios clara es importante cuando un proyecto utiliza varios ficheros de distintos tipos. Durante la elaboración de la práctica, manejaremos los siguientes directorios:

- `src`: directorio con el código fuente de la práctica (ficheros con extensión `.java`). Es el único directorio que contiene ficheros elaborados durante las prácticas. Los otros directorios o bien los  genera Eclipse automáticamente, o bien su contenido puede ser proporcionado por el profesor.
- `bin`: directorio donde aparecerán los ficheros resultado de la compilación del código fuente anterior. Lo crea el IDE (el entorno de desarrollo, esto es, Eclipse) automáticamente.

En prácticas siguientes es posible que se utilicen directorios adicionales. En concreto, si la práctica hace uso de bibliotecas externas proporcionadas por el profesor/a, podría aparecer otro directorio donde se añaden esas librerías. Esos posibles directorios adicionales *no* se deberán incluir en la entrega. 

## Primera parte: "Hello World" en consola

La primera parte de la práctica consiste en la creación de un proyecto simple en Java que escribe un simple `Hello World!`.

### Paso 1:

Abrimos el terminal `cmd.exe` (Windows > Ejecutar > `cmd.exe`). Una vez que se abre el terminal, debemos ubicarnos en el directorio `hlocal`ejecutando `cd c:\hlocal`.

Se crea un primer fichero de texto llamado "HelloWorld.java", que puede editarse con el NotePad++ / VS Code / bloc de notas[^1]. Java es sensible a mayúsculas/minúsculas, por lo que es importante mantener las mayúsculas donde se menciona aquí. Como puede observarse, el fichero tiene extensión `java`.

La siguiente imagen muestra cómo invocar el bloc de notas desde la línea de comandos de Windows.

![image](img/23_24_im00.png)

### Paso 2:

En el fichero creado en el paso anterior definimos una clase llamada "HelloWorld". Ojo, el nombre de la clase debe ser igual al del fichero. El código a escribir es el siguiente:

```Java
public class HelloWorld {
    public static void main(String[] args){
        System.out.println("Hello World!");
    }   
}
```

![image](img/23_24_im1.png)

### Paso 3:

Compilar `HelloWorld.java` desde la línea de comandos de Windows con  el comando:

```
javac HelloWorld.java
```

Si no hay errores de compilación se creará el fichero `HelloWorld.class`.

![image](img/23_24_im7.png)

Si hubo algún error, lo más probable es que se deba a que no se pudo invocar al compilador (`javac.exe`). El compilador debe ser accesible a través del PATH. Para ello, tendremos que agregar al PATH la dirección de la carpeta `bin` del JDK. En los laboratorios se encuentra en el directorio `C:\JDK\jdk25-x86_64\bin`. Para agregarlo podemos utilizar el siguiente comando:

```
set PATH=C:\JDK\jdk25-x86_64\bin;.;%PATH%
```

Posteriormente, para asegurarnos de que estamos usando la versión correcta, podemos ejecutar el siguiente comando:

```
java -version
```

![image](img/23_24_im7_j17.png)

### Paso 4:

Para ejecutar la aplicación se debe ejecutar la máquina virtual de Java y pedirle que utilice como punto de entrada de la aplicación la  clase `HelloWorld.class`. Para eso, se ejecuta el comando `java HelloWorld`[^2]. Igual que para compilar el código, para poder ejecutar la aplicación debe estar disponible `java` en el PATH. En los laboratorios se puede encontrar en el mismo directorio que el compilador.

![image](img/23_24_im777.png)

## Segunda parte: "Hello World" en Eclipse

Antes de empezar a trabajar en la plataforma de Eclipse, debemos aprender el significado de *workspace*.

1. Un espacio de trabajo (*workspace*) es una carpeta donde estarán las carpetas correspondientes a los proyectos Java creados con Eclipse.
2. Una instancia en ejecución de Eclipse solo puede trabajar con un workspace a la vez.
3. Cambiar el workspace requiere reiniciar Eclipse.

En lo que sigue asumiremos que el workspace lo ubicaremos en el directorio `c:\hlocal\TP`[^3].

> Recuerda borrar el directorio del proyecto (o del workspace) antes de terminar la sesión de laboratorio para evitar que alguien pueda utilizar tu código y pueda ser detectado como una copia de la práctica. 

Un *proyecto* es una carpeta que se crea en el workspace. Cada práctica será un proyecto nuevo. Dentro de un proyecto nos encontraremos las siguientes carpetas:

- `src`: Carpeta donde estará el código fuente (`source code`), es decir, los ficheros `.java`. **Ésta es la que hay que guardar (GDrive, OneDrive, directorio de red, etc.) cuando se acabe cada sesión de laboratorio**.

- `bin` : Carpeta donde estarán los ficheros compilados, que tienen extensión `.class` y contienen los *bytecode*s interpretables por la máquina virtual de Java. **No es necesario guardar esta carpeta dado que se puede generar a partir del código fuente**. Por defecto, esta carpeta está oculta en Eclipse, aunque puedes verificar su contenido a través del explorador de archivos de tu Sistema Operativo.

> Aunque es un poco más avanzado, si te animas, puedes utilizar algún sistema de control de versiones, como Git, para alojar tu código y de paso facilitar la coordinación con tu compañero/a de prácticas (Eclipse tiene soporte integrado para Git). Si utilizas un servicio web como [GitHub](https://github.com/), [GitLab](https://about.gitlab.com/) o [BitBucket](https://bitbucket.org/),  **recuerda crear un repositorio de manera privada** para que nadie pueda copiar la práctica: en los repositorios públicos el código es visible a todo el mundo. Por otro lado, está completamente **desaconsejado hacer un *fork* del repositorio oficial que contiene el enunciado y código base de las prácticas** (para evitar hacer *pull requests* por error hacia el mismo).

A continuación trasladamos el ejemplo anterior a la plataforma de trabajo Eclipse.

### Paso 1:

Ejecutar `Eclipse.exe`.

### Paso 2:

Crear un nuevo workspace. Si ya está abierto Eclipse, cambiar al workspace deseado desde el menú *File* -> *Switch Workspace* de Eclipse.

![image](img/23_24_im2.png)

![image](img/23_24_im4.png)

### Paso 3:

Crear un proyecto: *File* -> *New* -> *Java Project*. Recuerda que cada práctica será un proyecto nuevo. Asegúrate de que el entorno de ejecución seleccionado es JavaSE-21. Por otro lado, en la última sección *Module*, **desmarca la opción *Create module-info.java file*** en caso de que aparezca marcada. 

![image](img/24_25_eclipse_circle.png)

### Paso 4:

La creación de un proyecto requiere indicar las carpetas **src** y  **bin**. Puedes mantener los valores por defecto que deja Eclipse para los mismos.

![image](img/23_24_im6.png)

### Paso 5:

Una vez tenemos nuestro proyecto configurado, vamos a realizar nuestro primer programa en Eclipse. Para ello, primero tendrás que crear una clase llamada "HelloWorld": desde el menú *File* -> *new Class*.

![image](img/23_24_im8.png)

### Paso 6:

Se puede ver que Eclipse habrá almacenado el fichero `HelloWorld.java` en la ruta esperada, `C:\hlocal\TP\Pr0\src\HelloWorld.java`.

![image](img/23_24_im88.png)

### Paso 7:

Escribe el código de la clase "HelloWorld".

![image](img/23_24_im9.png)

### Paso 8:

Para ejecutar la aplicación, Eclipse ofrece distintas formas. Una de ellas es:

-   Seleccionar la clase `HelloWorld.java` en la pestaña *Package Explorer* (situado a la izquierda).
-   Pulsar el botón derecho.
-   Seleccionar *Run As* -> *Java Application*.

![image](img/23_24_im10.png)

Otra alternativa es pulsar el icono verde de "Run" después de seleccionar la clase `HelloWorld.java` en la pestaña *Package Explorer*.

![image](img/23_24_im99.png)

### Paso 9:

Eclipse ha compilado nuestro fichero de código fuente y el resultado de esa compilación ha sido un fichero con el mismo nombre y extensión `.class`. Podemos ver que en la carpeta `C:\hlocal\TP\Pr0\bin\` tenemos el fichero `HelloWorld.class`.

![image](img/23_24_im12.png)

## Tercera parte: método nuevo de la clase

En Eclipse las clases se pueden organizar en paquetes (*packages*). Para crear un paquete es necesario seleccionar la carpeta *src* usando el botón derecho en la pestaña *Package Explorer* y posteriormente seleccionar *New* -> *package*.

![image](img/23_24_im13.png)

Crea el paquete `tp.pr0`.

![image](img/23_24_im13m.png)

Crea la clase `Pr0Main` dentro del paquete `tp.pr0`.

![image](img/23_24_im13m2.png)

En dicha clase, además de tener un método `main` para que sea ejecutable, vamos a añadir un método estático, similar a las funciones procedurales, al que poder llamar desde el método principal. Al ser un método estático no es necesario que lo llame un objeto instanciado, sino que se califica con el nombre de la clase.

``` Java
package tp.pr0;

public class Pr0Main {

   public static void writeGreeting(String name) {
      System.out.println("Hello, " + name);
   }

   public static void main(String args[]) {
      Pr0Main.writeGreeting("Bender Bending Rodríguez");
   }
}
```

**Notas:**

- Como convenio, los nombres de los datos y métodos en una clase se escriben en minúsculas. Solo las clases e interfaces van con mayúsculas.
- Todas las instrucciones se terminan en \";\".
- Observa las carpetas que Eclipse crea en el directorio `src` para alojar el código fuente de las clases pertenecientes al nuevo paquete, así como la ubicación de `Pr0Main.java` y `Pr0Main.class`.

## Cuarta parte: clase matemática
En esta parte haremos una clase nueva con algunas funciones matemáticas simples, que utilizaremos desde el método `main` para escribir una lista de números combinatorios.

Se debe crear la clase `MathsFunctions` en el paquete `tp.pr0`. Contendrá dos métodos estáticos adicionales:

- `public static int factorial (int n)`

- `public static int combinatorial (int n, int k)`

Ambos métodos están descritos en el siguiente documento generado con el comando `javadoc`:

![image](img/23_24_pr0doc.png)

Teniendo en cuenta que, como se indica en la documentación de la clase:

* ${n \choose k} = \frac{n!}{k!(n-k)!}$
*   El factorial de 0 es 1, y si nos preguntan por el factorial de un número negativo, devolveremos un 0.
*   En el caso de los números combinatorios el cálculo solo tiene sentido si se cumple que 0 <= k <= n. Es decir:
    * Si k < 0 o n < 0: devolveremos -1
    * Si k > n: devolveremos 0
    * Si todas las condiciones se cumplen, aplicaremos la fórmula anterior

Una vez realizado, podemos probarlo con el código siguiente en el método `main` (comentando o eliminando la línea anterior):

``` Java
      //Pr0Main.writeGreeting("Bender Bending Rodríguez");
	  for (int i = 0; i < 6; ++i) {
		  for (int j = 0; j <= i; ++j) {
			  System.out.print(MathsFunctions.combinatorial(i,j) + " ");
		  }
		  System.out.println();
	 }
```

Cuya salida debería ser:
``` Java
1 
1 1 
1 2 1 
1 3 3 1 
1 4 6 4 1 
1 5 10 10 5 1 
```

## Quinta parte: prueba sencilla con traza del programa

A continuación vamos a realizar una prueba sencilla del programa anterior. Aunque en este caso es obvio si la salida es correcta o no, aprender este proceso te será útil para trabajar con las pruebas de las futuras prácticas.

Para realizar esta prueba vamos a configurar Eclipse para que vuelque la salida a un fichero, en lugar de mostrarlo por consola.

Lo primero que haremos es crear un fichero[^4] llamado `combinatorial_expected_output.txt` pulsando el botón derecho sobre el paquete `tp.pr0` *New* -> *File*. En dicho fichero, añadiremos la salida esperada:

``` Java
1 
1 1 
1 2 1 
1 3 3 1 
1 4 6 4 1 
1 5 10 10 5 1 

```
  
Una vez creado el fichero con la salida esperada, vamos a volcar la salida de nuestro propio programa en un fichero. Para ello debes cambiar algunos parámetros de la gestión de ejecución: botón derecho sobre `Pr0Main.java` *Run as* -> *Run Configurations...*. Aquí encontrarás una pestaña llamada `Commons` que tendrás que configurar tal y como se muestra en la siguiente figura:

![Configuración Commons](img/23_24_testing01.png)

Hay multitud de programas gratuitos para comparar visualmente ficheros, por ejemplo Eclipse ya tiene integrada una herramienta para comparar archivos que puedes lanzar al seleccionar dos archivos, pulsar con el botón derecho y en el menú emergente seleccionar `Compare With > Each other`.

![Cómo comparar dos archivos en Eclipse](img/23_24_testing02.png)

Aparecerá una nueva ventana para indicar las diferencias entre los archivos. Si la salida es la esperada, el resultado será como el siguiente:

![Salida correcta de la herramienta de comparación de archivos de Eclipse](img/23_24_testing03.png)

Si la salida no coincidiera, Eclipse lo remarcará de la siguiente forma (en este ejemplo  se descomentó a propósito la línea del método desarrollado en el apartado anterior):

![Salida incorrecta de la herramienta de comparación de archivos de Eclipse](img/23_24_testing04.png)


## Sexta parte: entrega de la práctica
Una vez que la práctica está implementada llega el momento de la entrega. Para entregar la práctica se utilizará el mecanismo de entregas del campus virtual. La fecha límite concreta de tu grupo estará disponible en el mismo.

Para entregar la práctica se debe comprimir la solución en un fichero `.zip` cuyo nombre será `Practica0.zip`. El fichero deberá contener únicamente:

- Un archivo `alumnos.txt` con el nombre de los miembros del grupo.

- El directorio `src` con el código fuente de la práctica.

![image](img/23_24_entrega_01.png)

Puedes crear un archivo `.zip` "desde cero" o utilizar la opción *File* -> *Export* -> *General*-> *Archive File* para generar un archivo .zip y seleccionar los directorios y ficheros que quieres incluir en el fichero. `.zip`.

![image](img/23_24_entrega_02.png)

[^1]: Todas las prácticas de la asignatura podrán realizarse en cualquier plataforma en la que pueda ejecutarse Eclipse; en esta descripción asumiremos que se está utilizando Windows.

[^2]: Observar que *no* se debe poner la extensión, `.class`.

[^3]: Es muy desaconsejable el uso de las memorias USB como workspace ya que la vida útil de las mismas se reduce drásticamente por la cantidad de operaciones que se hacen sobre ellas. <!-- Por otro lado, el uso de la unidad virtual de cada uno como workspace es desaconsejable por la velocidad del mismo y la cantidad de ficheros intermedios, no necesarios, que pueden llegar a generarse. -->

[^4]: En futuras prácticas se te proporcionarán ficheros de prueba tanto para la entrada como para la salida esperada.

## Apéndice 1: Configuración de un JRE alternativo en el workspace de Eclipse

En caso de que quieras configurar Eclipse para usar un JDK espec ífico, tendrás que instalar dicho JDK y especificarle a Eclipse que quieres usarlo.
Para hacer esto último, tienes que modificar las
preferencias de tu *workspace*. Para modificar las preferencias selecciona *Window* -> *Preferences*. Puedes teclear "JRE" en el buscador o navegar hasta llegar a la opción *Java* -> *Installed JREs*. Una vez allí pulsa en el botón *Add...*

![image](img/JREworkspace01.png)

En la siguiente pantalla asegúrate que está seleccionada la opción "Standard VM" y pulsa en el botón *Next...*

![image](img/JREworkspace02.png)

En la nueva ventana pulsa en el botón *Directory...* y selecciona el directorio donde has instalado / descomprimido la instalación de Java que deseas configurar.

![image](img/JREworkspace03.png)

Si has seleccionado correctamente el directorio, podrás ver que Eclipse rellena automáticamente algunos de los apartados de la ventana. Si es así, pulsa simplemente *Finish*.

![image](img/JREworkspace04.png)

Una vez que has añadido tu nueva instalación de Java, es recomendable que la selecciones como opción por defecto para no tener que configurar cada nuevo proyecto que crees dentro del *workspace*.

![image](img/JREworkspace05.png)
