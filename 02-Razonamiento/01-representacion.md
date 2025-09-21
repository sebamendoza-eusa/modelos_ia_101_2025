1. Representación del conocimiento y razonamiento: introducción
===

## Qué significa “representar conocimiento”

En el ámbito de la inteligencia artificial, hablar de **representación del conocimiento** significa mucho más que acumular datos en una base. Se trata de **modelar un fragmento del mundo real** de manera que una máquina pueda **entenderlo y operar con él**. Esto implica traducir hechos, conceptos, relaciones y reglas a un **formato formal y computable** que permita al sistema **razonar**, es decir, **derivar conclusiones nuevas a partir de la información existente**.

### La clave está en la semántica

La diferencia esencial respecto al manejo de datos en bruto es la **semántica**. Mientras que los datos describen observaciones aisladas, el conocimiento incorpora **significado**: identifica entidades, establece vínculos entre ellas y fija condiciones en las que ciertos fenómenos ocurren. Es decir, cuando decimos que una representación de conocimiento incorpora **semántica**, nos referimos a que no solo guarda símbolos, palabras o números, sino también su **significado dentro de un contexto**. La semántica convierte un conjunto de datos dispersos en una **estructura comprensible y útil** para el razonamiento automático.

Por ejemplo, los siguientes datos están desprovistos de semántica

```
“38.5”, “tos”, “paciente_123”
```

Se trata de valores aislados: un número (que podría ser una temperatura), una palabra (tos) y una etiqueta de identificación.

Por contra, a continuación se presentan datos provistos de semántica

```
temperatura(paciente_123, 38.5)
síntoma(paciente_123, tos)
```

Aquí no solo tenemos los valores, sino también su **significado**: la temperatura es un atributo de un paciente, y la tos es un síntoma que él presenta. La semántica, por tanto, es la que hace posible que el sistema **entienda** las relaciones: que 38.5 corresponde a una **temperatura corporal elevada**, que “tos” no es cualquier palabra sino un **síntoma clínico**, y que ambos juntos pueden asociarse a un **estado patológico**.

En el campo de la Inteligencia Artificial, se podría afirmar que la semántica aparece en tres niveles diferenciados: **léxico, estructural y pragmático.**

El **nivel léxico** se ocupa del **significado individual de los símbolos**. Es el primer paso: asignar a cada palabra, término o etiqueta una interpretación que sea coherente con el dominio donde se aplica el sistema.

Por ejemplo, el término **“fiebre”** podría ser entendido por una máquina de muchas maneras: como una palabra sin contexto, como un nombre propio, incluso como parte de una canción. Pero en un sistema médico, el nivel léxico fija que “fiebre” es un **síntoma clínico** que indica temperatura corporal elevada.

Este nivel asegura que el sistema **entienda de qué se está hablando** cuando aparece una palabra o símbolo, evitando ambigüedades iniciales.

Por su parte, el **nivel estructural** se centra en **cómo se relacionan los elementos entre sí**. No basta con saber que existen símbolos, sino que hay que capturar sus vínculos y dependencias lógicas.

Por ejemplo, la regla:
$$
\textbf{Fiebre} \land \textbf{Tos} \rightarrow \textbf{Posible\_Gripe}
$$
establece una **dependencia lógica**: la coincidencia de fiebre y tos aumenta la probabilidad de que el paciente tenga gripe. Aquí los conceptos ya no aparecen de forma aislada, sino como partes de un **sistema de relaciones** que permiten generar conocimiento nuevo.

Así pues, el nivel estructural es clave para pasar de los datos a la **inferencia**, es decir, para deducir o inducir conclusiones que no estaban explícitas en los hechos originales.

Por último, el **nivel pragmático** se ocupa de **cómo se usa la información en contextos reales de acción**. En este nivel la semántica deja de ser un simple mapa de significados o reglas abstractas, para convertirse en una **guía práctica** que orienta decisiones.

Siguiendo el mismo ejemplo: si el sistema detecta que el paciente presenta fiebre y tos, el razonamiento pragmático se traduce en **acciones concretas**, como recomendar una prueba adicional, sugerir aislamiento domiciliario o derivar al especialista. Aquí el conocimiento ya no solo explica, sino que **decide y actúa**, cerrando el ciclo de percepción–razonamiento–acción propio de los sistemas inteligentes.

Visto lo anterior puede afirmarse que estos tres niveles se **acumulan** y se necesitan mutuamente:

- El **léxico** da significado a las palabras básicas.
- El **estructural** organiza esos conceptos en reglas y relaciones.
- El **pragmático** los pone en práctica en un entorno real.

