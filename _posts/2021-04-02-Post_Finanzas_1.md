---
layout: post
title:  "Financial Post #1"
date:   2021-04-02 22:00:00 -0400
tags: Financial_post
---

# ¿Qué entendemos por riesgo en las finanzas?
    
<img src="/img/post_fin/riesgo/risk-management.png" width="600" height="200">    
    
<br>
Abraham Soldevilla Cueva, Febrero 2021 
<br>

<br>
En Quantmoon Technologies buscamos aportar a la comunidad mediante la difusión de conocimiento financiero. En consecuencia, en este primer artículo decidí escribir sobre el riesgo, ya que este concepto suele malinterpretarse. 

En general, riesgo es la posibilidad de sufrir una perdida. En las finanzas, entendemos riesgo como la posibilidad de perder dinero al invertirlo, ya sea en la Bolsa, un emprendimiento o al prestarlo (a un amigo o al banco de tu preferencia). 

El riesgo financiero se divide en muchas formas, tamaños y colores, entre ellos:
<br>
- Riesgo de Mercado: la posibilidad de perder dinero debido a cambios en las condiciones del mercado, como un menor tipo de cambio para los guias en Cuzco, el aumento en la tasas de interés para un emprendedor o cuando sube el precio del limón para un cevichero, entre otros.
- Riesgo de Crédito: la posibilidad de perder dinero debido a que tu cliente no te paga lo acordado, como le paso a Mike Ross en el primer capítulo de Suits.
- Riesgo Operacional: la posibilidad de perder dinero por un error en algún proceso, ya sea humano o de sistemas. Imaginen que le pagan a un proveedor con un cheque y por error escriben un cero de más.
- Riesgo Legal: la posibilidad de perder dinero debido a una acción legal. Como le pasó a Michael Jackson por conciertos cancelados al ser demandado por abuso infantil sin poder salir de Gringolandia.

Aunque tentador, en este artículo no voy a profundizar en ninguna de estas partes del riesgo financiero, ya que quiero que exploremos el riesgo per se. Para esto, voy a apoyarme en algunos conceptos matemáticos, los cuales introduciré en la primera parte de este artículo. Luego, explicaré la diferencia conceptual entre riesgo e incertidumbre, ya que muchas veces, suelen confundirse. Finalmente, se presentarán algunas métricas de riesgo financiero.

# Parte 1: Entendiendo la aleatoriedad en las inversiones
    
Imaginemos que estamos por iniciar un negocio, digamos venta de dos Pye de Limon a 75 soles cada uno. Como somos diligentes, antes de invertir (digamos que 100 soles) hacemos un estudio de mercado para tener una idea de cuanto podríamos GANAR o PERDER (P&L, por sus siglas en ingles) en este negocio. Los resultados de este estudio son los siguientes:

$$P\&L=\begin{cases}
+50, \text{ escenario 1: vendo los dos}\\
+10, \text{ escenario 2: solo vendo uno}\\
-30, \text{ escenario 3: no vendo nada}
\label{uncertainty} \tag{1}
\end{cases}$$


<img src="/img/post_fin/riesgo/pye_limon.jpg" width="500" height="200">    


Esto quiere decir que, en un escenario favorable mi inversión tendría un retorno del 50%, en un escenario neutral, del 10% y, en un escenario desfavorable perdería 20% al rematarlos a 35 soles cada uno. 

Seguramente ya notaron que este estudio está incompleto, ya que no se indica que tan probable es la ocurrencia de cada posible escenario. Estimar la ***probabilidad*** de encontrarnos en cada escenario no es imposible, pero necesitamos información y conocimientos de estadística. 

Asumos que logramos estimar estas ***probabilidades***. En consecuencia, nuestra función de Ganancias y Perdidas (P&L) es:   

$$P\&L=
\begin{cases}
    +50, \text{ con probabilidad } p_1\\
    +10, \text{ con probabilidad } p_2\\
    -30, \text{ con probabilidad } p_3
    \label{risky} \tag{2}
\end{cases},$$

donde, $$p_1+p_2+p_3=1$$

Los matemáticos denominaron a este tipo de funciones ***Variable aleatoria discreta***, si en vez de solo tres escenarios hubiera un número incontable de posibles casos tendríamos una ***Variable aleatoria continua***. En general, toda ***Variable aleatoria*** tiene una función de distribución, la cual determina las probabilidades asociadas a cada posible resultado.

