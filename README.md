Prompt:
# PRODUCT REQUIREMENTS DOCUMENT (PRD)

# Exam Engine 2.0
## Módulo Generador de la Parte 3 – Short Conversations (Saber 11 – ICFES)
### EDICIÓN 100% OFFLINE – SIN INTERNET, SIN BACKEND Y SIN APIs

---

## Objetivo general

Desarrollar una aplicación web capaz de generar y presentar automáticamente pruebas equivalentes a la Parte 3 del examen de Inglés del Saber 11 (ICFES).

La aplicación NO debe producir ejercicios tradicionales de inglés.

Debe generar evaluaciones que reproduzcan fielmente el diseño del ICFES tanto en estructura visual como en intención pedagógica y psicométrica.

### REGLA FUNDAMENTAL DE ESTA VERSIÓN

La aplicación terminada debe tener **funcionalidad 100% offline**.

Debe funcionar con el computador completamente desconectado de Internet y abrirse directamente mediante doble clic sobre `index.html`.

**NO debe necesitar:**

- Internet
- localhost
- servidor local
- Node.js
- npm
- Vite
- Live Server
- backend
- API
- API Key
- base de datos remota
- CDN
- servicios cloud
- autenticación externa
- conexión con modelos de Inteligencia Artificial durante la ejecución

La IA puede utilizarse durante el desarrollo para crear y revisar el banco de contenidos, pero **la aplicación terminada NO puede depender de una IA para generar contenido en tiempo de ejecución**.

La generación automática debe realizarse mediante un **motor local de plantillas, reglas, combinaciones y banco de ítems previamente construido**.

---

# Principio de funcionamiento offline

La aplicación debe ser **local-first**.

Todo lo necesario para ejecutar la aplicación debe estar incluido dentro del proyecto.

La aplicación debe poder copiarse, por ejemplo, a una memoria USB y ejecutarse en otro computador sin instalar software adicional.

Flujo mínimo obligatorio:

```text
Copiar carpeta
      ↓
Doble clic en index.html
      ↓
Seleccionar / generar prueba
      ↓
Responder
      ↓
Calificar
      ↓
Revisar resultados
      ↓
Exportar / imprimir
```

Todo este flujo debe funcionar sin conexión a Internet.

---

# Prohibiciones absolutas

La aplicación terminada NO debe utilizar:

- `fetch()`
- `XMLHttpRequest`
- Axios
- REST API
- GraphQL
- WebSockets
- APIs externas
- servicios de IA externos
- OpenAI
- Gemini
- Claude
- Pollinations
- Firebase
- Supabase
- bases de datos remotas
- URLs HTTP/HTTPS para cargar recursos
- imágenes remotas
- fuentes remotas
- Google Fonts
- Font Awesome remoto
- Bootstrap CDN
- Tailwind CDN
- cualquier `<script src="https://...">`
- cualquier `<link href="https://...">`
- cualquier `<img src="https://...">`
- analítica externa
- publicidad
- recursos que requieran conexión a Internet

No debe existir ninguna llamada de red durante la ejecución.

---

# Ejecución mediante file://

La aplicación debe funcionar directamente mediante:

```text
file:///.../index.html
```

No debe requerir un servidor HTTP.

Para garantizar la compatibilidad con `file://`, se recomienda que:

- el HTML sea autocontenido;
- el CSS esté incluido localmente;
- el JavaScript esté incluido localmente;
- el banco de preguntas esté embebido en JavaScript o en un bloque `<script type="application/json">` dentro del HTML;
- no se utilicen módulos ES que dependan de rutas externas;
- no se utilice `fetch()` para leer archivos JSON locales.

---

# Referencia

La aplicación deberá tomar como referencia el formato oficial del cuadernillo Saber 11.

Debe conservar:

- organización visual
- longitud
- distribución
- dificultad
- número de preguntas
- estilo de redacción
- tipo de distractores
- propósito comunicativo