Un sistema de IA que solo se quede en el primer nivel será un mero **almacén de etiquetas**. Si llega al segundo, podrá **razonar**, pero solo al integrar el tercero será capaz de **apoyar decisiones útiles en el mundo real**.

> **Ejemplo**: Un chatbot médico no puede limitarse a reconocer que la palabra “fiebre” aparece en el mensaje (nivel léxico). Debe relacionarla con otros síntomas como “tos” para inferir un posible diagnóstico (nivel estructural), y finalmente ofrecer una acción coherente como recomendar una consulta médica (nivel pragmático).

> **Para reflexionar…**
>
> ¿Qué riesgos puede tener un sistema que se queda solo en el nivel léxico, por ejemplo un buscador que trata “fiebre” como cualquier palabra sin contexto?
>
> ¿Qué ventajas competitivas pueden obtener empresas o instituciones que logran alcanzar el nivel pragmático en la representación del conocimiento?
>

------

Es fundamental usar algún tipo de representación cuando manejamos la semántica de los sistemas inteligentes. Se necesita **ir más allá de los datos aislados** y manejar el **significado de los conceptos**, y para ello se utilizan **representaciones semánticas**. Estas representaciones son formas estructuradas de organizar el conocimiento que facilitan el razonamiento automático y la interpretación en contextos reales. Lo importante es que el sistema **entienda el papel que cada concepto desempeña y cómo se relaciona con los demás**, lo que lo acerca a un conocimiento más próximo al humano.

> **Ejemplo**:
> Un motor de búsqueda que encuentra “jaguar” debe decidir si se refiere a:
>
> - un **animal** (semántica biológica),
> - una **marca de coches** (semántica industrial),
> - o un **equipo de fútbol** (semántica cultural).
>
> Sin semántica, el sistema solo ve una cadena de texto; con semántica, puede **desambiguar** en función del contexto.

Vamos ahora a ocuparnos de las tres formas principales de representar el conocimiento en sistemas de IA: Las ontologías, los grafos de conocimiento y los marcos y redes semánticas.

#### Ontologías

Una **ontología** puede entenderse como un **mapa conceptual formalizado**, cuyo propósito es describir con precisión qué entidades existen en un dominio y cómo se relacionan entre sí. La idea es sencilla pero poderosa: si distintos sistemas o especialistas usan la misma ontología, todos comparten un mismo “vocabulario estructurado” y, por tanto, pueden **intercambiar conocimiento sin ambigüedades**.

A diferencia de una lista de términos o un diccionario, una ontología no solo nombra los conceptos, sino que los **organiza jerárquicamente**. Así, un concepto general puede englobar a otros más específicos: “animal” incluye a “mamífero”, que a su vez incluye a “perro” o “gato”. Pero la ontología no se limita a clasificar; también establece **relaciones semánticas** entre conceptos, como “es parte de”, “causa”, “se asocia con” o “requiere”.

Lo que hace que una ontología sea especialmente útil en inteligencia artificial es su carácter **formal**. Esto significa que no se trata solo de diagramas comprensibles para humanos, sino de estructuras escritas en lenguajes normalizados que las máquinas pueden procesar directamente. En este sentido, una ontología actúa como un **puente entre el conocimiento humano y la interpretación automática**, asegurando que lo que para una persona es intuitivo también pueda ser comprendido y manipulado por un sistema de IA.

Una ontología suele estar formada por tres piezas fundamentales: **conceptos, relaciones y restricciones**.

Los **conceptos** son las **unidades básicas** de la ontología. Representan las entidades principales del dominio, organizadas de lo más general a lo más específico. En cierto modo funcionan como “clases” que agrupan individuos con características comunes. Por ejemplo, en una ontología sobre animales, el concepto general *Animal* puede dividirse en *Mamífero*, *Ave* o *Reptil*, y cada uno de ellos puede subdividirse todavía más, hasta llegar a instancias concretas como *Perro* o *Gato*. Esta organización jerárquica permite **ubicar cada entidad en un nivel de generalidad adecuado**, y facilita que el sistema razone en distintos grados de detalle.

Pero los conceptos por sí solos son poco útiles si no están conectados. Por eso las ontologías definen también **relaciones** que explican cómo se vinculan unos con otros. Estas relaciones tienen un significado semántico explícito: no son simples enlaces arbitrarios, sino conexiones con un papel claro.

Algunos ejemplos frecuentes son:

- **“es un tipo de” (is-a)**: *Perro* es un tipo de *Mamífero*.
- **“forma parte de” (part-of)**: *Corazón* forma parte de *Ser humano*.
- **“está asociado con”**: *Diabetes* está asociada con *Insulina*.

