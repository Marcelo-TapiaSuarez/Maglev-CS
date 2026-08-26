El sistema de levitación magnética (Maglev) de un grado de libertad es fascinante porque es inestable por naturaleza, lo que justifica perfectamente la necesidad de aplicar todo lo aprendido en la materia.

El funcionamiento básico consiste en un electroimán fijo en la parte superior que atrae una esfera metálica hacia arriba, contrarrestando exactamente la fuerza de la gravedad para mantenerla suspendida en el aire.

Aquí te detallo cómo se compone y cómo encaja con los requerimientos del trabajo:

## Componentes del Sistema

* **Actuador:** Es el electroimán (una bobina con un núcleo de hierro), accionado a través de un circuito de potencia (como un transistor MOSFET). Con esto defines cómo se ejecutará la acción de control.  
* **Sensor:** Generalmente se usa un par emisor-receptor infrarrojo. La esfera, al flotar, bloquea parcialmente el haz de luz. La cantidad de luz recibida se traduce en un voltaje proporcional a la posición. Así determinas cómo se va a medir la variable de salida.  
* **Planta:** Es la propia dinámica de la esfera sometida a las fuerzas.

## El Desafío Matemático (Lo que lo hace ideal para el TFI)

La fuerza magnética que atrae la bola no es lineal: aumenta cuadráticamente con la corriente de la bobina y disminuye cuadráticamente a medida que la bola se aleja. Para cumplir con el requisito de identificar las no linealidades involucradas, tendrás que plantear la ecuación diferencial usando las leyes de Newton.  

Luego, para determinar la Función de transferencia, deberás aplicar el método de linealización por Series de Taylor alrededor de un punto de operación (la distancia a la que quieres que flote la bola). Al hacer este análisis de estabilidad absoluta, descubrirás matemáticamente que el sistema a lazo abierto tiene un polo en el semiplano derecho del plano $s$. Es decir, sin un controlador, la bola siempre se caerá o se pegará al imán.  

## ¿Dónde buscar información de calidad?

* **Libros Clásicos de Control:** Este sistema es el ejemplo por excelencia en la bibliografía universitaria. Te recomiendo consultar:
  * *Ingeniería de Control Moderna* de Katsuhiko Ogata.
  * *Sistemas de Control Automático* de Benjamin C. Kuo.
  
  En ambos libros encontrarás el paso a paso del modelo matemático de los distintos elementos componentes del sistema, la linealización y ejemplos de diseño de controladores para este caso específico.  

* **Repositorios Universitarios (GitHub):** Al ser un proyecto académico popular, hay muchísimos repositorios públicos. Explorar aquí es muy valioso porque no solo encontrarás los diagramas de bloques del sistema y scripts de simulación, sino que muchos estudiantes publican el código (habitualmente estructurado en C++17 o versiones modernas si optaron por la implementación física con microcontroladores) junto con los reportes técnicos completos redactados en formato LaTeX, lo cual es excelente para tomar como referencia al momento de estructurar las ecuaciones y la maquetación de tu propio informe.  

* **Google Académico / IEEE Xplore:** Buscando términos como "Magnetic levitation ball PID control" o "Modelado y control de un levitador magnético", accederás a artículos (papers) donde otros autores ya han calculado constantes físicas típicas de las bobinas y han simulado la respuesta temporal del sistema probando diferentes configuraciones (adelanto, atraso, PID).  

---

¿Te gustaría que repasemos cómo se plantearía la sumatoria de fuerzas de Newton para empezar a armar el modelo matemático, o prefieres buscar la bibliografía primero?



# Páginas útiles


> https://www.sciencedirect.com/science/article/pii/S2211379717320065#b0105
> 
> https://www.researchgate.net/publication/383050008_Modelling_and_Control_of_a_Magnetic_Levitation_System
> 
> https://la.mathworks.com/help/control/ug/maglev-lpv-model-from-equations.html?s_tid=srchtitle_support_results_2_magnetic+levitation
> 
> https://la.mathworks.com/help/sldo/ug/magnetic-levitation-controller-tuning.html?s_tid=srchtitle_support_results_1_magnetic+levitation
> 
> https://la.mathworks.com/help/control/ug/maglev-lpv-model-from-batch-linearization.html?s_tid=srchtitle_support_results_4_magnetic+levitation