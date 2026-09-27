# Informe de revisión estricta: manuscrito RVU-RAG

**Manuscrito revisado:** *Structured Curation of Complex Medical Sources Improves Retrieval Accuracy and Guideline Alignment in a Retrieval-Augmented Generation System for Pediatric Vesicoureteral Reflux* (versión JPU del 27/09/2026)
**Revistas objetivo:** JMIR Medical Informatics / International Journal of Medical Informatics (IJMI)
**Agentes aplicados:** Citation Checker · Figure Integrity Checker · Methodology Reviewer · Scientific Reviewer · Reviewer #2

---

## Veredicto global

| Dimensión | Puntuación | Comentario |
|---|---|---|
| Integridad de citas | 92/100 | Sin citas inventadas. Hay 2 referencias ambiguas (ver abajo) |
| Integridad de tablas y figuras | 70/100 | 1 tabla con contenido no verificable que redacté yo; 2 afirmaciones sin ítem identificado |
| Rigor metodológico | 55/100 | Reporte insuficiente frente a TRIPOD-LLM; intervención "empaquetada"; una sola ejecución |
| Significación científica | 60/100 | Contribución real pero incremental; el título promete más de lo que da la Fase 2 |
| Robustez adversarial (Reviewer #2) | 45/100 | La Fase 2 es circular y no ciega; el resultado principal depende de un solo ítem |

**Decisión que tomaría un revisor exigente sobre la versión JPU: *major revision*,** con riesgo real de rechazo en IJMI.

**La versión corregida (JMIR/IJMI) resuelve todo lo que se puede resolver sin datos nuevos.** Lo que no, queda marcado como `[AUTHORS: …]` en el manuscrito. Son datos que solo tenéis vosotros.

---

## 1. Citation Checker

**Método:** DOI y metadatos comprobados contra PubMed; arXiv, MDPI y ACL mediante búsqueda web. CrossRef estaba bloqueado desde este entorno.

| Estado | n | Referencias |
|---|---|---|
| Matched | 18 | AUA/Peters, RIVUR, PREDICT/Morello, Cochrane/Williams, Meena, Arlen, Law, Khondker, Mina-Riascos, Jhaveri, Tullus & Shaikh, ACR/Chandra, VURx/Kirsch, Fang, Neha (AI 2025;6:226), Ceresa (arXiv 2505.04680), Khan (arXiv 2410.15944), Zhang (arXiv 2504.09554, retitulado "Mixture-of-RAG"). Añadida y verificada: TRIPOD-LLM (Nat Med 2025, PMID 39779929) |
| Ambiguous | 2 | **EAU Guidelines**: libro sin DOI, y la edición del corpus es incierta (2024 en el suplementario, 2026 en el texto). **Fang**: PubMed lo registra online el 27/11/2025; no he podido verificar el volumen 41:1097-110 en papel |
| Not found | 0 | — |
| Mismatch (fabricación) | 0 | — |

**Otros hallazgos:**
- **CITE-01 (menor).** La guía española se cita por la edición inglesa (*An Pediatr Engl Ed*, doi …anpede.2024.07.010). Es correcto, pero hay que citar la misma edición que se usó en el corpus.
- **CITE-02 (menor).** Xiong et al. citaba el arXiv; lo cambio a la versión revisada por pares (ACL Findings 2024).

---

## 2. Figure Integrity Checker

No hay figuras, solo tablas (`image_manifest_provided: false`), así que únicamente se hizo el nivel 1, de consistencia textual.

- **FIG-01 (mayor, lo corrijo).** La Tabla 1 de la versión JPU ("contenido complejo por fuente") **la redacté yo por inferencia; no sale de vuestros datos**. En la versión corregida la sustituyo por datos verificables del suplementario: número de ítems y tipo de pregunta por fuente, que suman 50.
- **FIG-02 (mayor, requiere datos).** "In two items the raw-PDF arm failed to retrieve a datum present in the source" no dice qué ítems son. Los únicos con puntuación 0 en PDF son P01 y P17, pero el texto no lo confirma. Hay que identificarlos.
- **FIG-03 (mayor, requiere datos).** Los errores mayores (2 frente a 1) no están asignados a ítems en la Tabla S2. Un revisor pedirá cuáles fueron y de qué tipo.
- **FIG-04 (menor).** Las Tablas S4 y S5 siguen con celdas `[to complete]`. Sin ellas, la Fase 2 no es reproducible.
- **Consistencia numérica:** todas las cifras del abstract, las tablas y el texto cuadran entre sí y con los datos por ítem. Las he recalculado todas.

---

## 3. Methodology Reviewer

**Diseño:** evaluación pareada de dos configuraciones de un sistema basado en LLM, más un componente cualitativo exploratorio.
**Guía aplicable:** **TRIPOD-LLM** (Gallifant et al., Nat Med 2025), que JMIR recomienda para estudios con LLM.

| Elemento TRIPOD-LLM | Estado en la versión JPU |
|---|---|
| Nombre y versión exacta del modelo (snapshot) | ❌ Solo "GPT-4o" |
| Fechas de consulta | ❌ No se indican |
| Parámetros (temperatura, top-p) | ✅ 0 y 1 |
| Configuración de la recuperación (chunking, nº de fragmentos) | ❌ No se indica |
| Prompt completo | ✅ En el suplementario |
| Número de ejecuciones por pregunta y variabilidad | ❌ Una sola ejecución, no declarada |
| Origen y construcción del conjunto de evaluación | ⚠️ Parcial: no dice quién hizo las preguntas ni si fueron previas a la consulta |
| Evaluadores: número, cegamiento, acuerdo | ⚠️ Cegamiento declarado, pero no cómo se ocultó el brazo |
| Disponibilidad de datos (preguntas y respuestas) | ❌ Solo hay puntuaciones; faltan las preguntas y las respuestas literales |
| Detalles de la encuesta (Fase 2) | ❌ Faltan fecha, modo, reclutamiento y tasa de respuesta |

**Hallazgos:**
- **METH-01 (mayor).** El Método dice que "la única diferencia fue el formato". **Es falso tal como está redactado:** la curación reorganiza contenido, añade interpretación, elimina ruido y reduce el corpus de 7 MB a 305 KB. La intervención es un paquete (contenido + formato + tamaño) cuyos componentes no se pueden separar. Hay que redefinirla.
- **METH-02 (mayor).** Las preguntas se diseñaron a propósito sobre datos "difíciles de recuperar de PDFs", y por las mismas personas que hicieron la curación. Esto introduce un **sesgo de diseño a favor del brazo curado**. Debe declararse, junto con si el banco se fijó antes de consultar a los asistentes.
- **METH-03 (mayor).** Hay **una sola respuesta por ítem y brazo.** GPT-4o no es determinista aunque tenga temperatura 0. Sin repeticiones no se puede separar el efecto de la curación de la variabilidad del modelo.
- **METH-04 (mayor).** **El evaluador ciego es codesarrollador** (A.Z.M.). Además, no se explica cómo se ocultó el brazo: si las respuestas citaban nombres de archivo (.pdf frente a .txt), el cegamiento se rompe.
- **METH-05 (mayor).** **La Fase 2 no tiene medida de resultado cuantitativa**, la adjudicación la hicieron los propios desarrolladores sin cegamiento, y faltan los datos de la encuesta.
- **METH-06 (menor).** Hay que justificar el Wilcoxon con aproximación normal. Con empates, el valor exacto condicional da p = 0,027, que conviene dar como análisis de sensibilidad.

---

## 4. Scientific Reviewer

- **Novedad: incremental pero real.** Que los PDF degradan la recuperación en RAG ya se sabe en ingeniería (Khan 2024; RAG con tablas). La aportación está en cuantificarlo con un diseño pareado en un dominio clínico concreto y con evaluación ciega. Encaja en revistas de informática médica, no en revistas clínicas generales.
- **SCI-01 (mayor, lo corrijo).** **El título promete "guideline alignment"**, pero esa parte es cualitativa y exploratoria. Hay que retitularlo alrededor de lo que sí se demuestra (Fase 1) y presentar la Fase 2 como exploratoria.
- **SCI-02 (mayor, lo corrijo).** El abstract y las conclusiones hablan de "auditor clínico-documental" y de valor clínico. Eso excede los datos: no hay pacientes, ni decisiones, ni un resultado clínico medido.
- **SCI-03 (menor, lo corrijo).** No se dice cuánto mejora el sistema en términos útiles para el lector: faltan intervalos de confianza y el desglose por tipo de pregunta. Lo añado: la mejora se concentra en extracción numérica y definiciones, y el punto débil son los algoritmos.
- **Encaje:** JMIR Med Inform (bueno), IJMI (bueno si se endurece la metodología), JPU (bueno por el tema, pero sus lectores son menos técnicos).

---

## 5. Reviewer #2 (en modo "cabrón")

**Lente principal:** la de un revisor metodológico de informática médica. Las lentes de NEJM y European Urology se usaron como secundarias.

**R2-01 (mayor, casi fatal).** El resultado principal es **frágil**: 10 ítems mejoran y 2 empeoran, con McNemar p = 0,039. **Si uno solo de esos 10 ítems pasa a empate, p = 0,065.** Con una única ejecución por ítem, preguntas diseñadas por los autores y puntuación hecha por los propios desarrolladores, un revisor dirá que la significación puede depender de la variabilidad del modelo o de la subjetividad del evaluador.
*Contraargumento de los autores:* la reevaluación ciega mantiene la dirección (11 frente a 2, p = 0,022), el efecto es consistente en varias fuentes y hay un mecanismo plausible (tablas y forest plots). Ayudaría mucho repetir cada pregunta 3-5 veces.

**R2-02 (mayor, compuesto).** **La Fase 2 es circular.** El prompt del evaluador RAG impone la misma jerarquía de fuentes que después se usa para adjudicar, la adjudicación la hacen sus creadores sin cegamiento, y el comparador (Open Evidence) no tenía ese corpus ni esas instrucciones. **Que "el RAG sale mejor alineado con la guía" es casi tautológico.**
*Contraargumento:* la Fase 2 no pretende demostrar superioridad, sino mostrar que acuerdo con expertos, acuerdo entre IA y alineamiento con la guía son desenlaces distintos. Esa conclusión se sostiene aunque la comparación no sea justa. **Para que el argumento valga hay que presentarla así, de forma explícita.**

**R2-03 (mayor).** **Confusión de la intervención.** La mejora puede deberse simplemente a que el corpus es 23 veces más pequeño (menos ruido para el recuperador) y no a la "estructura". Sin un brazo intermedio (PDF convertido a texto plano sin curar) no se puede atribuir el efecto a la curación.
*Contraargumento:* para el usuario clínico, el paquete completo es lo relevante. Pero entonces el título y las conclusiones deben hablar de "curación" en general, no de "formato" ni de "estructura".

**R2-04 (menor).** Validez externa: un solo modelo, una sola plataforma (OpenAI File Search, que cambia su parser con el tiempo) y un solo dominio.

**R2-05 (menor, divulgación).** Los autores evalúan su propia herramienta y difunden los resultados en redes sociales antes de publicar. No es motivo de rechazo, pero el conflicto de interés debe declararse con claridad, y ya se hace.

**Rejection case:**
- **Argumento más fuerte:** R2-01 + R2-02 juntos. Un efecto pequeño y frágil medido por los desarrolladores, más una Fase 2 circular, permiten argumentar que el artículo no demuestra nada más allá de un informe de experiencia.
- **¿Rechazaría un revisor razonable?** **Sí, en IJMI con la versión JPU. No, si se reencuadra** (Fase 1 como resultado principal con incertidumbre honesta, Fase 2 como exploratoria generadora de hipótesis) y se completan los datos de reporte.

---

## 6. Qué he corregido yo y qué os toca a vosotros

### Corregido en la nueva versión (JMIR / IJMI)
1. **Nuevo título**, centrado en la Fase 1; la Fase 2 pasa a ser "exploratoria".
2. **La intervención se describe como paquete** (contenido + formato + tamaño), sin afirmar que solo cambiaba el formato.
3. **Intervalos de confianza:** diferencia de correctas +16 pp (IC 95 %: 2-30, Newcombe) y diferencia media de puntuación 0,20 (IC 95 %: 0,06-0,36, bootstrap).
4. **Análisis de fragilidad** declarado: basta 1 ítem para perder la significación.
5. **Wilcoxon exacto** (p = 0,027) como sensibilidad.
6. **Desglose de ítems discordantes** por tipo y fuente (Tabla 3), sacado de vuestros datos.
7. **Tabla 1 rehecha** con datos verificables (ítems por fuente).
8. **Circularidad y falta de cegamiento de la Fase 2** declaradas en Métodos y Limitaciones; se retiran las afirmaciones de "valor clínico".
9. **Limitaciones reescritas** a fondo: sesgo de diseño del banco, una sola ejecución, evaluadores no independientes, tamaño del corpus.
10. **TRIPOD-LLM:** citado y con su checklist en el suplementario (Tabla S6).
11. **Formato JMIR Medical Informatics** (abstract de 450 palabras como máximo con Background/Objective/Methods/Results/Conclusions, Principal Findings, Comparison With Prior Work, Abbreviations, Multimedia Appendix) y **formato IJMI** (abstract más corto, Highlights, Summary table "What was already known / What this study added", declaraciones de Elsevier).

### ⚠️ Lo que tenéis que aportar (marcado `[AUTHORS: …]` en el manuscrito)
1. **Snapshot exacto del modelo** (p. ej. `gpt-4o-2024-08-06`) y **fechas** de las consultas.
2. **Configuración de File Search:** tamaño de fragmento y solapamiento (por defecto 800/400 tokens) y número máximo de resultados.
3. **Quién diseñó las preguntas y cuándo** (antes o después de ver respuestas).
4. **Cómo se cegó la reevaluación:** si se quitaron nombres de archivo o citas que delataran el brazo, y si el orden fue aleatorio.
5. **Qué ítems fueron errores mayores** y **cuáles los 2 fallos de recuperación.**
6. **Encuesta SIUP:** fechas, modo (online o en congreso), cómo se reclutó, cuántos invitados frente a 30 respondedores, y consentimiento. Además, las Tablas S4 y S5 completas.
7. **Fecha y modo de consulta de Open Evidence.**
8. **Muy recomendable antes de enviar:** repetir las 50 preguntas **3 veces por brazo**. Son unas 300 consultas y una tarde de trabajo, y desactiva el R2-01, el ataque más peligroso.
9. **Opcional pero potente:** un tercer brazo con el PDF pasado a texto plano sin curar. Separaría el efecto del formato del efecto de la curación y desactivaría el R2-03.
10. **Preguntas y respuestas literales** como material suplementario (JMIR lo valora mucho).

### ⚠️ Recordatorio de integridad
Si el manuscrito en español para *Cirugía Pediátrica* sigue activo, **no se puede enviar esta versión a ninguna revista** sin retirarlo o declararlo, porque comparten los resultados de la Fase 1. Lo mismo aplica si llegasteis a enviar la versión a JPU: **una sola revista a la vez.**