Gracias a estas relaciones, el sistema puede ir más allá de los hechos aislados y **deducir información nueva**. Si sabe que “todo mamífero es un animal” y que “un perro es un mamífero”, puede concluir que “un perro es un animal” sin necesidad de que alguien lo indique expresamente.

Por último, el tercer componente que estructura una ontología, son las **restricciones**, que actúan como condiciones adicionales para garantizar que el conocimiento representado sea **coherente y preciso**. No basta con decir que “un ser humano tiene progenitores”; también es necesario precisar que los progenitores deben ser exactamente dos, y además del mismo tipo (seres humanos).

Las restricciones pueden limitar el número de relaciones permitidas, el tipo de conceptos que pueden vincularse o las propiedades que deben cumplirse en un contexto. En términos prácticos, funcionan como **reglas de consistencia** que ayudan a evitar contradicciones dentro de la ontología.

Al combinar **conceptos, relaciones y restricciones**, la ontología se convierte en un marco robusto para representar el conocimiento de un dominio. Los conceptos proporcionan las piezas, las relaciones marcan cómo se conectan y las restricciones aseguran que todo encaje sin inconsistencias. De este modo, lo que a primera vista parece solo un catálogo jerárquico se convierte en una **infraestructura lógica**, capaz de servir de base para el razonamiento automático y la interoperabilidad entre sistemas.

> **Ejemplo:**
>
> Si construimos una ontología sobre el ámbito educativo, podríamos empezar con un concepto amplio como *persona*, que se divide en *profesor* y *estudiante*. Entre ambos aparecería la relación *enseña a* o *aprende de*. Al definir formalmente estos conceptos y relaciones, el sistema ya puede razonar con ellos: si “Ana es profesora” y “Ana enseña a Juan”, la ontología le permite entender que “Juan es estudiante”.

A la hora de trabajar con ontologías existen toda una serie de herramientas de diseño y manejo de las mismas. Estas herramientas cumplen un papel doble: sirven de **soporte técnico** para la representación formal y de **puente práctico** para que expertos de distintos dominios colaboren en la construcción del conocimiento compartido.

Una de las plataformas más utilizadas a nivel mundial es **Protégé**, desarrollada por la Universidad de Stanford. Se trata de un entorno de software libre que permite crear, visualizar y editar ontologías en formatos estándar como OWL (Web Ontology Language) o RDF (Resource Description Framework). Su principal ventaja es que combina un interfaz accesible con funciones avanzadas, de modo que lo pueden utilizar tanto investigadores en informática como profesionales de otros campos que necesiten representar su conocimiento de forma formalizada. Protégé incluye, además, herramientas de validación que ayudan a comprobar la coherencia de las relaciones definidas.

En paralelo, existen **librerías en distintos lenguajes de programación** que facilitan el trabajo directo con ontologías. En Python, por ejemplo, destaca `OWLready2`, que facilita la integración de ontologías OWL con aplicaciones de IA. Estas librerías resultan útiles cuando se busca combinar la potencia del razonamiento semántico con modelos de aprendizaje automático o sistemas expertos implementados en código.

> Las ontologías son, en definitiva, una forma de **poner orden en el conocimiento**, no solo para clasificarlo, sino para hacerlo **explícito, compartido y utilizable** por sistemas inteligentes. Constituyen una de las piedras angulares de la IA simbólica, porque convierten el lenguaje humano, lleno de matices y ambigüedades, en una representación estructurada que admite razonamiento automático.

------

##### Para reflexionar…

1. ¿Por qué crees que organizar el conocimiento en jerarquías y relaciones explícitas facilita el razonamiento automático?
2. ¿Qué diferencias encuentras entre un diccionario, que simplemente define palabras, y una ontología, que busca capturar un dominio completo de forma estructurada?

#### Grafos de conocimiento

Un **grafo de conocimiento** es una manera de organizar la información inspirada en cómo los seres humanos entendemos las conexiones entre ideas. En lugar de almacenar datos en tablas rígidas, como ocurre en las bases de datos tradicionales, un grafo representa a las **entidades como nodos** y a sus **relaciones como aristas**. Así, cada nodo puede corresponder a una persona, un objeto, un lugar o incluso a un concepto abstracto, mientras que cada arista indica el vínculo que une esas entidades: “trabaja en”, “es parte de”, “causa”, “se trata con”.

