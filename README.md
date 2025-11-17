TryHackMe — Offensive Security Intro
Mi primer laboratorio de ciberseguridad ofensiva

Este repositorio documenta mi práctica en el laboratorio Offensive Security Intro de TryHackMe, donde aprendí los fundamentos del hacking ético y realicé mi primera explotación contra una web vulnerable en un entorno controlado.

🔍 1. Objetivo del laboratorio

Conocer el flujo básico del hacking ofensivo

Interactuar con una máquina real creada por TryHackMe

Analizar elementos de una web vulnerable

Encontrar el fallo y explotarlo

Obtener el mensaje final de éxito (BANK‑HACKED)

Este fue mi primer contacto práctico con la ciberseguridad ofensiva.

🧠 2. ¿Qué aprendí?

✔ Cómo acceder a una máquina virtual remota
✔ Cómo inspeccionar archivos HTML y JS vulnerables
✔ Cómo identificar la lógica insegura en una aplicación
✔ Cómo manipular datos del cliente (cookies + JavaScript)
✔ Cómo validar que había explotado correctamente la vulnerabilidad
✔ Cómo documentar un análisis técnico de manera profesional

🖥️ 3. Entorno utilizado

Plataforma: TryHackMe

Room: Offensive Security Intro

Máquina asignada (IP dinámica): 10.10.X.X

Entorno de análisis: Terminal de la TryBox + navegador

Archivos inspeccionados:

/index.html

/js/script.js

🗂️ 4. Análisis del código vulnerable

Durante el análisis identifiqué varios puntos débiles:

🔸 4.1 Manipulación de cookies

El archivo script.js gestionaba el saldo del banco usando cookies del navegador:

setCookie('bank_value', (amount + parseFloat(amountEl.value || 0)).toFixed(2), 365)


👉 Esto significa que el usuario podía modificar su propio saldo manipulando cookies.

🔸 4.2 Lógica insegura del lado del cliente

Toda la verificación de transacciones se hacía con JavaScript en el lado del cliente, sin comprobación del servidor.

Esto permitió alterar el comportamiento de la “banca”.

🚀 5. Explotación técnica

Los pasos básicos fueron:

Abrir la web del “banco” vulnerable

Inspeccionar los archivos HTML y JS

Confirmar que el saldo dependía de cookies

Manipular las cookies con herramientas del navegador

Forzar el estado de cuenta a positivo

Activar la función showWinningMsg()

Obtener el mensaje final: BANK-HACKED

🏁 6. Resultado final

El laboratorio fue completado con éxito.

Mensaje obtenido:

BANK-HACKED

Captura en screenshots/room-completed.png.
