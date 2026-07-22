# Check-in · Terapia Ocupacional

Página tipo encuesta para las herramientas de la sesión de terapia ocupacional
(registro diario, prioridades 3-2-1, energía/ánimo/ansiedad, rutina matinal,
diario de autoexigencia, actividad significativa y técnica STOP).

Es un **sitio estático**: un solo archivo `index.html`, sin backend ni build.
Las respuestas se guardan en el `localStorage` del navegador de quien la usa
(quedan solo en su dispositivo) y se pueden exportar a CSV/Excel desde la
misma página.

## Subir a GitHub

```bash
cd checkin-repo
git init
git add .
git commit -m "Primera versión del check-in"
git branch -M main
git remote add origin https://github.com/<tu-usuario>/<tu-repo>.git
git push -u origin main
```

(O más simple: crea el repo vacío en github.com → "Add file" → "Upload files"
→ arrastra `index.html` y este `README.md`.)

## Desplegar en Vercel

1. Entra a vercel.com e inicia sesión (puedes usar tu cuenta de GitHub).
2. "Add New…" → "Project" → selecciona el repositorio que acabas de crear.
3. Vercel detecta que es un sitio estático — no hace falta configurar
   build command ni output directory. Deja todo por defecto.
4. "Deploy". En menos de un minuto te da un link tipo
   `https://tu-repo.vercel.app` que puedes compartir o guardar como acceso
   directo en el celular.

Cada vez que subas un cambio a `main` en GitHub, Vercel vuelve a publicar
automáticamente.

## Nota sobre los datos

Como el guardado es local al navegador, cada persona que use el link ve solo
sus propios registros — no hay una base de datos central donde se junten los
de varias personas. Si más adelante quieren centralizar los registros (por
ejemplo, que un equipo o un profesional los vea todos juntos), hay que sumar
un backend simple (Vercel KV, Google Sheets vía Apps Script, Airtable, etc.);
avísenme si llegan a necesitar eso y lo armamos.
