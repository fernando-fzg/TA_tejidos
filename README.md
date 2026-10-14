# Banco de preguntas · Tópicos Avanzados en Ingeniería de Tejidos

Cuestionario web con **200 preguntas de opción múltiple**, organizado en **20 bloques de 10**. Al terminar cada bloque muestra el puntaje y la retroalimentación de cada pregunta: indica la respuesta correcta y explica por qué. Al completar los 20 bloques, un resumen final presenta el porcentaje de aciertos por tema, ordenado del tema más débil al más fuerte.

## Temas (según los materiales del curso)

| Bloques | Tema | Fuente |
|---|---|---|
| 1–3 | Ingeniería de piel y sustitutos dérmicos | Clase 1 · Fu et al. 2023 · Mu et al. 2021 |
| 4–5 | Bases de ingeniería de tejido óseo y cartilaginoso | Clase 2 |
| 6–7 | Andamios porosos de Zn–1Mg con recubrimiento bioactivo | Zhang et al. 2023 |
| 8–9 | Diseño y optimización de andamios tridimensionales | Clase de la Dra. Palma |
| 10–12 | Ingeniería de tejido musculoesquelético | Tópicos Avanzados en Ing. de Tejidos Musculoesqueléticos |
| 13–14 | Modelado matemático de la producción de GAG | Fu et al. 2017 |
| 15–17 | Biorreactor 3D de bajo cizallamiento para hMSC | Burns et al. 2021 |
| 18–20 | Caracterización de biosensores y fracciones del proteoma | Vaccari, Guerra et al. 2025 |

## Funciones

- El botón **«Ver resultados del bloque»** se habilita cuando respondes las 10 preguntas del bloque.
- Puedes reintentar un bloque; al hacerlo, las alternativas cambian de orden.
- El menú **«Bloques»** permite saltar a cualquier bloque.
- En **«Ajustes»** puedes mezclar las preguntas de todos los temas, barajar las alternativas o activar el modo oscuro.
- El avance se guarda en el navegador (`localStorage`). No usa servidor ni cuentas.

## Archivos

```
index.html     → la página y toda la lógica del cuestionario
preguntas.js   → el banco de preguntas (editable)
README.md
```

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo, `banco-tejidos`).
2. Sube `index.html`, `preguntas.js` y `README.md` a la raíz del repositorio. Puedes arrastrarlos en la web con **Add file → Upload files**, o usar la terminal:
   ```bash
   git init
   git add .
   git commit -m "Banco de preguntas de Ingeniería de Tejidos"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/banco-tejidos.git
   git push -u origin main
   ```
3. En el repositorio, entra a **Settings → Pages**.
4. En **Build and deployment**, elige **Source: Deploy from a branch**, la rama **main** y la carpeta **/ (root)**. Luego pulsa **Save**.
5. En uno o dos minutos la página estará en `https://TU-USUARIO.github.io/banco-tejidos/`.

## Agregar o editar preguntas

Cada pregunta de `preguntas.js` tiene este formato:

```js
{ t: "A",                       // código de tema (ver TEMAS al inicio del archivo)
  q: "Enunciado de la pregunta",
  o: ["Correcta", "Distractor 1", "Distractor 2", "Distractor 3"],
  a: 0,                         // índice de la alternativa correcta
  e: "Retroalimentación que se muestra al corregir" },
```

Las alternativas se barajan al mostrarse, así que puedes escribir siempre la correcta en la primera posición. Si el total de preguntas no es múltiplo de 10, el último bloque tendrá menos preguntas.