No copiar preguntas reales.

Debe generar nuevo contenido siguiendo la misma lógica evaluativa.

---

# Competencia evaluada

La aplicación debe construir preguntas que evalúen únicamente competencias comunicativas.

No debe evaluar gramática aislada.

Las preguntas deberán medir:

- comprensión de turnos de habla
- intención comunicativa
- actos de habla
- inferencia inmediata
- adecuación pragmática
- funciones del lenguaje
- uso cotidiano del inglés

---

# Estructura del examen

Cada prueba tendrá exactamente:

```text
Example (0)
Questions 1–10
```

El Example nunca se califica.

Debe aparecer antes de la pregunta 1.

La respuesta correcta debe mostrarse marcada en el Example.

Las preguntas 1–10 no mostrarán la respuesta antes de ser calificadas.

---

# Conversaciones

Cada pregunta consistirá en un intercambio breve.

Un hablante expresa una idea.

El estudiante debe escoger la respuesta más apropiada.

Cada conversación debe representar una situación auténtica.

Ejemplos de contexto:

- escuela
- familia
- restaurante
- compras
- salud
- vacaciones
- deportes
- transporte
- clima
- tecnología
- tiempo libre
- amigos

---

# Nivel lingüístico

Marco Común Europeo:

```text
A2 – B1
```

El vocabulario deberá ser cotidiano.

No utilizar expresiones demasiado técnicas.

No utilizar lenguaje académico innecesario.

---

# Número de opciones

Cada pregunta tendrá exactamente tres opciones:

```text
A
B
C
```

Nunca cuatro.

---

# Diseño psicométrico

Cada conversación debe evaluar solamente una intención comunicativa.

Ejemplos:

- apologizing
- thanking
- accepting
- refusing
- agreeing
- disagreeing
- inviting
- offering help
- requesting information
- giving advice
- congratulating
- expressing sympathy
- expressing surprise
- expressing preferences
- asking for clarification

No mezclar varias competencias en una misma pregunta.

---

# Distractores

Los distractores deberán cumplir todas estas condiciones:

✔ Ser gramaticalmente correctos.

✔ Tener longitud similar.

✔ Pertenecer al mismo contexto.

✔ Ser plausibles.

✔ No ser absurdos.

✔ Representar otra intención comunicativa.

Nunca construir distractores obviamente incorrectos.

---

# Ejemplo

Speaker A

"I'm going to Vancouver next week."

Opciones:

A
That's great!

B
I like swimming.

C
You are first.

Las tres opciones son gramaticalmente correctas.

Solo una responde adecuadamente al contexto.

---

# Ejemplo obligatorio

Siempre generar un Example numerado como 0.

Debe contener:

- conversación
- tres opciones
- respuesta correcta marcada
- no calificable

Nunca omitir el Example.

---

# Motor local de generación

## REEMPLAZO DE IA EN TIEMPO DE EJECUCIÓN

La versión offline NO utilizará Inteligencia Artificial para generar conversaciones mientras el usuario utiliza la aplicación.

En su lugar, deberá existir un motor local capaz de generar pruebas nuevas combinando contenido previamente validado.

El motor podrá utilizar:

- banco local de conversaciones;
- plantillas de situaciones;
- plantillas de actos de habla;
- bancos de respuestas;
- bancos de distractores;
- reglas de compatibilidad semántica;
- reglas de dificultad;
- selección aleatoria local;
- combinaciones previamente validadas;
- metadatos psicométricos.

Toda esta información deberá estar incluida dentro del proyecto.

La aplicación podrá generar una prueba diferente en cada ejecución sin necesidad de conectarse a Internet.

---

# Banco local de contenidos

El proyecto deberá incluir un banco suficientemente amplio de conversaciones previamente creadas y revisadas.

Se recomienda un mínimo de:

```text
100 ítems de conversación
```