La diferencia fundamental es que los grafos de conocimiento no solo dicen *qué datos existen*, sino que también muestran *cómo están conectados* y qué significan esas conexiones. Esto los convierte en estructuras con un enorme valor para la inteligencia artificial, porque permiten que un sistema no se limite a buscar coincidencias de palabras, sino que pueda **razonar con relaciones semánticas**.

Un ejemplo sencillo puede verse en el ámbito de la salud. Supongamos que un grafo contiene la información de que *Juan padece diabetes tipo 2* y que la *diabetes tipo 2 se trata con metformina*. Aunque no lo digamos explícitamente, el sistema puede deducir que *Juan está relacionado con la metformina como tratamiento*. Aquí no se trata solo de unir datos, sino de construir un entramado de significados que facilita inferencias.

Este tipo de grafos destacan por tres cualidades. En primer lugar, su **flexibilidad**: es fácil añadir nuevas entidades y relaciones sin alterar la estructura existente. En segundo lugar, su **capacidad de inferencia**, que permite descubrir vínculos indirectos entre elementos. Y en tercer lugar, su **escalabilidad**, que hace posible construir desde pequeños grafos de dominio —por ejemplo, para gestionar el conocimiento dentro de un pequeño negocio— hasta grafos de alcance global que organizan millones de entidades para mejorar las búsquedas en Internet.

En la práctica, los grafos de conocimiento se aplican en buscadores, asistentes virtuales, sistemas de recomendación, investigación biomédica y ciudades inteligentes, entre otros muchos contextos. Además, en la IA moderna se integran cada vez más con modelos de aprendizaje automático, sobre todo con los grandes modelos de lenguaje (LLMs). De esta combinación surge un equilibrio poderoso: los LLM generan hipótesis y respuestas de manera flexible, mientras que el grafo aporta **anclaje semántico y verificabilidad**. En definitiva, los grafos de conocimiento son la forma en que la inteligencia artificial se acerca a un **entendimiento estructurado del mundo**, conectando datos dispersos en una red que puede ser explorada, ampliada y utilizada para razonar.

Uno de los ejemplos más conocidos de grafos de conocimiento en uso real es el **Google Knowledge Graph**. Se trata de una enorme base de datos semántica que organiza información sobre personas, lugares, objetos, obras y conceptos, vinculándolos entre sí mediante relaciones explícitas.

Su objetivo principal es que el buscador de Google no solo encuentre páginas con palabras coincidentes, sino que **entienda el significado de las consultas**. Gracias a esto, el sistema puede responder de manera más precisa y contextualizada.

> **Ejemplo**: Si escribimos en el buscador “Jaguar”, el sistema no se limita a mostrar páginas que contengan esa palabra. El Knowledge Graph le permite distinguir si nos referimos al animal, a la marca de coches o a un equipo deportivo, en función del contexto y de nuestras búsquedas previas.

El funcionamiento se basa en una gran red de **nodos** (entidades como “Albert Einstein”, “Relatividad”, “Premio Nobel”) y **relaciones** (“descubrió”, “recibió”, “nació en”). De este modo, una consulta puede resolverse no solo con coincidencias de texto, sino con **razonamiento semántico**: relacionando conceptos y trayendo información estructurada.

Esta herramienta tiene aplicaciones que van más allá de las búsquedas en Internet. También se utiliza para alimentar asistentes virtuales como Google Assistant, para mejorar sistemas de recomendación y para integrar información procedente de distintas fuentes en un mismo marco semántico. En definitiva,**Google Knowledge Graph** es un ejemplo de cómo los grafos de conocimiento pueden escalar a nivel global, convirtiéndose en la **infraestructura invisible** que permite que un buscador “entienda” de qué hablamos y no solo “qué palabras” usamos.

