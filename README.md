# Gen-Eco en Ruta: Guardianes Alfa
Videojuego web educativo (HTML5, CSS3, JavaScript puro) para estudiantes de 16 a 18 años del Gimnasio Nuevo Modelia (Bogotá). Fortalece la motivación hacia la educación ambiental mediante 4 misiones: residuos (ODS 12), energías limpias (ODS 13), biodiversidad (ODS 15 y patrimonio natural) y consumo responsable (ODS 12).

## Estructura
```
gen-eco-en-ruta/
├── index.html   (juego)
├── style.css
├── script.js
├── admin.html   (panel docente: consulta, CSV, JSON, restaurar, borrar)
└── README.md
```

## Publicar en GitHub Pages
1. Crea cuenta en github.com → **New repository** → nombre `gen-eco-en-ruta`, público, sin README.
2. **uploading an existing file** → arrastra los 5 archivos (en la raíz) → **Commit changes**.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch `main`, carpeta `/ (root)` → Save.
4. Espera 1 a 3 minutos. URL: `https://TU-USUARIO.github.io/gen-eco-en-ruta/`. Panel: `.../admin.html`.

## Panel docente
Clave inicial: `GenEco2045` (cámbiala en la constante `PW` de `admin.html`). **Está en el código fuente: es una protección básica, no seguridad profesional.** El juego no recoge datos personales (solo código anónimo tipo GA001).

## Datos y limitaciones
Todo se guarda en `localStorage` del navegador y dispositivo usados. No hay base de datos central ni envío a servidores. No se sincroniza entre computadores; se pierde al borrar datos del navegador, usar modo incógnito o cambiar de navegador. Después de **cada sesión**, abre `admin.html` en ese mismo computador y exporta CSV y JSON; consolida los archivos de todos los equipos. Para recuperar: `admin.html` → *Restaurar JSON* (combina por id sin duplicar).

El CSV está en formato largo: una fila por respuesta (`tipo` = reto o comprension). Resultados posibles: `correcta`, `incorrecta`, `sin_responder`, `mejor_opcion`, `intermedia`, `menos_sostenible`. Estado de misión: `no_realizada`, `iniciada`, `abandonada`, `completada`. **El puntaje mide desempeño en el juego, no motivación**; la motivación debe medirse con un instrumento validado aparte.

## Puntuación
Reto: +10 acierto / +2 participación (errores); preguntas de comprensión: +10 acierto; bonus +20 por completar misión. No hay puntos negativos ni rankings.

## Pruebas manuales antes de aplicar (no se han ejecutado en navegador)
1. Carga sin errores en consola (F12) en Chrome, Edge y celular.
2. Código inválido (vacío, "A B", "ñ") es rechazado; "ga001" se guarda como GA001.
3. Las misiones 2, 3 y 4 aparecen bloqueadas hasta completar la anterior.
4. M1: seleccionar+recipiente, arrastrar (PC) y tocar (celular); el cronómetro baja de 45 y al llegar a 0 los pendientes quedan `sin_responder`.
5. Pausa detiene el tiempo; "Volver al mapa" marca la misión `abandonada` y permite retomarla.
6. M3: 6 parejas, contador de intentos y tiempo; M4: 8 situaciones.
7. Recargar a mitad de sesión: aparece "Continuar sesión" sin duplicar registros en admin.
8. Pantalla final «Guardián Ambiental Alfa» tras 4 misiones; resumen parcial si se termina antes.
9. Admin: conteo correcto, alertas de incompletos, CSV abre en Excel, JSON se restaura, borrar exige escribir ELIMINAR.
10. Navegación solo con Tab/Enter/Espacio; zoom 200 %; pantalla de 360 px.

## Guía breve para el docente (sesión de 55 min)
1. (5 min) Presenta el propósito: explorar, no evaluar. Entrega códigos GA001, GA002…
2. (5 min) Abren la URL, eligen avatar, escriben su código.
3. (35 min) Juegan las 4 misiones a su ritmo. Observa y no corrijas respuestas.
4. (5 min) Cierran en «Terminar sesión y ver resumen».
5. (5 min) Conversación: ¿qué te sorprendió?, ¿qué decisiones cambiarías? Después exporta CSV y JSON desde `admin.html` en cada equipo.
