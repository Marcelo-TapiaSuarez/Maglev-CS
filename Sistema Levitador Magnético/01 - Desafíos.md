Es totalmente válido prescindir de la parte física; la guía establece explícitamente que la implementación del sistema no será exigida por la cátedra. Al descartar el armado en hardware, el peso del proyecto recae en el análisis teórico y la simulación por software.  

En ese escenario, sí, el modelo matemático y el diseño del controlador se convierten en las partes más desafiantes y centrales del trabajo.

Aquí te explico por qué y qué implica esa complejidad:

### 1. El Desafío del Modelo Matemático
Para determinar el modelo matemático de los distintos elementos componentes del sistema, hay que combinar dos mundos físicos:  

* **La parte eléctrica:** La ecuación de la malla del electroimán.
* **La parte mecánica:** La segunda Ley de Newton aplicada a la esfera en el aire.

Tener bases sólidas en física y electrónica facilita muchísimo plantear estos diagramas de cuerpo libre y entender el comportamiento de las fuerzas. Una vez planteadas las ecuaciones diferenciales, hay que identificar las no linealidades involucradas (la fuerza magnética no es lineal) y aplicar el Teorema de Taylor para linealizar el sistema alrededor de un punto de equilibrio.  

Al momento de redactar el informe, desarrollar todo este despiece analítico y las ecuaciones resultantes utilizando herramientas de edición de texto técnico como LaTeX garantiza un nivel de precisión y rigor que los profesores valoran muchísimo en la presentación final.

### 2. La Complejidad del Controlador
Al obtener la Función de transferencia y hacer el análisis de estabilidad absoluta, te encontrarás con que el Maglev es inestable a lazo abierto (tiene un polo positivo). 

Esto significa que no puedes sintonizar un controlador PID a prueba y error fácilmente. Tendrás que usar herramientas de diseño más analíticas, como el método de cancelación de polos dominantes o los métodos de compensación en frecuencia, para forzar a los polos a moverse hacia el semiplano izquierdo (hacer el sistema estable).  

### 3. La Simulación como Prueba Final
Dado que no vas a armar la maqueta, la simulación será tu "realidad". Deberás simular la respuesta temporal del sistema rigurosamente, demostrando cómo el controlador reacciona frente a perturbaciones. De ser posible, agregar al modelo de simulación las no linealidades detectadas en la etapa de análisis (en Simulink, por ejemplo, usando bloques matemáticos en lugar de la función de transferencia lineal) le dará un nivel sobresaliente al TFI.  

---

**En resumen:** es un proyecto matemáticamente exigente porque la planta es inestable, pero esto es precisamente lo que te permite lucirte aplicando todas las técnicas fuertes de la materia (álgebra de bloques, análisis temporal y frecuencial).  

¿Te gustaría que te pase la estructura básica de las dos ecuaciones diferenciales (la eléctrica y la mecánica) para que veas si te resulta cómodo trabajarlas?