> **Neo4j y los grafos de conocimiento**
>
> Para trabajar con grafos en inteligencia artificial necesitamos herramientas capaces de almacenar entidades y relaciones de forma nativa. **Neo4j** es una de las bases de datos orientadas a grafos más extendidas, y se ha convertido en un referente porque permite representar la información directamente en forma de **nodos** (entidades) y **aristas** (relaciones).
>
> A diferencia de las bases de datos relacionales tradicionales, que organizan los datos en tablas, Neo4j se centra en la **conectividad**. Esto hace que consultas complejas sobre relaciones —por ejemplo, “qué medicamentos están relacionados con qué enfermedades y a través de qué síntomas”— puedan resolverse de manera mucho más eficiente. Su lenguaje de consulta, llamado **Cypher**, está diseñado específicamente para navegar por grafos, lo que facilita extraer patrones y dependencias entre elementos.
>
> Aunque Neo4j puede aplicarse en campos tan diversos como redes sociales, logística o detección de fraude, en inteligencia artificial ha cobrado especial importancia como soporte para la construcción de **grafos de conocimiento**. Estos grafos organizan entidades y sus vínculos de forma semántica, permitiendo que un sistema no solo almacene datos, sino que también entienda **cómo se relacionan entre sí**.
>
> Por ejemplo, en el ámbito biomédico, un grafo de conocimiento en Neo4j podría enlazar genes, proteínas y enfermedades, de modo que un investigador pueda explorar de manera intuitiva posibles conexiones relevantes para un diagnóstico o una terapia. En buscadores y sistemas de recomendación ocurre algo similar: Neo4j facilita el almacenamiento y la exploración de grafos que vinculan productos, usuarios, intereses o contextos.
>
> En resumen, Neo4j no es en sí mismo una herramienta exclusiva de grafos de conocimiento, pero por su estructura, lenguaje y flexibilidad, se ha convertido en una de las plataformas más utilizadas para **construir, consultar y explotar grafos de conocimiento** en aplicaciones reales.

#### Marcos y redes semánticas

Además de los grafos de conocimiento, la inteligencia artificial también ha desarrollado otras estructuras diseñadas para capturar el **significado en contextos concretos**. Entre ellas destacan los **marcos** y las **redes semánticas**, cuyo objetivo es representar **escenas o situaciones típicas** de la vida cotidiana.

Un **marco** funciona como una plantilla que organiza los elementos y roles habituales de una situación. Pensemos en la escena “ir a un restaurante”: el marco incluiría papeles como cliente, camarero, menú, comida y cuenta. Cada vez que un sistema se enfrenta a una descripción relacionada con esta situación, puede activar el marco correspondiente y anticipar qué actores y objetos deben intervenir.

Las **redes semánticas** amplían esta idea conectando marcos y conceptos a través de relaciones explícitas, formando una estructura de nodos y enlaces. Estas redes permiten que el sistema **interprete frases ambiguas** o incompletas basándose en el contexto. Si alguien dice “el camarero trajo la cuenta”, el sistema entiende que se trata de la situación del restaurante y que la “cuenta” se refiere al pago de la comida, no a un número abstracto.

La fuerza de marcos y redes semánticas reside en su **capacidad para aportar contexto**. No se limitan a procesar palabras aisladas, sino que representan **conocimiento estructurado de escenas típicas**, lo que ayuda a la IA a anticipar acciones y desambiguar significados. Aunque hoy en día han sido parcialmente sustituidos por modelos conexionistas y grandes modelos de lenguaje, siguen siendo una referencia fundamental en la evolución de la IA simbólica y aún se utilizan en ámbitos donde el contexto estructurado es esencial.

Aunque los **marcos** y las **redes semánticas** surgieron como propuestas específicas dentro de la IA simbólica, en la práctica las herramientas empleadas para su diseño y gestión coinciden con las utilizadas en otras formas de **representación del conocimiento**. Entornos como **Protégé**, las **bases de datos de grafos** (por ejemplo, Neo4j) o las librerías de Python para manejar RDF y ontologías se aplican indistintamente para construir marcos, grafos de conocimiento u ontologías formales. Esto se debe a que, en el fondo, todas estas estructuras comparten la misma lógica: organizar entidades, roles y relaciones de manera que sean comprensibles tanto para un humano como para un sistema automático.

------

> **Para reflexionar…**
>
> ¿Hasta qué punto un modelo actual de lenguaje (como ChatGPT) realmente “comprende” la semántica, y hasta qué punto solo maneja correlaciones estadísticas?
>
> ¿Qué riesgos pueden surgir si un sistema de IA **pierde el contexto semántico** (ej. al tomar decisiones médicas o legales)?
>

### Los objetivos de una representación adecuada

Se puede intuir entonces que representar el conocimiento en IA no tiene como meta acumular símbolos, sino **hacerlos operativos**. En la práctica, esto se traduce en dos grandes objetivos: **explicar** y **decidir**.

**Explicar** significa que el sistema sea capaz de **dar razones** de por qué una conclusión se sostiene o por qué una acción es adecuada. Esta capacidad es clave en entornos profesionales donde la **justificación es tan importante como la respuesta**: medicina, derecho, ingeniería crítica, etc.

Por ejemplo, en un **sistema experto médico**, no basta con indicar que un paciente tiene “posible gripe”. El valor añadido está en que pueda argumentar: “La conclusión se debe a la presencia de fiebre y tos persistente, combinadas con el antecedente de exposición reciente”. En un **sistema financiero**, una recomendación de inversión tiene que ir acompañada de explicaciones sobre los indicadores que han motivado la decisión (riesgo, volatilidad, tendencia del mercado).