Lo que quiero dejar claro aqui es que toda inversión tiene muchos posibles resultados entre buenos y malos, donde cada resultado tiene una probabilidad de ocurrencia, las cuales están determinadas por una función de distribución.

# Parte 2: La diferencia entre el riesgo y la incertidumbre

Volviendo a lo que nos compete, cuando medimos el riesgo de una inversión utilizamos conceptos de teoría de probabilidad (como los descritos en la Parte 1), es decir necesitamos la función de distribución de nuestras Ganancias y Pérdidas.

Como se mencionó antes, con suficientes datos podemos tener una idea muy buena sobre la función de distribución. En consecuencia, nuestra inversión estaría descrita por la Ecuación \eqref{risky}. En este caso, el inversionista está asumiendo el riesgo de su inversión y puede cuantificar varios aspectos del mismo usando estadística o teoría de probabilidad. 

Sin embargo, sin los datos nos embarcaríamos en una misión a territorio inexplorado, donde no tendríamos ni idea sobre las probabilidades de exito o fracaso. En consecuencia, nuestra inversión estaría descrita por la Ecuación \eqref{uncertainty}. En este caso, el inversionista se la está jugando, ya que tiene completa incertidumbre sobre su inversión. Lo mejor que puede hacer aqui el inversionista es prepararse para el peor escenario posible, dando lugar a las famosas ***pruebas de estrés***.

Para terminar de entender la diferencia entre ambos conceptos procederé a dar ejemplos extremos.

<img src="/img/post_fin/riesgo/batman.jpg" width="800" height="200">    

Gracias al trabajo de Batman en "the Big Short" sabemos que Michael Burry estudió una gran cantidad de datos inmobiliarios para determinar la distribución de las Ganancias y Perdidas (P&L) de los CDO. De esta forma se dio cuenta que estos instrumentos financieros eran altamente riesgosos. La gracia aqui es que el mercado los consideraba instrumentos de inversión AAA, es decir tan seguros como un Bono Gringo. En este caso Michael Burry gestionó el riesgo de los CDO comprando un seguro llamado CDS, el cual te paga un porcentaje del valor del CDO, en caso este instrumento no te pague lo acordado. Paro aqui para no hacer spoilers de esta película, se las recomiendo si aún no la han visto.

<img src="/img/post_fin/riesgo/martian.jpg" width="800" height="200">   

La historia del cine de Ciencia Ficción está llena de películas sobre invasiones alienígenas, luego conocemos (casi) todos los posibles escenarios. Sin embargo, hasta donde yo se, nunca hemos sido atacados por seres de otros planetas. En ese sentido, no hay forma de saber la probabilidad de un ataque marciano o fantasmatico. En este caso la humanidad se encuentra en incertidumbre. Esto no quiere decir que los Gobiernos más belicosos del mundo no tengan algún plan de contingencia contra una posible invasión alinenigena.  

En cristiano, hablamos de riesgo cuando tenemos una idea sobre la probabilidad de ocurrencia de cada posible evento (i.e. conocemos o creemos conocer la distribución de probabilidad). Caso contrario, lideamos con incertidumbre. 

# Parte 3: Algunas métricas de riesgo

Una métrica es una función que mide la distancia entre dos puntos. En ese sentido, una métrica de riesgo mide el riesgo tomando como referencia la certeza (la métrica sería cero). En ese sentido, una métrica de riesgo muy lejos de cero implica mucho riesgo, mientras que una muy cercana a cero implica poco riesgo. Sin duda, la métrica de riesgo más famosa es la volatilidad, la cual suele medirse utilizando la desviación estandar (sd(.), por sus siglas en ingles). 

Para calcular la ***sd(P&L)*** de la ecuación \eqref{risky} se aplica la siguiente fórmula:

$$\begin{align*}
sd(P\&L)   & = \sqrt{E[(P\&L - \mu)^2]}\\
           & = \sqrt{(500\times p_1-\mu)^2 + (100 \times p_2-\mu)^2 + (-200\times p_3-\mu)^2} 
\end{align*}$$

donde,

$$\mu = 500\times p_1 + 100 \times p_2 -200\times p_3,$$ 

es el valor esperado de P&L 

En mi opinión, la sd(.) brinda una idea bastante clara del riesgo que enfrenta el proyecto evaluado (mientras más grande más riesgo) y utilizada en conjunto con $\mu$ me permite tomar decisiones. Sin embargo, no nos dice mucho sobre el riesgo que enfrentamos nosotros al invertir, ya que solo usa información del ***P&L***. 

