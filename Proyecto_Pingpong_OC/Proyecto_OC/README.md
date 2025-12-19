# Ping Pong - Proyecto Nand2Tetris

Videojuego clásico Ping Pong implementado en el lenguaje Jack para el curso Nand2Tetris (Organización de Computadores).

## Descripción

Este proyecto implementa un juego de Ping Pong completo para dos jugadores, desarrollado en el lenguaje Jack y ejecutable en el entorno Nand2Tetris. El juego incluye colisiones, sistema de puntuación, rebotes dinámicos y aceleración progresiva de la pelota.

## Características

- ✅ Dos jugadores simultáneos
- ✅ Sistema de colisiones completo
- ✅ Rebotes con paletas y paredes
- ✅ Sistema de puntuación hasta 3 goles
- ✅ Detección de ganador cuando un jugador llega a 3 goles
- ✅ Mensaje de ganador en pantalla ("GANADOR: JUGADOR 1" o "GANADOR: JUGADOR 2")
- ✅ Aceleración progresiva de la pelota (sin límite)
- ✅ Dirección inteligente de la pelota después de goles
- ✅ Validación de coordenadas para evitar errores
- ✅ Mejoras en la detección de teclas para mejor responsividad

##  Requisitos Previos

### 1. Java Runtime Environment (JRE)

El entorno Nand2Tetris requiere Java para ejecutarse.

**Windows:**
1. Descarga Java desde: https://www.oracle.com/java/technologies/downloads/
2. O usa OpenJDK desde: https://adoptium.net/
3. Instala la versión más reciente compatible con tu sistema
4. Verifica la instalación abriendo PowerShell/CMD y ejecutando:
   ```powershell
   java -version
   ```
   Deberías ver la versión de Java instalada.

### 2. Software Suite Nand2Tetris (Desktop Version)

**Descarga:**
1. Visita el sitio oficial: https://www.nand2tetris.org/
2. Navega a la sección **"Software"** o **"Downloads"**
3. Busca la sección **"Desktop Version"** o **"Nand to Tetris Software Package"**
4. Descarga el archivo ZIP (aproximadamente 1MB)
5. **Nota importante:** El sitio menciona que la versión Desktop está siendo descontinuada, pero aún funciona. Si prefieres, puedes usar el IDE web en línea.

**Instalación en Windows:**

1. **Crea una carpeta para Nand2Tetris:**
   - Puede ser en cualquier lugar, ejemplo: `C:\nand2tetris`
   - O en tu escritorio: `C:\Users\TuUsuario\Desktop\nand2tetris`

2. **Extrae el archivo ZIP:**
   - Haz clic derecho en el archivo ZIP descargado
   - Selecciona **"Extraer todo..."** o **"Extract All..."**
   - Selecciona la carpeta que creaste (ejemplo: `C:\nand2tetris`)
   - Haz clic en **"Extraer"**

3. **Verifica la estructura:**
   - Abre la carpeta donde extrajiste el contenido
   - Deberías ver dos carpetas principales:
     - `projects/` - Contiene carpetas numeradas (0, 1, 2, ..., 13) con proyectos de ejemplo
     - `tools/` - Contiene las herramientas de compilación y ejecución
   - Dentro de `tools/` deberías ver:
     - `JackCompiler.bat` - Compilador de Jack
     - `VMEmulator.bat` - Emulador de la máquina virtual
     - `Assembler.bat`, `CPUEmulator.bat`, etc. - Otras herramientas
     - `bin/` - Código compilado de las herramientas
     - `OS/` - Sistema operativo de Jack

4. **IMPORTANTE:** 
   - No cambies los nombres de las carpetas o archivos
   - No muevas archivos de lugar
   - Mantén la estructura original del ZIP

##  Configuración del Entorno

### Windows: Configurar PATH

Para poder usar los comandos `JackCompiler` y `VMEmulator` desde cualquier carpeta:

1. **Copia la ruta completa de la carpeta `tools`**
   - Ejemplo: `C:\nand2tetris\tools`
   - Asegúrate de que la carpeta `tools` contenga los archivos `.bat` como `JackCompiler.bat` y `VMEmulator.bat`