De esta forma, la representación no es solo un **mecanismo de cálculo interno**, sino también un **lenguaje de comunicación** entre la máquina y el humano

El otro gran objetivo es la **acción**: tomar decisiones de forma autónoma en función del conocimiento disponible. Decidir supone pasar de “saber algo” a **hacer algo con ello**.

Ilustremos lo anterior con un par de ejemplos. En un **sistema de control industrial**, la regla *“Si la presión del tanque supera cierto umbral, activar válvula de seguridad”* es una decisión automática basada en conocimiento representado formalmente. En el caso de un **robot autónomo**, la representación del entorno permite decidir “gira a la derecha” porque sabe que hay un obstáculo delante y un camino libre a la derecha.

La clave es que la representación esté diseñada no solo para **describir la realidad**, sino para **guíar la acción en ella**.

En la práctica, **explicar y decidir no son objetivos independientes**, sino complementarios. Un sistema que **explica sin decidir** se convierte en un observador pasivo: útil para analizar, pero inoperante en situaciones dinámicas. Por su parte, un sistema que **decide sin explicar** puede ser eficiente, pero genera desconfianza y falta de control (es lo que hoy llamamos “caja negra” en IA). Por eso, los modelos de representación buscan equilibrar ambos propósitos: dar soporte a la **acción autónoma** y, a la vez, mantener la **capacidad de justificar** el razonamiento.

------

> **Ejemplo**: Un asistente virtual para emergencias médicas debe decidir si recomienda administrar un medicamento. Esa decisión debe estar apoyada por una explicación clara: “Se recomienda paracetamol porque el paciente presenta fiebre de 39 °C, no hay alergias registradas y no se han identificado contraindicaciones en su historial”.
>
> Aquí la representación cumple su doble rol: la **decisión inmediata** y la **explicación justificativa**.

------

> **Para reflexionar…**
>
> ¿En qué ámbitos debería darse más peso a la capacidad de **explicar** frente a la de **decidir**?
>
> ¿Qué consecuencias puede tener en la práctica un sistema que **decide muy bien pero no sabe explicar** por qué lo hace?

---

### Criterios de una buena representación

Una representación de conocimiento no es útil por el mero hecho de almacenar símbolos. Para que un sistema pueda **razonar de manera eficaz**, esa representación debe cumplir ciertos **criterios de calidad**.

El primero es la **expresividad**: la capacidad de decir lo que realmente importa en el dominio. Una lógica muy básica puede resultar demasiado limitada para expresar relaciones complejas, mientras que una lógica muy rica puede volverse inabordable en términos de cómputo.

El segundo criterio es la **eficiencia computacional**. Un formalismo no solo debe ser capaz de representar ideas, sino también permitir que un sistema **razone en un tiempo aceptable**. Una representación demasiado pesada o con inferencias inabarcables pierde utilidad práctica.

La **modularidad y mantenibilidad** también son esenciales. El conocimiento debe poder **actualizarse o ampliarse** sin necesidad de reescribirlo todo. En sistemas expertos, por ejemplo, esta cualidad facilita que un especialista humano añada o modifique reglas sin romper la consistencia general.

Otro criterio es la **interpretabilidad**: el sistema debe poder **explicar sus decisiones** de manera que resulten comprensibles para un humano. Sin esta capacidad, aunque la decisión sea correcta, el usuario puede no confiar en ella.

Por último, la representación debe mostrar **robustez ante la incertidumbre**. El mundo real rara vez se presenta en blanco y negro; por eso es importante que el formalismo pueda gestionar información incompleta, imprecisa o conflictiva.

En la práctica, siempre existe un **compromiso**: cuanto más expresivo es un sistema, más costosa suele ser la inferencia. Diseñar una buena representación significa buscar un **equilibrio** entre potencia y viabilidad.

## Conocimiento declarativo y procedimental

Aparte de lo visto hasta ahora, en inteligencia artificial resulta fundamental distinguir entre dos maneras de representar el saber: el **conocimiento declarativo** y el **conocimiento procedimental**. Esta diferencia marca el modo en que un sistema puede explicar lo que sabe y utilizarlo para resolver problemas.

### Conocimiento declarativo: “lo que es”

El conocimiento declarativo expresa **hechos, definiciones y relaciones** que se consideran verdaderos dentro de un dominio. Se representa habitualmente en forma de **reglas, lógicas u ontologías**. Gracias a su estructura explícita, permite a un sistema **explicar sus conclusiones**, verificar su coherencia y ser actualizado por expertos de manera controlada.