En mi experiencia, para gestionar tus propias finanzas es mejor utilizar la covarianza (cov(), en adelante) como medida del riesgo. La idea tras esta medida es evaluar el proyecto de inversión utilizando tu propia información, por ejemplo, la distribución de una función de tu consumo esperado. De esta forma puedes medir el riesgo de tu proyecto respecto a tu propio bienestar. Para seguir utilizando nuestra ecuación \eqref{risky} asumamos que elegimos una función de nuestro consumo real al término del proyecto de inversión que sigue la siguiente distribución:

$$
X=
\begin{cases}
    X_1, \text{ con probabilidad } p_1\\
    X_2, \text{ con probabilidad } p_2\\
    X_3, \text{ con probabilidad } p_3
    \label{riskyc} \tag{3}
\end{cases},
$$
con

$$\mu_X = X_1\times p_u + X_2 \times p_n + X_3\times p_d,$$ 

es el valor esperado de X. 

Para calcular la ***cov(P&L,X)*** entre las ecuaciones \eqref{risky} y \eqref{riskyc} se aplica la siguiente fórmula:

$$\begin{align*}
cov(P\&L,X)   & = E[\,(P\&L - \mu)\,(X - \mu_X)\,]\\
           & = (500\, p_1-\mu)\,(X_1 \, p_1 - \mu_X) + (100 \, p_2-\mu)\,(X_2 \, p_2 - \mu_X) + (-200\, p_3-\mu)\,(X_3 \, p_3 - \mu_X)
\end{align*}$$

A mi me gusta usar esta metrica, porque me dice si el proyecto es bueno o malo para mi, esto es especialmente atractivo para inversionistas adversos al riesgo, como se detalla en Cochrane 2001. Por ejemplo, si X está negativamente relacionado a mi consumo futuro, es decir a mayor X menor mi consumo futuro (vacas flacas) y viceversa (vacas gordas), puedo interpretar ***cov(P&L,X)*** de la siguiente forma:

$$
cov(P\&L,X) 
\begin{cases}
    >\, 0, \text{ el proyecto me conviene}\\
    =\, 0, \text{ el proyecto no me perjudica}\\
    <\, 0, \text{ el proyecto me perjudica}
\end{cases}
$$

Por último, pero no menos importante, quiero resaltar que no hay una métrica de riesgo por excelencia, ya que se suelen elegir en función al contexto. Por ejemplo, cuando evaluamos un portafolio de proyectos de inversión, tenemos que considerar como cambiaría la métrica al agregar un elemento a nuestro portafolio. En ese sentido, en Artzner et al. (1997) proponen un conjunto de propiedades matemáticas deseables en una métrica del riesgo (denotada como ***M(.)*** en adelante), estas son:
- ***Subaditividad:*** 
$$M(P\&L_1+P\&L_2)\leq M(P\&L_1)+M(P\&L_2)$$
- ***Monotonicidad:*** 
$$\text{Si }P\&L_1\leq P\&L_2 \text{ para cada posible escenario, entonces }M(P\&L_1)\leq P\&L_2$$
- ***Homogeneidad positiva:*** 
$$\text{Para todo }a>0, \, M(a\, P\&L_1)=a\, M( P\&L_1)$$
- ***Invarianza en translaciones:*** 
$$\text{Para toda constante }C, \, M( P\&L_1+C) = M( P\&L_1)-C$$

Las métricas de riesgo que satisfacen estas propiedades son denominadas como ***metricas de riesgo coherentes***, algunos ejemplos son:
- Expected Shortfall (o Conditional Value at Risk)
- The Wang risk measure
- Superhedging price

Para concluir, recordemos que toda inversión tiene muchos posibles resultados entre buenos y malos, donde cada resultado tiene una probabilidad de ocurrencia, las cuales están determinadas por una función de distribución. Hablamos de riesgo cuando conocemos o creemos conocer la función de distribución, caso contrario, lideamos con incertidumbre. Finalmente, todas las métricas de riesgo asumen que conocemos (o creemos conocer) la distribución de probabilidad de las Ganancias y Pérdidas (P&L) de nuestra inversión. Esto no es trivial, se necesitan datos, modelos matemáticos y el software de tu preferencia para poder estudiar la distribución de tus datos y elegir algún candidato. 


# Referencias

* (Article) Artzner, Philippe & Delbaen, Freddy & Jean-Marc, Eber & Heath, David. (1999). Coherent Measures of Risk. Mathematical Finance. 9. 203 - 228.
* (Book) Cochrane, J.H. (2001). Asset Pricing. Princeton University Press. v. 1
 
