# Posts LinkedIn: RAG v0.9, SCAR y revisión de IA en urología

---

## 1. POST RAG (versión final, basada en la v0.9)

> Este estudio tiene algo especial: lo he hecho con mi padre.
>
> Él, cirujano pediátrico en la sección de Urología Pediátrica de la Arrixaca, pone el criterio clínico. Yo, la parte de IA. Queríamos responder una pregunta sencilla: ¿basta con subir las guías en PDF a una IA para que responda bien?
>
> Spoiler: no.
>
> 📄 **Primera parte: ¿importa cómo le das los documentos?**
> Montamos un evaluador con RAG sobre reflujo vesicoureteral e ITU pediátrica: GPT-4o que solo puede responder con 12 fuentes cerradas (guías EAU, AUA y española, RIVUR, PREDICT, metaanálisis, scores predictivos).
> Mismo modelo, mismas instrucciones y 50 preguntas difíciles, con datos escondidos en tablas, forest plots y scores. Lo único que cambiaba era el formato de las fuentes: el PDF original o un texto curado a mano.
> • Puntuación: 84 → 94 sobre 100
> • Respuestas completamente correctas: 72 % → 88 % (p = 0,039)
> • En algunas preguntas el dato estaba en el PDF… y la IA no lo encontraba.
> Yo volví a puntuar las 100 respuestas a ciegas, sin saber cuál era cuál, y el resultado se mantuvo (93 vs 82).
>
> Un detalle honesto: en las dos preguntas sobre algoritmos de la guía ganó el PDF. Pasar un diagrama de flujo a texto también puede perder información. La curación hay que revisarla.
>
> 👩‍⚕️ **Segunda parte: IA frente a expertos**
> 11 casos controvertidos respondidos por 30 urólogos pediátricos de la SIUP (todos con más de 10 años de experiencia), por Open Evidence y por nuestro evaluador.
> Lo que más me ha hecho pensar: coincidir con la mayoría de expertos, coincidir con otra IA y estar alineado con la guía son tres cosas distintas.
> • En un reflujo grado IV-V que persiste, mantener la profilaxis es vigilar, no tratar el reflujo.
> • Cuando las guías no dan un intervalo único para la cistografía de control, lo honesto es decirlo, no elegir una opción del test.
>
> Lo que me llevo:
> 1️⃣ Antes de preguntarte qué modelo usar, pregúntate qué documentos le das y en qué formato.
> 2️⃣ Que una respuesta suene segura no significa que acierte.
>
> Limitaciones, que las hay: la herramienta la evaluamos nosotros, las preguntas son nuestras y falta validación externa y prospectiva.
>
> [SOLO SI SE CONFIRMA] Lo presentamos en el Congreso de la SIUP en Lima (7-10 de octubre). Si vas a estar, nos vemos allí 🇵🇪
>
> Y sí: investigar con tu padre es de lo mejor que me ha dado la residencia.
>
> #UrologíaPediátrica #ReflujoVesicoureteral #InteligenciaArtificial #RAG #SaludDigital

**Imagen sugerida:** una tabla sencilla "PDF 84 · Texto curado 94" o una foto vuestra (tu padre y tú). Con foto de los dos funcionará mucho mejor que con cualquier diapositiva.

---

## 2. POST SCAR: "¿Has asentido alguna vez a la IA sin estar de acuerdo?"

*(Planteado como reflexión, sin citar el manuscrito porque no está publicado. Los estudios que se mencionan sí lo están.)*

> Sesión clínica. Alguien proyecta lo que recomienda la IA para el caso.
> Tú habías pensado otra cosa. Tienes un motivo concreto: algo del paciente que no está en el resumen.
>
> ¿Lo dices?
>
> Muchas veces no. Y no porque la IA te haya convencido, sino porque discrepar delante de quien te evalúa tiene un coste. Asientes, la sesión sigue y en el acta queda "consenso".
>
> Llevo un tiempo dándole vueltas a este fenómeno: estar en desacuerdo por dentro y conforme por fuera. La literatura ya da pistas:
> 🔹 En mamografía, sugerencias erróneas presentadas como de IA cambiaron la clasificación que hacían radiólogos (Radiology 2023).
> 🔹 En experimentos con 1.445 personas, muchas siguieron a un algoritmo que se equivocaba en tareas que sabían resolver solas (J Manag Inf Syst 2025).
> 🔹 Entrenar a la gente para que "hable" no mejoró de forma significativa cuánto hablaba en quirófano simulado (Acad Med 2016). El problema no suele ser la persona, es el contexto.
>
> Lo que me preocupa no es que la IA se equivoque. Es que su recomendación se convierta en la vara con la que se mide quién "sabe", y que las objeciones útiles no lleguen a decirse.
>
> Tres ideas que me parecen razonables, sobre todo en docencia:
> 1️⃣ Pedir el juicio del residente antes de enseñar lo que dice la IA.
> 2️⃣ Preguntar "¿qué parte del caso no te encaja?" en lugar de "¿estás de acuerdo?".
> 3️⃣ Valorar el razonamiento, no la coincidencia con la máquina. Tampoco premiar discrepar por discrepar.
>
> ¿Te ha pasado, desde un lado o desde el otro?
>
> #InteligenciaArtificial #EducaciónMédica #Residentes #SeguridadDelPaciente #IAenMedicina

**Ojo con el tono:** está escrito en general, no sobre tu servicio. Si te preguntan en comentarios, puedes decir que estás trabajando en un artículo sobre esto sin dar más detalles.

---

## 3. POST REVISIÓN: "Una IA con un AUC altísimo no está lista para tu consulta"

*(Con datos publicados que cita tu revisión. Hay dos versiones del cierre según el estado del manuscrito.)*