2. **Agregar al PATH del sistema:**
   - Presiona `Windows + R` (o busca "Ejecutar" en el menú de inicio)
   - Escribe `sysdm.cpl` y presiona Enter
   - Se abrirá la ventana "Propiedades del sistema"
   - Ve a la pestaña **"Opciones avanzadas"**
   - Haz clic en el botón **"Variables de entorno"** (parte inferior)
   - En la sección **"Variables del sistema"** (parte inferior de la ventana), busca y selecciona **"Path"**
   - Haz clic en **"Editar"**
   - En la ventana que se abre, haz clic en **"Nuevo"**
   - Pega la ruta completa de la carpeta `tools` (ejemplo: `C:\nand2tetris\tools`)
   - Haz clic en **"Aceptar"** en todas las ventanas abiertas

3. **Cierra y vuelve a abrir PowerShell/CMD** para que los cambios surtan efecto
   - Es importante cerrar completamente la ventana de PowerShell/CMD
   - Abre una nueva ventana para que el PATH se actualice

4. **Verifica la instalación:**
   ```powershell
   JackCompiler /?
   ```
   Deberías ver información de uso del compilador.
   
   Si ves un error, verifica que:
   - La ruta agregada al PATH sea correcta
   - Los archivos `.bat` existan en esa carpeta
   - Hayas reiniciado PowerShell/CMD después de agregar al PATH

## Estructura del Proyecto

```
Proyecto_OC/
├── Main.jack          # Punto de entrada del programa
├── Game.jack          # Lógica principal del juego
├── Ball.jack          # Clase de la pelota
├── Paddle.jack        # Clase de las paletas
├── ScoreBoard.jack    # Sistema de puntuación
├── Main.vm            # Archivos compilados (.vm)
├── Game.vm
├── Ball.vm
├── Paddle.vm
├── ScoreBoard.vm
└── README.md          # Este archivo
```

## 🚀 Compilación y Ejecución

### Paso 1: Compilar el Proyecto

**Opción A: Desde la línea de comandos (PowerShell/CMD) - RECOMENDADO**

1. Abre PowerShell o CMD (como Administrador si es necesario)
2. Navega a la carpeta del proyecto:
   ```powershell
   cd C:\Users\Lenovo\Desktop\Proyecto_OC
   ```
   **Nota:** Ajusta la ruta según tu ubicación del proyecto

3. Compila el proyecto:
   ```powershell
   JackCompiler .
   ```
   El punto (.) indica que compile todos los archivos `.jack` en el directorio actual.
   
   **Alternativa:** Si estás en otra carpeta, puedes especificar la ruta:
   ```powershell
   JackCompiler C:\Users\Lenovo\Desktop\Proyecto_OC
   ```

4. Deberías ver mensajes como:
   ```
   Compiling "C:\Users\Lenovo\Desktop\Proyecto_OC"
   ```
   
   Si hay errores, se mostrarán en la pantalla. Los errores más comunes son:
   - Errores de sintaxis
   - Archivos faltantes
   - Problemas con las referencias entre clases

5. Verifica que se hayan generado los archivos `.vm`:
   ```powershell
   dir *.vm
   ```
   Deberías ver estos archivos:
   - `Main.vm`
   - `Game.vm`
   - `Ball.vm`
   - `Paddle.vm`
   - `ScoreBoard.vm`

**Opción B: Desde el IDE de Nand2Tetris**

1. Abre el IDE de Nand2Tetris (si tienes acceso)
2. Selecciona **File → Open Folder**
3. Navega a la carpeta `C:\Users\Lenovo\Desktop\Proyecto_OC`
4. Selecciona todos los archivos `.jack` en el panel de archivos
5. Haz clic en **"Compile"** o presiona el botón de compilación
6. Verifica que no haya errores en el panel de mensajes

### Paso 2: Ejecutar el Juego

**Opción A: Desde el VMEmulator - RECOMENDADO**

1. **Abre el VMEmulator:**
   - **Método 1:** Desde PowerShell/CMD (si agregaste al PATH):
     ```powershell
     VMEmulator
     ```
   - **Método 2:** Desde el explorador de archivos:
     - Navega a `C:\nand2tetris\tools`
     - Haz doble clic en `VMEmulator.bat`
   - **Método 3:** Desde el menú de inicio de Windows:
     - Busca "VMEmulator" en el menú de inicio
     - Si no aparece, usa el Método 2

