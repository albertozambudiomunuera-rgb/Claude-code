# Borradores LinkedIn: semana del 27/09/2026

Fuentes: charla "IA en Urología – Yo también la uso" (23/09), revisión *Clinical readiness of AI in urologic oncology* (npj Digital Medicine, **sin publicar**), manuscrito RVU-RAG (ES anonimizado + EN v0.7 con la fase SIUP), manuscrito SCAR (AI & Society, **sin publicar**).

---

## POST 1: "No hay una IA de próstata" (para hoy)

**Imágenes:** `img/post1_un-cuello-de-botella-una-ia.png` (principal) y, opcionalmente, `img/post1_chat-abierto-vs-rag.png` como segunda imagen.
Les he quitado el pie "Astellas · IA en Urología" y el número de diapositiva, y he cambiado "el paper fantasma que veremos después" por "citas inventadas con aspecto impecable". Así no se nota que salen de una charla.

> Cuando hablamos de "IA en urología" parece que nos referimos a una sola herramienta. No es así.
>
> En cáncer de próstata hay una IA distinta para cada cuello de botella del recorrido del paciente:
>
> 🔹 **Imagen.** Segundo lector de RM. En PI-CAI (Lancet Oncol 2024) la IA superó a 62 radiólogos en AUC (0,91 vs 0,86), pero no demostró no inferioridad frente a los informes reales del día a día, donde el radiólogo tiene la historia clínica y puede consultar a otros.
> 🔹 **Biopsia.** Patología digital: es lo más cerca de la práctica rutinaria. Tiene autorización FDA como segundo lector, y en un estudio prospectivo redujo el uso de inmunohistoquímica casi a la mitad.
> 🔹 **Riesgo.** ArteraAI: autorización De Novo de la FDA en 2025 y presencia en las guías NCCN. No solo pronostica: intenta predecir a quién le sirve añadir ADT a la radioterapia.
> 🔹 **Decisión.** Mapas 3D del tumor (Unfold AI) para planificar cirugía o terapia focal.
> 🔹 **Seguimiento.** Asistentes de voz tipo Lola/Tucuvi que llaman al paciente entre consultas.
>
> Y luego están los chats generales (ChatGPT, Claude, Gemini…), que es lo que más usamos de verdad en consulta. Ahí la pregunta clave no es qué modelo usas, sino de dónde sale la respuesta: de la memoria del modelo o de una guía cargada y citada.
>
> Lo que me llevo después de revisar la evidencia:
> 1️⃣ Precisión alta en un estudio retrospectivo no es lo mismo que beneficio para el paciente.
> 2️⃣ Casi todo es retrospectivo, y buena parte lo firman los propios desarrolladores.
> 3️⃣ Si el algoritmo falla, la firma del informe sigue siendo nuestra.
>
> ¿Cuál de estas has visto ya funcionando en tu hospital?
>
> #Urología #InteligenciaArtificial #CáncerDePróstata #SaludDigital #IAenMedicina

**Datos y fuentes (por si alguien pregunta en comentarios):**
- PI-CAI: Saha et al., Lancet Oncol 2024;25:879-887.
- Patología: Paige Prostate FDA De Novo DEN200080; CONFIDENT-P (Flach et al., JCO Clin Cancer Inform 2025), con RR de IHQ por cáncer detectado de 0,55.
- ArteraAI: FDA DEN240068 (2025); NCCN Prostate v7.2026.
- Unfold AI: FDA 510(k) dic-2022, solo disponible en EE. UU.

---

## POST 2: RVU + RAG, antes del congreso SIUP (martes 29 o miércoles 30)

