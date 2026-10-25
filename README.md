# Listening Exam — 8th Grade

Colegio Nocturno de Cariari · Second Semester 2026 · Teacher: Saiden Ortiz Gómez · 9 points (10%) · One lesson

Same design and behaviour as the 10th and 11th grade exams: each audio can be played **up to 3 times**, the exam
is graded automatically, and every result goes to a Google Sheet.

| Part | Audio | What students do | Points |
| --- | --- | --- | --- |
| Multiple Choice | `audio1.mp3` | 3 questions about the holiday the speaker celebrated, options A–C | 3 |
| Identification | `audio2.mp3` | On the map, choose who celebrated New Year in Honduras, Nicaragua and Costa Rica: Mark, Anne or Jenna | 3 |
| Short Answer | `audio3.mp3` | Complete 3 sentences with Holi Festival, Rio de Janeiro Carnival or Day of the Dead | 3 |

In Identification and Short Answer each name or option can be used only once, as on the printed exam.

## The answer key is not here

The repository is public, so the answers are **only in the teacher's Google Apps Script**. The page sends the
student's answers; the script grades them and writes one row per student:

`Fecha y hora · Nombre del estudiante · Grupo · Puntaje · Porcentaje · Nota (10%) · Multiple Choice · Identification ·
Short Answer · Correctas · Incorrectas · Detalle por pregunta · ID`

## Setup

1. **Google Sheet**: create a new sheet → `Extensions ▸ Apps Script` → paste the script → run `configurar` once →
   `Deploy ▸ New deployment ▸ Web app` (*Execute as: Me*, *Who has access: Anyone*) → copy the `/exec` URL.
2. **The page**: put that URL in `script.js`:

   ```js
   const APPS_SCRIPT_URL = "https://script.google.com/macros/s/..../exec";
   ```

3. **GitHub Pages**: `Settings ▸ Pages ▸ Deploy from a branch ▸ main ▸ /(root)`. The exam is then at
   <https://royespnz-jpg.github.io/8-listening-test/>.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The exam page |
| `script.js` | Questions, audio control (3 plays), drop-downs, sending to the sheet |
| `style.css` | "Night School Aurora" theme (same as 7th, 10th and 11th grade) |
| `audio1.mp3 … audio3.mp3` | The three audios |
| `img/identification.jpg` | The map of Honduras, Nicaragua and Costa Rica, with the three empty boxes |