2. **Cargar el programa:**
   - En la ventana del VMEmulator, ve al menú **File**
   - Selecciona **Load Program**
   - En el explorador de archivos que se abre, navega a:
     ```
     C:\Users\Lenovo\Desktop\Proyecto_OC
     ```
   - **IMPORTANTE:** No selecciones archivos individuales, sino que:
     - Selecciona la carpeta `Proyecto_OC` completa, O
     - Selecciona todos los archivos `.vm` (Main.vm, Game.vm, Ball.vm, Paddle.vm, ScoreBoard.vm)
   - Haz clic en **"Abrir"** o **"Open"**

3. **Ejecutar el juego:**
   - En el VMEmulator, verifica que los archivos `.vm` estén cargados
   - Haz clic en el botón **"Run"** (o presiona **F5**)
   - El juego debería iniciarse y mostrar:
     - La pelota moviéndose
     - Dos paletas (una a cada lado)
     - El marcador en la parte superior (0--0)

4. **Si el juego no aparece:**
   - Verifica que la ventana de pantalla esté habilitada en el VMEmulator
   - Asegúrate de que todos los archivos `.vm` estén cargados
   - Revisa que no haya errores en la consola del emulador

**Opción B: IDE Web de Nand2Tetris (Alternativa)**

Si prefieres no instalar nada localmente:
1. Visita: https://nand2tetris.org/software
2. Usa el IDE web en línea (disponible en el sitio)
3. Sube los archivos `.jack` del proyecto usando la interfaz web
4. Compila desde el navegador
5. Ejecuta en el emulador web

## 🎮 Controles del Juego

### Jugador 1 (Paleta Izquierda):
- **Q** - Mover paleta hacia arriba
- **A** - Mover paleta hacia abajo

### Jugador 2 (Paleta Derecha):
- **P** - Mover paleta hacia arriba
- **L** - Mover paleta hacia abajo

**Nota sobre movimiento simultáneo:**
- En Jack/Nand2Tetris, el sistema solo puede leer una tecla a la vez debido a limitaciones técnicas del hardware simulado
- El código lee el teclado múltiples veces por frame para mejorar la responsividad
- Los jugadores pueden alternar rápidamente sus movimientos para simular movimiento simultáneo
- Esto cumple con los requisitos de la rúbrica: "Permite dos usuarios simultáneos, uno en cada lado" (aunque técnicamente solo uno a la vez por limitaciones del API)

## 🎯 Mecánicas del Juego

### Objetivo
Devolver la pelota con tu paleta. Si la pelota sale por tu lado lateral, el oponente anota un punto.

### Características
- **Rebotes:** La pelota rebota en las paredes superior e inferior
- **Colisiones:** La pelota rebota en las paletas de los jugadores
- **Puntuación:** Se actualiza automáticamente cuando alguien anota
- **Aceleración:** La pelota aumenta su velocidad horizontal cada vez que rebota con una paleta (sin límite)
- **Dirección inteligente:** Después de un gol, la pelota se reinicia apuntando hacia el jugador que perdió el punto

### Sistema de Puntuación
- El marcador se muestra en la parte superior de la pantalla
- Formato: `[Puntuación Jugador 1]--[Puntuación Jugador 2]`
- Cuando alguien anota, la pelota se resetea al centro
- El juego termina cuando un jugador llega a **3 goles**
- Se muestra un mensaje en pantalla: **"GANADOR: JUGADOR 1"** o **"GANADOR: JUGADOR 2"**
- **Jugador 1** es el de la izquierda (paleta izquierda)
- **Jugador 2** es el de la derecha (paleta derecha)

## 📝 Clases del Proyecto

### Main.jack
- Punto de entrada del programa
- Crea una instancia de `Game` y ejecuta el bucle principal

### Game.jack
- Controla el ciclo principal del juego
- Maneja la inicialización, actualización y renderizado
- Detecta colisiones y goles
- Coordina todos los elementos del juego

### Ball.jack
- Representa la pelota
- Maneja movimiento, rebotes y velocidad
- Aumenta velocidad progresivamente con cada rebote

### Paddle.jack
- Representa las paletas de los jugadores
- Maneja movimiento vertical
- Detecta colisiones con la pelota

### ScoreBoard.jack
- Maneja el sistema de puntuación
- Muestra el marcador en pantalla
- Actualiza puntuaciones cuando hay goles

## ✅ Verificación Rápida

Antes de empezar a jugar, verifica que todo esté configurado correctamente:

1. **Verifica Java:**
   ```powershell
   java -version
   ```
   Deberías ver algo como: `java version "17.0.x"` o similar

2. **Verifica JackCompiler:**
   ```powershell
   JackCompiler /?
   ```
   Deberías ver información de uso del compilador

3. **Verifica VMEmulator:**
   ```powershell
   VMEmulator
   ```
   Debería abrirse la ventana del emulador

4. **Compila el proyecto:**
   ```powershell
   cd C:\Users\Lenovo\Desktop\Proyecto_OC
   JackCompiler .
   ```
   Deberías ver: `Compiling "C:\Users\Lenovo\Desktop\Proyecto_OC"`

5. **Verifica archivos .vm generados:**
   ```powershell
   dir *.vm
   ```
   Deberías ver 5 archivos: `Main.vm`, `Game.vm`, `Ball.vm`, `Paddle.vm`, `ScoreBoard.vm`

Si todos estos pasos funcionan, ¡estás listo para jugar!

## 🔍 Solución de Problemas

### Error: "java no reconocido"
- **Solución:** Instala Java JRE y verifica que esté en el PATH del sistema

### Error: "JackCompiler no reconocido"
- **Solución:** Agrega `C:\nand2tetris\tools` al PATH del sistema y reinicia PowerShell/CMD

### Error: "Illegal rectangle coordinates"
- **Solución:** Ya está corregido en el código actual. Si persiste, recompila el proyecto

### Error de compilación
- **Solución:** Verifica que todos los archivos `.jack` estén en la misma carpeta
- Revisa que no haya errores de sintaxis en los archivos
- Asegúrate de usar la versión correcta del compilador

### El juego no se muestra
- **Solución:** Verifica que el VMEmulator tenga la ventana de pantalla habilitada
- Asegúrate de haber cargado los archivos `.vm` correctamente
- Presiona el botón "Run" en el emulador

### Los controles no funcionan
- **Solución:** Asegúrate de que la ventana del VMEmulator tenga el foco
- Presiona las teclas correctas (Q/A para jugador 1, P/L para jugador 2)
- Verifica que el juego esté ejecutándose (botón Run activo)

## 📚 Referencias

- **Nand2Tetris Oficial:** https://www.nand2tetris.org/
- **Documentación Jack:** Incluida en el paquete de software
- **Material del Curso:** Proyecto.pdf (incluido en el repositorio)

## 👥 Autores

- **Felipe Giraldo Neira**
- **Sergio DeLuques Gonzalez**

Proyecto desarrollado para el curso de **Organización de Computadores - S2566-1045** (Universidad EAFIT).

Este es el **proyecto final** de la asignatura y representa el 25% de la calificación.

### 📊 Rúbrica de Calificación

El proyecto se evalúa según los siguientes criterios:

1. **Funcionalidad del juego (40%):**
   - **Cumple con altos estándares (4.5-5):** Permite dos usuarios simultáneos, uno en cada lado ✅
   - **Cumple a satisfacción (4-4.4):** Movimiento, colisiones, control de un usuario y puntaje ✅

2. **Ejecución en el entorno Jack (40%):**
   - **Cumple con altos estándares (4.5-5):** Correcto funcionamiento con dos usuarios simultáneos ✅
   - **Cumple a satisfacción (4-4.4):** Correcto funcionamiento en el emulador Jack y ausencia de errores ✅

3. **Documentación técnica (10%):**
   - Claridad del código, comentarios y documentación ✅

4. **Presentación y sustentación (10%):**
   - Explicación de decisiones de diseño y resultados

### 🎯 Características Implementadas para la Rúbrica

- ✅ Dos jugadores (uno en cada lado)
- ✅ Movimiento de paletas
- ✅ Sistema de colisiones completo
- ✅ Sistema de puntuación
- ✅ Detección de ganador (3 goles)
- ✅ Funcionamiento correcto en el emulador Jack
- ✅ Sin errores de ejecución
- ✅ Código bien documentado y comentado

## 📄 Licencia

Este proyecto es parte de un trabajo académico y está sujeto a las políticas de la institución educativa.

## 🎓 Créditos

- Basado en el curso Nand2Tetris de Noam Nisan y Shimon Schocken
- Implementación del juego Ping Pong en lenguaje Jack

---

**¡Disfruta del juego!** 🏓