para permitir múltiples combinaciones de pruebas.

Cada ítem deberá incluir:

- contexto;
- diálogo;
- tres opciones;
- respuesta correcta;
- intención comunicativa;
- acto de habla;
- dificultad;
- nivel;
- registro;
- metadatos psicométricos.

El contenido debe estar almacenado localmente.

No cargarlo mediante `fetch()`.

---

# Aleatoriedad local

El motor podrá utilizar:

```javascript
Math.random()
```

para:

- seleccionar conversaciones;
- seleccionar contextos;
- variar el orden de los ítems;
- variar el orden de las opciones cuando sea seguro hacerlo.

La respuesta correcta debe permanecer correctamente asociada a su opción.

No utilizar servicios externos para generar números aleatorios.

---

# Motor psicométrico

Cada pregunta deberá incluir metadatos invisibles para el estudiante.

Ejemplo:

```json
{
  "competency": "communicative competence",
  "speechAct": "requesting information",
  "communicativeFunction": "asking for information",
  "difficulty": "A2",
  "register": "informal",
  "context": "transport",
  "correctAnswer": "B"
}
```

Estos datos permitirán generar retroalimentación personalizada sin necesidad de servicios externos.

---

# Validaciones automáticas locales

Antes de presentar una prueba, el sistema deberá verificar automáticamente:

✓ Existe una única respuesta correcta.

✓ Todos los distractores son plausibles.

✓ El inglés es natural.

✓ El vocabulario corresponde al nivel A2–B1.

✓ La conversación representa una situación real.

✓ La respuesta correcta satisface la intención comunicativa.

✓ El Example aparece antes de la pregunta 1.

✓ Existen exactamente 10 preguntas calificables.

✓ Cada pregunta tiene exactamente tres opciones.

✓ No existen preguntas duplicadas dentro de la misma prueba.

Si un ítem no supera las validaciones, el motor deberá descartarlo y seleccionar otro ítem local válido.

---

# Interfaz de usuario

La aplicación deberá permitir:

- generar una nueva prueba con un clic;
- visualizar el diálogo en formato similar al ICFES;
- representar gráficamente a los hablantes mediante ilustraciones o avatares locales;
- editar cualquier conversación antes de exportarla;
- regenerar únicamente una pregunta utilizando contenido local;
- modificar el contexto de una conversación mediante opciones disponibles en el banco local;
- cambiar el nivel de dificultad entre los niveles disponibles en el banco;
- visualizar la clave de respuestas;
- ocultar o mostrar el Example;
- imprimir el examen;
- guardar el examen como PDF mediante la función de impresión del navegador;
- exportar a HTML;
- exportar el examen en formato JSON compatible con Exam Engine 2.0.

### Exportación a Word

Si se implementa exportación a Word, debe funcionar completamente offline.

No utilizar una API externa para crear documentos.

La solución podrá:

1. incluir dentro del proyecto una biblioteca local necesaria para generar `.docx`, o
2. generar un documento HTML compatible con Microsoft Word si la prioridad es mantener el proyecto liviano.

La aplicación nunca deberá enviar el contenido a un servidor para crear el documento.

---

# Exportación a PDF

La exportación a PDF debe funcionar sin Internet.

La solución preferida será:

```javascript
window.print();
```

acompañada de estilos:

```css
@media print {
  /* diseño del examen para impresión */
}
```

El usuario podrá seleccionar:

```text
Guardar como PDF
```

desde el diálogo de impresión del navegador.

No utilizar un servicio PDF externo.

---

# Arquitectura

La aplicación deberá ser modular a nivel lógico, pero deberá poder ejecutarse sin servidor.

Estructura conceptual:

```text
part3/
│
├── index.html
├── README.md
├── assets/
│   ├── avatars/
│   └── icons/
└── data/
    └── exam-bank.js
```

Sin embargo, para garantizar compatibilidad con `file://`, el agente podrá integrar CSS, JavaScript y datos directamente dentro de `index.html`.

