# RVU + RAG: resumen de versiones, cuál es la buena y post

## 1. Qué hay en cada archivo

| Archivo | Qué es | Contenido | Estado |
|---|---|---|---|
| `Manuscrito_RVU_RAG_Cirugia_Pediatrica_anonimizado_FINAL` (.docx y .pdf) | Artículo en español para *Cirugía Pediátrica* | Descripción de la herramienta (web + formulario + webhook + GPT-4o con RAG, temperatura 0) + evaluación de 50 preguntas con PDF frente a texto curado (84 vs 94/100), sin estadística | El .docx y el .pdf son **idénticos** |
| `RVU_RAG_v0_7` | Versión en inglés, 4 autores | **Fase 1** (50 preguntas, con Wilcoxon y McNemar) + **Fase 2** (11 casos: 30 expertos SIUP vs Open Evidence vs RAG). Incluye tablas 1 y 2 y un apartado de "refinamiento posterior" | Versión anterior (es la misma que me pasaste la primera vez) |
| `RVU_RAG_v0_9_JPU_corrected` | La v0.7 corregida para *J Pediatr Urol*, anonimizada | Mismo contenido que la v0.7, más limpio. Las referencias están reordenadas y se ha quitado el apartado de refinamiento | **La más avanzada** |
| `Supplementary_Material` | Material suplementario | Prompt completo, rúbrica, puntuación de las 50 preguntas y **evaluación ciega por ti (κ 0,87 / 0,74)** | Es de una versión antigua que **solo tenía la Fase 1** (título distinto, 2 autores) |

## 2. ¿Cuál es el mejor artículo?

**La v0.9 para JPU**, sin duda. Ya reúne todo: la Fase 1 con estadística y la Fase 2 con los expertos SIUP, que es lo que le da interés clínico. No hace falta escribir uno nuevo que lo aúne; hace falta **cerrarla**, porque tiene fallos.

### Problemas que hay que arreglar antes de enviarla o reenviarla

1. **⚠️ Publicación duplicada.** El artículo en español y el de JPU publican **el mismo experimento de 50 preguntas con los mismos resultados (84 vs 94)**. Si están los dos enviados a la vez, los editores pueden considerarlo publicación redundante. Hay dos opciones:
   - **(recomendada)** Retirar el de *Cirugía Pediátrica* o reconvertirlo en una nota técnica sobre cómo se construyó la herramienta web, sin repetir los resultados y citando el de JPU.
   - O declarar el otro manuscrito a ambos editores en la carta de presentación.
2. **Faltan las tablas en la v0.9.** El texto remite a "Table 1" y "Table 2", pero el .docx no tiene ninguna tabla. Están en la v0.7: hay que copiarlas.
3. **El suplementario no corresponde a la v0.9.** La v0.9 anuncia S1 (preguntas), S2 y S2b (fase 2 SIUP), S3 (matriz de adjudicación), S4 (notas metodológicas) y S5 (prompt de la fase 2). El archivo que tienes tiene otra numeración, no incluye nada de la fase 2 y trae el prompt de la fase 1. Hay que rehacerlo.
4. **Contradicción en las limitaciones.** La v0.9 dice que *"independent blinded assessment and inter-rater reliability should be included in future work"*, pero **ya lo hicisteis**: tú puntuaste las 50 preguntas a ciegas, con κ 0,87 en el brazo PDF y 0,74 en el de texto, y el resultado se reprodujo (93 vs 82). Eso es una fortaleza: súbelo al texto principal (Métodos + Resultados) y quita esa frase de las limitaciones.
5. **¿Con qué prompt se generaron las respuestas de la fase 2?**
   - La v0.7 decía que se usó el evaluador **original** y que el corpus se amplió **después** (Cochrane, ACR, Tullus, VURx), sin usarse en las respuestas analizadas.
   - La v0.9 dice que se usó el prompt del **Apéndice S5** y ya cita esas fuentes en la adjudicación.
   - Hay que dejar claro cuál es la verdad: si las respuestas son del evaluador original, la v0.9 tiene que decirlo así.
6. **Autoría.** La v0.7 tiene 4 autores (Gerardo, tú, Somoza y Altamirano), pero el suplementario solo 2. Confirmad la lista final. El conflicto de interés (que evaluáis vuestra propia herramienta) y la exención del comité de ética tienen que ir en la title page.