> Una IA con un AUC altísimo no está necesariamente lista para tu consulta.
>
> La pregunta útil no es "¿qué precisión tiene?", sino "¿qué nivel de evidencia tiene detrás?". Si ordenamos la IA en uro-oncología por su mejor evidencia, no por su mejor resultado, el mapa cambia:
>
> 🟢 **Patología digital de biopsia de próstata**: lo más maduro. Autorización FDA como segundo lector, un laboratorio con 3 años de uso rutinario y más de 122.000 preparaciones, y estudios prospectivos que reducen la inmunohistoquímica.
> 🟡 **Biomarcadores predictivos (tipo ArteraAI)**: autorizados y en guías NCCN. En un ensayo prospectivo, conocer el resultado cambió el 27,5 % de las decisiones sobre ADT. Aún falta saber si mejora los resultados oncológicos.
> 🟡 **Cirugía guiada por IA**: un ensayo aleatorizado (RIDERS) con menos márgenes positivos (22 % vs 39 %). Es un único grupo y hace falta replicarlo.
> 🟠 **RM de próstata y citología urinaria**: validación externa y prospectiva, pero sin demostrar todavía que se eviten biopsias o cistoscopias sin perder tumores.
> 🔴 **IA generativa para decidir tratamientos**: validación técnica, sobre todo con casos simulados. Hoy, investigación o uso muy supervisado.
>
> La siguiente mejora no va a venir de subir el AUC otro punto. Va a venir de demostrar que una IA concreta, en un circuito concreto, cambia una decisión a mejor y lo sigue haciendo después de implantarla.
>
> **[Cierre A, si ya hay preprint o aceptación]:** Lo hemos resumido en una revisión con un marco de 6 "puertas" para decidir cuándo una IA puede pasar a la práctica. Enlace en comentarios 👇
> **[Cierre B, si aún no]:** ¿Qué IA de esta lista usáis ya en vuestro hospital?
>
> #Urología #CáncerDePróstata #InteligenciaArtificial #MedicinaBasadaEnLaEvidencia #SaludDigital

---

## 4. POST: "Funciona en el laboratorio. ¿Y en tu hospital?"

*(Datos de estudios publicados citados en la revisión.)*

> Una IA puede funcionar genial con imágenes seleccionadas y fallar en la vida real. Tres ejemplos de urología:
>
> 🔹 **Cistoscopia.** Hay sistemas que detectan tumor vesical con mucha precisión en imágenes fijas seleccionadas. En un piloto prospectivo en tiempo real, durante la RTU la sensibilidad por fotograma cayó al 52,9 %. Sangrado, movimiento, iluminación: el mundo real no viene en el dataset.
> 🔹 **RM y extensión extraprostática.** En un metaanálisis, la sensibilidad bajó de 0,77 en validación interna a 0,66 en validación externa… con el mismo AUC (0,81 vs 0,80). El modelo seguía ordenando bien a los pacientes; lo que no se trasladaba era el punto de corte.
> 🔹 **PI-CAI.** Más de 10.000 RM, pero el 93,4 % de un solo fabricante de resonancia.
>
> Antes de fiarte de una IA, pregunta:
> 1️⃣ ¿Dónde se validó? ¿En otro hospital, con otras máquinas y otra población?
> 2️⃣ ¿Con qué punto de corte y para qué papel: triaje, segundo lector o descartar?
> 3️⃣ ¿Alguien ha medido qué pasa con los pacientes, o solo el AUC?
>
> Si la respuesta es "en un centro, retrospectivo y con el AUC", no es mala IA. Es una IA que todavía no ha salido del laboratorio.
>
> #Urología #InteligenciaArtificial #Endourología #CáncerDeVejiga #SaludDigital

---

## 5. POST (de la charla): "Yo también la uso"

> Hace no tanto, admitir que habías usado IA para preparar una sesión sonaba a trampa. El mérito estaba en haber sufrido el proceso, no en la calidad del resultado.
>
> Creo que es un error de categoría. Nadie audita cómo se escribió un texto: se audita si es correcto. La responsabilidad no se delega; la ejecución, sí.
>
> Y las revistas ya lo han entendido. No prohíben la IA: la regulan.
> ✔️ Exigen declarar su uso.
> ✔️ Un modelo no puede ser autor.
> ✔️ La responsabilidad sigue siendo íntegra de los autores.
> El debate ha pasado de "¿lo permitimos?" a "¿cómo lo declaras?".
>
> Yo la uso: para ordenar ideas, revisar el inglés, buscar bibliografía que luego compruebo a mano y hasta para programar herramientas para la consulta. Y lo declaro en cada artículo.
>
> Lo que sí me parece peligroso es el secretismo. Quien la usa a escondidas no la declara, no la verifica y no aprende a detectar cuándo se equivoca.
>
> Mi regla: la IA es un residente de primer año infinitamente rápido, con cero criterio y cero vergüenza para inventarse una respuesta antes que admitir que no la sabe. Útil, siempre que el volante lo lleves tú.
>
> ¿Tú lo dices en voz alta cuando la usas?
>
> #InteligenciaArtificial #Urología #EducaciónMédica #Residentes #Investigación

---

## Calendario propuesto

| Día | Post |
|---|---|
| Mar 29 o mié 30 | 1. RAG con tu padre |
| Vie 2 oct | 5. "Yo también la uso" (opinión, fácil, genera comentarios) |
| Semana congreso / tras Lima | 2. SCAR |
| Semana siguiente | 4. "Funciona en el laboratorio" |
| Cuando haya preprint o aceptación | 3. Niveles de evidencia (cierre A) |
| Mié/jue (ya previsto) | Verificar citas / "paper fantasma" |
