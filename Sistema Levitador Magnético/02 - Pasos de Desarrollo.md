Para estructurar el trabajo de forma ordenada y cumplir con todos los puntos exigidos, lo ideal es seguir el mismo flujo que propone la guía, adaptado específicamente a las necesidades del Maglev.

Aquí tienes un plan de acción paso a paso para arrancar:

### Paso 1: Definición del problema  

* Empieza por describir el principio de funcionamiento del sistema.  
* Haz una lista para determinar las variables del sistema con sus correspondientes unidades de medida (por ejemplo: la masa de la esfera en $kg$, la corriente de la bobina en $A$, la posición en $m$).  
* En esta etapa es crucial identificar las no linealidades involucradas, puntualmente la ecuación de la fuerza electromagnética.  

### Paso 2: Análisis de la planta  

* Plantea las dos ecuaciones diferenciales que rigen el sistema: la de la malla eléctrica y la de la segunda Ley de Newton. Con esto logras determinar el modelo matemático de los distintos elementos componentes del sistema.  
* Aplica Series de Taylor para linealizar las ecuaciones en el punto donde quieres que flote la esfera.
* Luego de aplicar Laplace, vas a determinar la Función de transferencia a lazo abierto.  
* Realiza el análisis de estabilidad absoluta calculando las raíces del denominador (polos) para demostrar formalmente que el sistema es inestable.  

### Paso 3: Especificaciones de diseño  

* Elige qué comportamiento deseas que tenga la esfera cuando haya una perturbación. Si trabajas en el dominio del tiempo, puedes definir sobrepasamiento máximo (cuánto permites que la bola oscile hacia arriba antes de estabilizarse) y definir tiempo de establecimiento (cuántos segundos tarda en quedarse quieta).  
* Debes verificar que estas especificaciones sean realizables.  

### Paso 4: Diseño del controlador y Simulación  

* Con las especificaciones claras, puedes diseñar al menos un controlador (adelanto, atraso o ambos, PID). Dado que la planta es inestable, usar herramientas como el lugar de las raíces te ayudará a ubicar los polos en el semiplano izquierdo.  
* Pasa a simular la respuesta temporal del sistema. Si utilizas scripts propios de simulación para calcular y verificar los márgenes, subirlos a un repositorio de GitHub con un buen archivo README te facilitará organizar los archivos requeridos para la entrega.  

### Paso 5: Elaboración del Informe

* Debes elaborar un informe describiendo el proceso de diseño, utilizando el lenguaje técnico apropiado. Al momento de redactar todo el desarrollo matemático y estructurar las subfiguras en LaTeX usando VS Code, te resultará más cómodo activar el ajuste de texto (Word Wrap) directamente desde el menú "View" o la paleta de comandos, especialmente para evitar que los atajos de teclado entren en conflicto con la superposición del software de tu GPU.  
* Finalmente, compila el PDF de tu reporte. Recuerda que el archivo debe ser nombrado con la estructura `Apellido1-Apellido2.TFI.SCI Año de cursado.pdf`.  