No es obligatorio separar los archivos si hacerlo perjudica la ejecución directa offline.

La arquitectura lógica deberá mantener módulos equivalentes a:

```text
┌──────────────────────────┐
│      AppController       │
├──────────────────────────┤
│ LocalExamGenerator       │
│ LocalItemBank             │
│ PsychometricValidator    │
│ ConversationRenderer     │
│ AnswerManager            │
│ Scoring                  │
│ ExportManager            │
└──────────────────────────┘
```

Cada responsabilidad deberá estar claramente separada en el código.

---

# Formato JSON esperado

Cada prueba deberá devolverse con la siguiente estructura:

```json
{
  "part": 3,
  "title": "Short Conversations",
  "instructions": "Choose the best response.",
  "example": {},
  "questions": [],
  "answerKey": [],
  "metadata": {}
}
```

El JSON deberá generarse localmente en memoria.

No deberá enviarse a ningún servicio externo.

---

# Persistencia local

La aplicación podrá utilizar `localStorage` exclusivamente para guardar información local, como:

- preferencia de tema;
- último examen seleccionado;
- resultados recientes;
- configuración local;
- progreso de una sesión.

Nunca sincronizar esta información con Internet.

Debe existir una opción para borrar los datos locales.

---

# Estado del examen

El sistema deberá controlar como mínimo:

```javascript
currentExam
currentQuestion
answers
score
examStarted
examFinished
```

Debe impedir:

- modificar respuestas bloqueadas;
- duplicar puntuaciones;
- contar el Example;
- finalizar incorrectamente una prueba;
- perder accidentalmente las respuestas sin confirmación.

---

# Scoring

El sistema deberá calcular localmente:

- respuestas correctas;
- respuestas incorrectas;
- porcentaje;
- desempeño general;
- tiempo empleado si se incorpora cronómetro.

El Example 0 nunca contará para la puntuación.

Las preguntas 1–10 serán las únicas calificables.

---

# Cronómetro opcional

Si se incorpora cronómetro, deberá funcionar exclusivamente mediante JavaScript local.

No utilizar servicios externos para medir el tiempo.

Debe:

- iniciar al comenzar la prueba;
- mostrar el tiempo transcurrido;
- detenerse al finalizar;
- registrar el tiempo final localmente.

---

# Diseño visual

La interfaz deberá ser profesional y responsive.

Debe funcionar en:

- computadores;
- tablets;
- teléfonos.

Se recomienda utilizar:

- CSS moderno;
- variables CSS;
- tarjetas;
- bordes redondeados;
- sombras suaves;
- transiciones;
- estados visuales de respuesta;
- barra de progreso;
- modo claro y oscuro.

No cargar fuentes desde Internet.

Utilizar fuentes del sistema, por ejemplo:

```css
font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
```

Los iconos deberán ser:

- SVG inline;
- CSS;
- Unicode;
- o archivos SVG locales.

---

# Avatares e ilustraciones

Si se utilizan avatares para los hablantes, todos deberán estar incluidos localmente.

No utilizar imágenes remotas.

No generar imágenes mediante IA durante la ejecución.

Los recursos podrán ser:

- SVG locales;
- PNG locales;
- ilustraciones CSS;
- avatares previamente creados.

---

# Restricciones de contenido

La aplicación nunca deberá generar:

✘ ejercicios de gramática

✘ traducciones

✘ ejercicios de completar espacios

✘ preguntas de vocabulario aislado

✘ respuestas absurdas

✘ conversaciones artificiales

✘ frases traducidas literalmente desde el español

Todo el contenido debe parecer escrito originalmente en inglés.

---

# Restricciones sobre IA

La IA agéntica puede utilizarse durante el desarrollo para:

- diseñar el banco de conversaciones;
- revisar la calidad lingüística;
- revisar distractores;
- generar metadatos;
- construir el código;
- realizar validaciones durante el desarrollo.