> **Ejemplo**:
> En medicina, una regla declarativa podría ser:
> *“Si el paciente tiene fiebre y tos persistente, entonces posible gripe.”*
>
> Aquí, el sistema no solo almacena datos, sino que los **estructura con semántica** para poder razonar sobre ellos.

Su principal ventaja es la **interpretabilidad**: cada paso del razonamiento puede justificarse. Su mayor limitación es la **rigidez**: el conocimiento declarativo requiere un esfuerzo de ingeniería y no se adapta bien a entornos cambiantes o con alta incertidumbre.

### Conocimiento procedimental: “cómo se hace”

El conocimiento procedimental no describe hechos estáticos, sino **estrategias, planes y métodos** para actuar o calcular. Se centra en el *saber hacer*, que puede plasmarse en algoritmos, planes de acción o, en el caso del aprendizaje automático, en **parámetros aprendidos** que guían la conducta del sistema.

> **Ejemplo**:
> En un modelo de aprendizaje por refuerzo, una política $\pi(s)$ especifica qué acción elegir en cada estado $s$.
> En una red neuronal, los **pesos internos** representan cómo transformar una imagen en una clasificación (“neumonía” o “no neumonía”).

La ventaja del conocimiento procedimental es su **eficacia** en problemas complejos y su **capacidad de adaptación**. La limitación está en que suele ser opaco: difícil de leer y justificar, lo que da lugar a las llamadas “cajas negras”.

### La complementariedad entre ambos

En la práctica, los sistemas más robustos combinan las dos perspectivas. El **declarativo** aporta un marco normativo, semántico y explicativo. El **procedimental** aporta adaptabilidad, eficiencia y capacidad de manejar la variabilidad de los datos.

Por ejemplo, en el ámbito de la **banca**, un modelo procedimental calcula la probabilidad de impago, pero reglas declarativas establecen límites legales: *“Nunca aprobar un crédito sin comprobación de ingresos”*. En cuanto al ámbito **sanitario**, un modelo de deep learning detecta patrones en radiografías, pero un grafo de conocimiento declarativo podría garantizar que las recomendaciones respeten protocolos clínicos.

> **Para reflexionar…**
>
> ¿Imagina una disciplina en la que aplicar modelos de IA. ¿Qué aspectos de la misma requieren más **explicaciones transparentes** y cuáles más **decisiones rápidas y adaptativas**?
>
> ¿Qué riesgos tendría delegar todo a modelos procedimentales sin el respaldo de reglas declarativas claras?

## Determinismo e incertidumbre

En los primeros sistemas de inteligencia artificial se asumía que el mundo podía describirse de forma **determinista**: las cosas eran verdaderas o falsas, sin puntos intermedios. Así, una regla como

$$
\textbf{Fiebre} \land \textbf{Tos} \rightarrow \textbf{Posible\_Gripe}
$$

se aplicaba siempre que se cumplieran las condiciones, y el sistema llegaba a una conclusión inequívoca.

Sin embargo, la realidad rara vez se comporta de forma tan clara. Los síntomas pueden aparecer de manera parcial. En sistemas automáticos los sensores pueden fallar y en muchos almacenes de datos, estos suelen estar incompletos. En estos casos surge la **incertidumbre**.

> **Ejemplo**: no todos los pacientes con fiebre y tos tienen gripe; algunos pueden tener una infección distinta o incluso una alergia. Si el sistema tratara esta regla como determinista, daría diagnósticos erróneos.

Para manejar la incertidumbre, la IA ha desarrollado herramientas que permiten asignar **grados de confianza** a las conclusiones en lugar de limitarse al “sí o no”. Una de las más conocidas es la **probabilidad**, que mide hasta qué punto una hipótesis es plausible a partir de la evidencia.

La idea esencial es que, cuando aparece nueva información, un sistema no solo debería **aplicar reglas rígidas**, sino también **actualizar su nivel de certeza** sobre lo que ocurre.

Imagina que queremos saber si un paciente tiene gripe al observar que tiene fiebre. Si sabemos que la gripe produce fiebre en la mayoría de los casos, podemos asignar una **probabilidad alta** a la hipótesis. Pero si también sabemos que la fiebre aparece en muchas otras enfermedades, la probabilidad no será del 100 %.

La **fórmula de Bayes**, que estudiaremos más adelante con detalle, permite actualizar estas creencias de manera formal y consistente. Por ahora basta con entender que la probabilidad ofrece un **lenguaje para hablar de la incertidumbre**.