> Subir los PDFs de las guías a una IA no basta.
>
> Junto a Gerardo Zambudio Carmona (Urología Pediátrica, H. Virgen de la Arrixaca), Iván Somoza y S. Altamirano (CHU A Coruña) construimos un evaluador con RAG para reflujo vesicoureteral pediátrico, y lo pusimos a prueba en dos fases.
>
> 📄 **Fase 1: ¿importa el formato de las fuentes?**
> Mismo modelo, mismas instrucciones y 50 preguntas. Lo único que cambiaba era cómo se le daban las 12 fuentes (guías, ensayos, metaanálisis, modelos predictivos): el PDF original o un texto curado a mano, con las tablas y los scores pasados a texto explícito.
> • Puntuación global: 84 → 94 sobre 100
> • Respuestas completamente correctas: 72 % → 88 % (McNemar p = 0,039)
> • En dos preguntas el dato estaba en el PDF… y el sistema no lo encontró.
>
> 👩‍⚕️ **Fase 2: IA vs expertos**
> 11 escenarios clínicos respondidos por 30 urólogos pediátricos de la SIUP (todos con más de 10 años de experiencia), por Open Evidence y por nuestro evaluador.
> La conclusión que más me interesa: coincidir con la mayoría de expertos, coincidir con otra IA y estar alineado con la guía son tres cosas distintas.
> • En el RVU grado IV-V persistente, mantener la profilaxis es vigilancia, no un tratamiento que corrija el reflujo. Según cómo se formule la pregunta, cambia la respuesta "correcta".
> • Cuando las guías no dan un intervalo único para la cistografía de control, el evaluador lo dijo en lugar de forzar una opción del test.
>
> Limitaciones, que las hay: el sistema lo evaluamos nosotros mismos, las preguntas las diseñamos nosotros y falta validación externa y prospectiva.
>
> Lo presentamos en el Congreso de la SIUP en Lima (7-10 de octubre). Si vas a estar, hablamos allí 🇵🇪
>
> #UrologíaPediátrica #ReflujoVesicoureteral #InteligenciaArtificial #RAG #SIUP2026

---

## Otras ideas sacadas del material (para más adelante)

| # | Idea | Gancho | Fuente | Ojo |
|---|------|--------|--------|-----|
| 3 | **"¿Has asentido alguna vez a la IA sin estar de acuerdo?"** (conformidad estratégica, SCAR) | El residente que no discute la recomendación porque la ha traído el adjunto. El acuerdo que queda en el acta no es acuerdo real. | Manuscrito SCAR | Sin publicar: plantéalo como reflexión, sin citar el paper. Muy bueno para residentes. |
| 4 | **Cómo verifico las citas de la IA** (el post de docencia pendiente) | El "paper fantasma": autor real + revista real + título que no existe. | Charla (diapos 47-55) + Whiles, Urology 2023: el 92 % de las respuestas con referencias tenía al menos una cita incorrecta o inexistente | Encaja con el miércoles/jueves ya previsto. |
| 5 | **Hicimos dos apps en el servicio con IA generativa** (STUI adaptativa + MiProstata) | 29 pacientes, mediana de 65 años: usabilidad 95/100 (la media de cualquier app es 68). Los urólogos fueron los más exigentes. | Charla (diapos 32-44) | Se publicará más adelante: **esperar a la publicación** para el post. |
| 6 | **¿En qué punto está de verdad cada IA?** Niveles E1-E5 | Patología digital en E5; IA generativa para decisiones clínicas en E1. | Revisión npj | Esperar a preprint o aceptación. |
| 7 | **La IA que más promete en funcional** | Predicción de respuesta a la toxina botulínica: ~90 % de aciertos con validación externa (Werneburg, Urology 2024). Flujometría por sonido con el móvil. | Charla (diapos 23-27) | Recordar: "precisión del fabricante ≠ precisión independiente". |
| 8 | **"Yo también la uso"**: del estigma a la competencia digital | Antes admitir que usabas IA sonaba a trampa. Hoy las revistas no la prohíben: exigen declararla. | Charla (diapos 4-8, 46) | Post de opinión, sin datos. Bueno para interacción. |
