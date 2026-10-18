# Primer aliento — experiencia interactiva

## Entrega
Sitio estático sin dependencias, basado en el index original y en los nueve pasos de la tabla del DOCX. Rediseño editorial con fondos marfil, verde profundo, acentos terracota y tipografía serif del sistema. No usa fuentes remotas, servicios de analítica ni bibliotecas externas.

## Incorporar videos
1. Descomprime el paquete completo.
2. Añade nueve videos MP4 en assets/videos, llamados paso-01.mp4 hasta paso-09.mp4.
3. Conserva index.html en la raíz.
4. Abre index.html para una prueba local o publica la carpeta completa en tu alojamiento estático.

No se incluyen videos. Si falta un archivo o falla su reproducción, las respuestas siguen bloqueadas. El selector «Preparación · Cargar un video local» permite probar cada escena; la selección solo dura en esa pestaña y no publica el archivo.

Por defecto ambos contextos comparten el video de cada paso, pero mantienen las preguntas diferenciadas del documento. Para videos diferentes por contexto, busca `const MEDIA` dentro de index.html y cambia las propiedades `rural` y `advanced`. Las rutas pueden apuntar a otros archivos del alojamiento. Para WebM cambia también la extensión de la ruta. No pegues enlaces de páginas de YouTube: este reproductor requiere un archivo de video reproducible directamente.

## Publicación y QR
Sube index.html y assets a tu alojamiento estático. El README original ya incluye el procedimiento de GitHub Pages. Una vez publicada, comprueba la dirección pública desde un celular y crea el QR con esa dirección. El QR debe apuntar al sitio publicado, no al archivo local ni al ZIP. No se incluye QR porque aún no se proporcionó una dirección pública de destino.

## Reglas de interacción
- Selección inicial de nivel 1/rural o niveles 2–4.
- Nueve escenas con opciones aleatorias. Las respuestas indicadas como correctas en el DOCX son la clave del ejercicio.
- El clic antes de completar el video muestra un diálogo y NO cuenta como intento.
- El desbloqueo exige el evento de finalización y haber recorrido el video. No basta con iniciar la reproducción.
- Se permite pausar y retroceder. No hay control de avance rápido; los saltos hacia una zona aún no vista se devuelven al punto recorrido.
- Cambiar de escena o cargar un video nuevo reinicia el bloqueo de reproducción.
- Respuesta incorrecta: explicación y reintento. Respuesta correcta: píldoras y acceso a la siguiente escena.
- Resultado: aciertos al primer intento y cuaderno de repaso de los nueve pasos.
- No hay persistencia al recargar, cuentas, notas guardadas ni integración LMS.
- Este control de reproducción es pedagógico, no un sistema antifraude: puede modificarse desde las herramientas de desarrollo. Tampoco verifica atención humana.

## Revisión clínica obligatoria
Se trasladaron las opciones y las píldoras del documento, sin certificarlas como recomendaciones vigentes. La interfaz muestra que el contenido está pendiente de revisión docente. Revisar antes de presentar como formación validada, especialmente:
- Paso 4: los cortes de edad gestacional difieren entre la opción correcta y la explicación de oxígeno inicial; validar cifras, cadencia y localización del sensor.
- Paso 8: revisar la mención de 30 segundos tras compresiones y el momento de reevaluación/medicación.
- Confirmar dosis, concentraciones, tiempos, umbrales de glucemia, disponibilidad de recursos y criterios de vía aérea con el responsable clínico.
- El párrafo suelto «Ventila, 2, Ventila» del nivel rural se anexó al distractor de altas presiones, siguiendo la nota de interpretación incluida en el DOCX.
Las explicaciones reproducen el guion, no una revisión independiente de evidencia. No emplear este prototipo para atender pacientes ni certificar competencias.

## Comprobaciones realizadas
- Sintaxis JavaScript: verificada con Node.
- Navegador Chromium automatizado, ancho 390 px: sin desbordamiento horizontal; alerta por clic temprano sin penalización; recorrido de nueve respuestas correctas hasta resultados; sin errores JavaScript en ese flujo.
- Video sintético temporal WebM: finalización real desbloquea; error no habilita siguiente; nueva escena vuelve a bloquear.
- Los MP4 finales y Safari/iOS/Android reales todavía deben probarse: los videos definitivos no estaban incluidos. El Chromium de pruebas no tenía decodificador H.264.