Pero la aplicación instalada en el dispositivo **NO puede llamar a una IA durante la ejecución**.

No debe existir ningún botón del tipo:

```text
Generate with AI
```

que requiera Internet.

El botón "Nueva prueba" debe utilizar exclusivamente el banco local y el motor de generación local.

---

# Prueba de funcionamiento offline

Antes de entregar la aplicación, la IA agéntica deberá comprobar conceptualmente el siguiente escenario:

### Prueba 1

Abrir `index.html` mediante doble clic.

### Prueba 2

Desconectar completamente Wi-Fi y Ethernet.

### Prueba 3

Recargar la aplicación.

### Prueba 4

Generar una nueva prueba.

### Prueba 5

Responder las preguntas 1–10.

### Prueba 6

Calificar la prueba.

### Prueba 7

Mostrar la clave y retroalimentación.

### Prueba 8

Regenerar una pregunta utilizando únicamente el banco local.

### Prueba 9

Cambiar el tema visual.

### Prueba 10

Imprimir o guardar el examen como PDF.

Todas estas funciones deben continuar funcionando sin Internet.

---

# Lista de verificación técnica obligatoria

Antes de entregar la aplicación, revisar:

- [ ] No existe `fetch()`.
- [ ] No existe `XMLHttpRequest`.
- [ ] No existe Axios.
- [ ] No existen APIs externas.
- [ ] No existen llamadas HTTP/HTTPS.
- [ ] No existen imágenes remotas.
- [ ] No existen fuentes remotas.
- [ ] No existen scripts remotos.
- [ ] No existen hojas de estilo remotas.
- [ ] No existe backend.
- [ ] No existe base de datos remota.
- [ ] No existe Pollinations.
- [ ] No existe OpenAI.
- [ ] No existe Gemini.
- [ ] No existe Claude.
- [ ] No existe generación de IA durante la ejecución.
- [ ] El banco de conversaciones está almacenado localmente.
- [ ] La generación de pruebas funciona mediante lógica local.
- [ ] La pregunta 0 no se califica.
- [ ] Las preguntas 1–10 sí se califican.
- [ ] Cada pregunta tiene A, B y C.
- [ ] La respuesta correcta está correctamente asociada.
- [ ] El motor puede generar una nueva prueba sin Internet.
- [ ] La regeneración de una pregunta funciona sin Internet.
- [ ] El modo claro/oscuro funciona sin Internet.
- [ ] La puntuación funciona sin Internet.
- [ ] La impresión/PDF funciona sin Internet.
- [ ] La aplicación funciona mediante doble clic sobre `index.html`.

---

# Criterio definitivo de aceptación

La aplicación **NO se considerará terminada** si necesita:

- Internet;
- una API Key;
- localhost;
- un servidor;
- npm;
- Node.js;
- una cuenta externa;
- una API de inteligencia artificial;
- una CDN;
- una base de datos remota;
- o cualquier recurso alojado fuera del proyecto.

### Prueba definitiva

El proyecto deberá poder copiarse completamente a una memoria USB, trasladarse a otro computador y ejecutarse mediante:

```text
Doble clic → index.html → Nueva prueba → Responder → Calificar → Revisar → Imprimir/Guardar PDF
```

con el computador **completamente desconectado de Internet**.

Ese flujo representa el criterio definitivo de **funcionalidad offline real**.

---

# Objetivo final

El resultado debe ser una aplicación profesional capaz de generar localmente pruebas de la Parte 3 del Saber 11 con una calidad equivalente a la de un equipo de diseñadores de ítems, garantizando:

- coherencia lingüística;
- validez psicométrica;
- fidelidad al formato de referencia;
- banco local de conversaciones;
- generación local de pruebas;
- funcionamiento responsive;
- exportación local;
- y **100% de funcionamiento offline**.
