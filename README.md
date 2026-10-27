# Tres en Raya

## Descripción

Tres en Raya es una aplicación de escritorio desarrollada en Java que permite jugar al clásico juego del tres en raya mediante una interfaz gráfica.

El juego ofrece dos modalidades: jugador contra jugador, para jugar entre dos personas en el mismo equipo, y jugador contra inteligencia artificial, con tres niveles de dificultad. También permite configurar los nombres de los jugadores, consultar partidas anteriores y visualizar los movimientos de partidas finalizadas.

El proyecto forma parte de mi aprendizaje en el ciclo de Desarrollo de Aplicaciones Multiplataforma (DAM), donde pongo en práctica conocimientos de programación orientada a objetos, interfaces gráficas con Java Swing, inteligencia artificial básica, persistencia de datos y pruebas de software.

## Tecnologías utilizadas

- **Java 17:** desarrollo de la lógica y la estructura de la aplicación.
- **Java Swing:** creación de la interfaz gráfica.
- **Maven:** gestión del proyecto, compilación y dependencias.
- **JUnit 5:** desarrollo y ejecución de pruebas.
- **Git y GitHub:** control de versiones y alojamiento del código.

## Funcionalidades

- Modo de juego entre dos jugadores en el mismo equipo.
- Modo de juego contra la inteligencia artificial.
- Tres niveles de dificultad para la IA: Fácil, Medio y Difícil.
- Configuración de los nombres de los jugadores.
- Interfaz gráfica con tablero de 3 × 3.
- Navegación por el tablero mediante ratón o teclado.
- Movimiento de selección mediante las flechas del teclado.
- Realización de movimientos con la barra espaciadora.
- Gestión de turnos y movimientos durante las partidas.
- Detección de resultados y almacenamiento automático de las partidas finalizadas.
- Consulta del historial de partidas guardadas.
- Visualización del tablero final y de los movimientos de una partida anterior.
- Persistencia del historial entre ejecuciones.
- Pruebas automatizadas y pruebas de interacción con la interfaz.

## Estructura del proyecto

```text
tres-en-raya/
├── pom.xml
├── historial.txt
├── README.md
├── RA1.md
├── boceto-zonas.md
└── src/
    ├── main/
    │   ├── java/
    │   │   └── com/
    │   │       └── tresenraya/
    │   │           ├── App.java
    │   │           ├── configuracion/
    │   │           │   └── Configuracion.java
    │   │           ├── ia/
    │   │           │   ├── IaDificil.java
    │   │           │   ├── IaFacil.java
    │   │           │   ├── IaMedia.java
    │   │           │   ├── IaUtilidades.java
    │   │           │   └── InteligenciaArtificial.java
    │   │           ├── interfaz/
    │   │           │   ├── VentanaConfiguracion.java
    │   │           │   ├── VentanaDificultad.java
    │   │           │   ├── VentanaHistorial.java
    │   │           │   ├── VentanaInicio.java
    │   │           │   ├── VentanaJuego.java
    │   │           │   ├── VentanaModoJuego.java
    │   │           │   ├── VentanaPartidaCargada.java
    │   │           │   └── componentes/
    │   │           │       ├── PanelInformacion.java
    │   │           │       └── PanelTablero.java
    │   │           ├── modelo/
    │   │           │   ├── Dificultad.java
    │   │           │   ├── Jugador.java
    │   │           │   ├── ModoJuego.java
    │   │           │   ├── Movimiento.java
    │   │           │   └── Partida.java
    │   │           ├── persistencia/
    │   │           │   ├── Historial.java
    │   │           │   ├── HistorialConsola.java
    │   │           │   ├── HistorialFichero.java
    │   │           │   ├── PartidaGuardada.java
    │   │           │   └── ResultadoPartida.java
    │   │           └── util/
    │   │               └── Constantes.java
    │   └── resources/
    └── test/
        └── java/
            └── com/
                └── tresenraya/
                    ├── configuracion/
                    ├── ia/
                    ├── interfaz/
                    │   └── componentes/
                    ├── modelo/
                    └── persistencia/
```

*El árbol muestra los principales archivos y paquetes del proyecto. Las carpetas de pruebas contienen clases de test adicionales.*

## Organización del código

- **App.java:** punto de entrada de la aplicación. Inicia la interfaz gráfica mediante `SwingUtilities`.
- **configuracion/:** gestiona la configuración de los jugadores.
- **ia/:** contiene la lógica de inteligencia artificial y los niveles de dificultad.
- **interfaz/:** reúne las ventanas de inicio, juego, configuración, selección de modo, dificultad e historial.
- **interfaz/componentes/:** contiene componentes gráficos reutilizables, como el tablero y el panel de información.
- **modelo/:** representa los elementos principales del juego, como jugadores, partidas, movimientos, modos y dificultades.
- **persistencia/:** gestiona el historial, los resultados y las partidas guardadas.
- **util/:** contiene constantes utilizadas por la aplicación.
- **src/test/:** contiene las pruebas para comprobar el comportamiento de los distintos componentes.
- **pom.xml:** define la configuración de Maven y las dependencias del proyecto.
- **historial.txt:** almacena los resultados y movimientos de las partidas finalizadas.

## Instalación y ejecución

### Requisitos

- Java JDK 17 o superior.
- Maven instalado y configurado, o un IDE compatible con proyectos Maven.
- Un sistema operativo compatible con Java Swing.

### 1. Clonar el repositorio

Abre una terminal y ejecuta:

```bash
git clone https://github.com/brando046/tres-en-raya.git
cd tres-en-raya
```

### 2. Compilar el proyecto

Desde la carpeta que contiene el archivo `pom.xml`, ejecuta:

```bash
mvn clean compile
```

### 3. Ejecutar la aplicación

Una vez compilado el proyecto, ejecuta:

```bash
java -cp target/classes com.tresenraya.App
```

También puedes importar el proyecto en IntelliJ IDEA, Eclipse o Visual Studio Code con soporte para Java y Maven, y ejecutar la clase `App.java`.

### 4. Generar el paquete del proyecto

Para compilar, ejecutar las pruebas y empaquetar el proyecto, utiliza:

```bash
mvn clean package
```

Maven generará los archivos correspondientes en la carpeta `target`.

## Pruebas

El proyecto incorpora pruebas en `src/test/java` para comprobar diferentes partes de la aplicación.

Para ejecutar las pruebas, utiliza:

```bash
mvn clean test
```

Las pruebas cubren aspectos como la configuración, la lógica de la inteligencia artificial, el modelo de juego, la persistencia del historial, la navegación por teclado y distintos comportamientos de la interfaz gráfica.

## Persistencia del historial

Las partidas finalizadas se guardan automáticamente en el archivo `historial.txt`, ubicado en la carpeta de ejecución.

El historial conserva los resultados y los movimientos de cada partida para poder consultarlos posteriormente desde la opción **Cargar partida**. Desde esa sección se puede seleccionar una partida guardada y visualizar su tablero final en modo de solo lectura.

El archivo de historial se crea automáticamente si no existe. Si se elimina, se perderán los registros almacenados en él.

## Repositorio

El código fuente y los archivos del proyecto están disponibles en GitHub:

**[Tres en Raya — GitHub](https://github.com/brando046/tres-en-raya)**

## Autor

**Brandon Castrillón**

Estudiante de Desarrollo de Aplicaciones Multiplataforma (DAM).

- **Portfolio:** [Portfolio personal](https://brando046.github.io/Portfolio-Brandon/)