En conclusion, el enfoque **determinista** simplifica el razonamiento, pero se queda corto en dominios reales. La **incertidumbre** es la norma en la vida real: sensores que fallan, síntomas ambiguos, datos incompletos… En el dominio de la incertidumbre la **probabilidad** es la herramienta más extendida para representar la información cuando trabajamos con IA.

**Para reflexionar…**

¿Qué ejemplos cotidianos conoces en los que un sistema humano o técnico debe decidir **con información incompleta**?

¿Qué riesgos puede tener confiar en sistemas deterministas en entornos donde predomina la incertidumbre?

------

## Del conocimiento al razonamiento

Representar conocimiento no tendría demasiado sentido si ese conocimiento no pudiera usarse para **pensar**. La verdadera utilidad de una representación aparece cuando se convierte en la base de un proceso de **razonamiento**, es decir, cuando un sistema es capaz de ir más allá de lo que ya sabe para **deducir nuevas conclusiones**, **proponer explicaciones plausibles** o **tomar decisiones**.

En inteligencia artificial se distinguen varias formas de razonar. La **deducción** es la más estricta: se trata de derivar consecuencias que son necesariamente verdaderas si lo son las premisas. Es el tipo de razonamiento que se aplica en lógica formal. Si sabemos que todos los pacientes con gripe tienen fiebre, y sabemos que Juan tiene gripe, entonces podemos concluir con certeza que Juan tiene fiebre. La deducción aporta rigor y fiabilidad, pero resulta rígida: depende por completo de la validez de las reglas iniciales.

Más flexible es la **abducción**, que no busca certezas, sino explicaciones razonables para lo que observamos. Si vemos que un paciente tiene fiebre y tos, una hipótesis plausible es que padezca gripe. No es una conclusión garantizada, pero sirve como punto de partida para una investigación o un diagnóstico. La abducción es el razonamiento que mejor refleja la práctica clínica y, en general, cualquier tarea en la que haya que interpretar síntomas, indicios o huellas.

La **inducción**, por su parte, sigue la vía contraria: a partir de varios casos concretos, generaliza una regla que podría aplicarse a situaciones futuras. Si en distintos pacientes la fiebre y la tos se han asociado repetidamente a un diagnóstico de gripe, el sistema generaliza que esos síntomas suelen indicar la enfermedad. Aquí se abre la puerta al aprendizaje automático, que formaliza este proceso inductivo a gran escala mediante algoritmos entrenados con grandes cantidades de datos.

Estas formas de razonar son de importancia fundamental en los denominados **sistemas expertos**. En ellos, estas formas de razonar se implementan de manera operativa mediante dos estrategias clásicas. Por un lado, el proceso denominado **encadenamiento hacia adelante**. Esta forma de proceder comienza con los hechos disponibles y va aplicando reglas de manera progresiva hasta llegar a una conclusión. Si el sistema registra fiebre y tos, aplicará la regla que los relaciona con una posible gripe y derivará ese diagnóstico como resultado. En el otro lado se tienen los procedimientos de **encadenamiento hacia atrás**. En ellos en cambio, se parte de una hipótesis y se buscan las pruebas que la sustenten. En el caso del paciente con posible gripe, el sistema indagará si hay fiebre, tos u otros síntomas asociados.

Estas estrategias permiten que el conocimiento almacenado en forma de hechos y reglas deje de ser un catálogo estático y se convierta en una **máquina de inferencias**, capaz de responder preguntas o apoyar decisiones.

> **Ejemplo:**
>
> Imaginemos que en una base de conocimiento figuran dos reglas: “si hay fiebre y tos, entonces posible gripe” y “si además aparece dolor muscular, se refuerza el diagnóstico de gripe”. Cuando el sistema recibe los síntomas de un paciente —fiebre, tos y dolor muscular—, un encadenamiento hacia adelante activará las dos reglas y generará como conclusión el diagnóstico de posible gripe reforzado por evidencia adicional. Y si, en lugar de tratar el problema como determinista, añadimos probabilidades a los síntomas, se podría llegar a la conclusión final teniendo en cuenta que la gripe es más o menos probable según la prevalencia en la población y los patrones de aparición de los síntomas.

Al final de este apartado, se ha pasado de hablar de **representar conocimiento** a entender cómo se convierte en un proceso de **razonamiento efectivo**. El siguiente paso en nuestro recorrido será estudiar los dos grandes pilares que históricamente han materializado estas ideas: los **sistemas expertos**, que se apoyan en reglas y deducción, y el **razonamiento probabilístico**, que introduce la flexibilidad necesaria para manejar la incertidumbre.

























