La expresión de la fuerza magnética que aparece restando en la ecuación es:

$$F_m = \alpha \frac{i(t)^2}{h(t)^2}$$

Esta fórmula proviene del principio del balance de energía y co-energía magnética almacenada en un inductor acoplado a un cuerpo ferromagnético móvil.

### 1. Energía almacenada en la bobina
La energía magnética $W_m$ almacenada en un inductor con inductancia $L(h)$ por el cual circula una corriente $i$ está dada por:

$$W_m = \frac{1}{2} L(h) \, i^2$$

### 2. Inductancia en función de la distancia ($h$)
La inductancia de la bobina no es constante; cambia según la posición de la esfera metálica. A medida que la bola de acero se acerca al electroimán ($h$ decrece), la reluctancia magnética disminuye y la inductancia total aumenta.

Experimental y analíticamente, para pequeñas distancias de entrehierro, la variación de la inductancia se modela de forma inversa a la posición:

$$L(h) = L_0 + \frac{2\alpha}{h}$$

Donde $L_0$ es la inductancia base de la bobina sin la esfera cercana y $\alpha$ (a veces llamada constante magnética $k$ o $C$) engloba parámetros geométricos: el número de vueltas al cuadrado ($N^2$), la permeabilidad magnética del medio ($\mu_0$) y el área efectiva del entrehierro.

### 3. Obtención de la fuerza magnética
En un sistema electromecánico conservativo, la fuerza magnética ejercida sobre la parte móvil se obtiene derivando la co-energía con respecto a la coordenada de desplazamiento:

$$F_m = \frac{\partial W_m}{\partial h} = \frac{1}{2} \frac{d L(h)}{dh} \, i^2$$

Al derivar la expresión de la inductancia respecto de $h$:

$$\frac{d L(h)}{dh} = \frac{d}{dh}\left(L_0 + 2\alpha h^{-1}\right) = -2\alpha h^{-2} = -\frac{2\alpha}{h^2}$$

Sustituyendo esta derivada en la ecuación de fuerza:

$$F_m = \frac{1}{2} \left(-\frac{2\alpha}{h^2}\right) i^2 = -\alpha \frac{i^2}{h^2}$$

El signo negativo indica que la fuerza es de atracción (tiende a reducir la distancia $h$).

### 4. Ecuación de movimiento de la imagen
En el diagrama, el eje vertical $h$ está definido positivo hacia abajo (la aceleración $\ddot{h}$ aumenta hacia el suelo). Por la segunda Ley de Newton:

$$\sum F = m_b \ddot{h}$$

$$m_b g - F_m = m_b \ddot{h}$$

$$m_b \ddot{h} = m_b g - \alpha \frac{i(t)^2}{h(t)^2}$$

En el equilibrio estático, la bola debe permanecer suspendida a una distancia constante $\bar{h}$ ($\ddot{h} = 0$) con una corriente constante $\bar{i}$, cumpliéndose la condición de equilibrio:

$$m_b g = \alpha \frac{\bar{i}^2}{\bar{h}^2}$$

