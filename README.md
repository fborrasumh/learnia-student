# LEARNIA Student

La IA que no estudia por ti. Te enseña a aprender. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/learnia-student/

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23218258.svg)](https://doi.org/10.5281/zenodo.23218258)

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- Importa `curso.learnia.json` (contrato `learnia-course/1`) y guarda tu progreso en IndexedDB.
- **¿Qué sé?**: diagnóstico sin pistas; perfil por tema y prioridad (p. ej. «Energía, pero antes refuerza Trabajo → Energía»).
- **Entender un tema**: tutor socrático con turnos limitados. Usa los materiales del curso (búsqueda local BM25), cita fuente y página y el código comprueba cada cita literal; sin clave muestra los pasajes del curso.
- **Practicar**, **Preparar examen** (entrenamiento adaptativo) y **¿Qué debería hacer ahora?** (plan de 5/15/30 minutos): selección por dominio, prerrequisitos débiles, errores recurrentes y olvido.
- **Resolver un problema**: Problem Coach con 5 niveles de pistas; la solución no se da de golpe y un filtro de código elimina de las respuestas de la IA cualquier frase que revele el resultado.
- **Explícamelo** (Feynman): cobertura de términos clave comprobada por código; con IA, la nota la calcula el código a partir de la rúbrica y las observaciones sin cita literal se descartan.
- **Recuperar un error**: error → diagnóstico → prerrequisito → microexplicación → actividad → nuevo intento → comprobación.
- **Mi progreso**: dominio, competencias, evolución semanal, errores frecuentes y perfil cognitivo (dominio, confianza, intentos, tendencia, retención, independencia).
- Exporta e importa tu aprendizaje en JSON (`student.learnia.json`); al importar las evidencias se unen sin duplicados y el dominio se recalcula con las mismas reglas.
- Funciona sin conexión para lo determinista; la IA (OpenAI, Gemini o Claude con tu clave) solo se usa en tutoría, feedback y microexplicaciones.

## Cómo se calcula el dominio

Regla fija y reproducible: media móvil de la puntuación de cada evidencia, ponderada por dificultad, penalizada por pistas e intentos y por errores repetidos, con retención exponencial en el tiempo. La IA no decide estos números.

## Privacidad

El perfil del estudiante (intentos, errores, evidencias y conversaciones) vive en IndexedDB de este navegador. No hay cuentas, servidor ni tracking. Al pedir tutoría o feedback a la IA solo sale lo que escribes, con tu nombre, correos, teléfonos y DNI enmascarados, más extractos del material del curso; antes del primer envío se muestra una muestra y hay que confirmar. La clave de IA se guarda solo en el navegador. El fichero que exportas contiene identificador pseudónimo, progreso, dominio, competencias, actividades, errores, evidencias y estadísticas (nombre y código solo si los marcas); no incluye conversaciones ni la clave.

## Límites

Probada con IA simulada (suites automáticas de extremo a extremo), no con claves reales; la IA puede equivocarse y todo lo generado debe revisarlo el profesor o el estudiante. Los pesos y umbrales del algoritmo de dominio y de las recomendaciones son heurísticos y no están validados empíricamente. El PDF del informe no se genera directamente. Para uso institucional con clave compartida haría falta un proxy seguro, no incluido.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche).


ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. (2026). *LEARNIA Student* (v1.0.0) [Software]. DOI: [10.5281/zenodo.23218258](https://doi.org/10.5281/zenodo.23218258)

## Licencia

MIT. Véase [LICENSE](LICENSE).
