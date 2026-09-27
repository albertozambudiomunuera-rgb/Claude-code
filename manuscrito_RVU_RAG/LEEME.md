# Manuscrito RVU-RAG: paquete para *Journal of Pediatric Urology*

| Archivo | Qué es |
|---|---|
| `Manuscript_RVU_RAG_JPU_blinded.docx` | Manuscrito anonimizado: abstract, Summary + Summary Table, texto, 3 tablas, referencias, numeración de líneas |
| `Supplementary_Material_RVU_RAG_JPU.docx` | Apéndice S1 (prompt) + tablas S1 a S5 |
| `Title_Page_RVU_RAG_JPU.docx` | Portada con autores, afiliaciones, contribuciones (CRediT), ética, conflictos y financiación |
| `Cover_Letter_RVU_RAG_JPU.docx` | Carta al editor, con el párrafo sobre el manuscrito en español |

## Cambios respecto a la v0.9
- **Tablas añadidas:** Tabla 1 (corpus de 12 fuentes), Tabla 2 (resultados de la fase 1 + reevaluación ciega) y Tabla 3 (ítems clave de la fase 2), más la Summary Table.
- **Evaluación ciega en el texto principal:** añadida a Métodos y Resultados, y eliminada de las limitaciones la frase que decía que faltaba. Datos recalculados a partir de las puntuaciones:
  - Reevaluación ciega: 82 vs 93, completas 34 vs 43, McNemar p = 0,022.
  - κ ponderado cuadrático: 0,87 (PDF) y 0,74 (texto).
- **Estadística verificada.** Wilcoxon p = 0,0187 (aproximación normal), McNemar exacto p = 0,0386 y test de signos p = 0,0386 coinciden con el original.
- **Hallazgo nuevo del suplementario:** los 2 ítems en los que ganó el PDF (P04 y P10) son ambos de algoritmos. Lo he añadido a Resultados y Discusión como matiz honesto.
- **Fase 2, versión reconciliada:** las respuestas se generaron con el evaluador de texto curado y el prompt S1. Cochrane, ACR, Tullus y VURx se usaron solo para adjudicar y no estaban en el corpus. Es lo que decía la v0.7.
- **Referencias:**
  - Xiong: cito la versión publicada en ACL Findings 2024 en lugar del arXiv.
  - Fang: añado volumen y páginas (2026;41:1097-110).
  - Zhang (arXiv 2504.09554): comprobado, el título actual es "Mixture-of-RAG".
- **Declaración de IA:** añadido Claude junto a ChatGPT, porque se ha usado en esta versión.

## ⚠️ Pendiente antes de enviar
1. **Tabla S4:** completar con los datos de la encuesta SIUP (pregunta, opciones, % de la mayoría experta, respuesta de Open Evidence y respuesta del RAG). No los tengo.
2. **Tabla S5:** completar las filas P2, P3, P6 y P7 y las celdas marcadas `[to complete]`. La clasificación de Open Evidence en P1 ("partially aligned / oversimplified") es una propuesta mía a partir del texto.
3. **Confirmar la fase 2:** que las respuestas son del evaluador de texto curado con el mismo prompt y el corpus de 12 fuentes. Si no, cambiar Métodos.
4. **Guía EAU:** ¿qué edición había en el corpus? El suplementario antiguo dice 2024 y la v0.9 cita 2026.
5. **Portada:** confirmar la lista de autores, el nombre completo de S. Altamirano y el reparto CRediT, que es una propuesta.
6. **Carta:** elegir la opción (a) o (b) sobre el manuscrito de *Cirugía Pediátrica*.
7. **Guía de autores de JPU** (límites comprobados: 3000 palabras, abstract de 400, 30 referencias, 4 tablas o figuras):
   - Este manuscrito tiene unas 2320 palabras, 21 referencias y 3 tablas más la Summary Table.
   - Revisar en el portal los encabezados exactos del abstract y el formato de la Summary Table o Figure.