## 3. Resumen en 30 segundos (para ti)

- **Pregunta:** ¿basta con subir las guías en PDF a una IA?
- **Fase 1:** mismo GPT-4o, mismo prompt y 50 preguntas difíciles (datos en tablas, forest plots, scores); lo único que cambia es el formato de las 12 fuentes.
  - PDF 84/100 frente a texto curado 94/100.
  - Respuestas correctas: 72 % frente a 88 % (McNemar p = 0,039).
  - Tu evaluación a ciegas reproduce el resultado.
- **Fase 2:** 11 casos clínicos, 30 urólogos pediátricos SIUP con más de 10 años de experiencia, Open Evidence y el RAG.
  - Coincidir con la mayoría de expertos, coincidir con otra IA y estar alineado con la guía **no son lo mismo**.
  - El RAG detecta opciones incompletas, preguntas sin respuesta única en las guías y la diferencia entre vigilar (profilaxis) y corregir la enfermedad (cirugía).
- **Mensaje:** la calidad de una IA clínica depende tanto de **qué documentos le das y cómo** como del modelo.

## 4. POST (versión con tu padre)

> Este estudio tiene algo especial: lo he hecho con mi padre.
>
> Él, cirujano pediátrico en la sección de Urología Pediátrica de la Arrixaca, pone el criterio clínico. Yo, la parte de IA. Queríamos responder una pregunta sencilla: ¿basta con subir las guías en PDF a una IA para que responda bien?
>
> Spoiler: no.
>
> 📄 **Primera parte: ¿importa cómo le das los documentos?**
> Construimos un evaluador con RAG para reflujo vesicoureteral pediátrico. Mismo modelo, mismas instrucciones y 50 preguntas. Lo único que cambiaba era el formato de las 12 fuentes (guías, ensayos, metaanálisis, scores): el PDF original o un texto curado a mano, con las tablas y los scores pasados a texto explícito.
> • Puntuación: 84 → 94 sobre 100
> • Respuestas completamente correctas: 72 % → 88 %
> • En algunas preguntas el dato estaba en el PDF… y la IA no lo encontraba.
> Yo volví a puntuar las 50 respuestas a ciegas, sin saber cuál era cuál, y el resultado se mantuvo.
>
> 👩‍⚕️ **Segunda parte: IA frente a expertos**
> 11 casos clínicos respondidos por 30 urólogos pediátricos de la SIUP (todos con más de 10 años de experiencia), por Open Evidence y por nuestro evaluador.
> Lo que más me ha hecho pensar: coincidir con la mayoría de expertos, coincidir con otra IA y estar alineado con la guía son tres cosas distintas.
> • En un reflujo grado IV-V que persiste, seguir con profilaxis es vigilar, no tratar el reflujo.
> • Cuando las guías no dan una única respuesta, lo honesto es decirlo, no elegir una opción del test.
>
> Lo que me llevo:
> 1️⃣ Antes de preguntarte qué modelo usar, pregúntate qué documentos le das y en qué formato.
> 2️⃣ Que responda con seguridad no significa que acierte.
>
> Limitaciones, que las hay: la herramienta la evaluamos nosotros, las preguntas son nuestras y falta validación externa y prospectiva.
>
> [SI SE CONFIRMA] Lo presentamos en el Congreso de la SIUP en Lima (7-10 de octubre). Si vas a estar, nos vemos allí 🇵🇪
>
> Y sí: investigar con tu padre es de lo mejor que me ha dado la residencia.
>
> #UrologíaPediátrica #ReflujoVesicoureteral #InteligenciaArtificial #RAG #SaludDigital

**Antes de publicar:**
- Etiqueta a tu padre (y a Iván Somoza y Altamirano, si siguen como autores: "con la colaboración de…").
- Confirma que se presenta en la SIUP. Si no, quita esa línea.
- JPU y *Cirugía Pediátrica* hacen revisión anonimizada. Un post con autores y resultados puede romper el anonimato de la revisión. Si quieres ir sobre seguro, publícalo coincidiendo con la presentación en el congreso, que sí es pública.
