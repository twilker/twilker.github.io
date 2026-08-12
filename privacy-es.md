---
title: DailyFlow – Política de Privacidad
layout: page
permalink: /dailyflow/privacy/es/
---

# DailyFlow – Política de Privacidad

**Idiomas:** [English](/dailyflow/privacy/) · [Deutsch](/dailyflow/privacy/de/) · Español · [Português (BR)](/dailyflow/privacy/pt-br/)

**Aplicación:** DailyFlow / Alltagshelfer (`com.marvelsofcode.dailyflow`)
**Fecha de entrada en vigor:** 12 de agosto de 2026

## 1. Responsable

Tobias Wilker
Correo electrónico: [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com)

Responsable del tratamiento de los datos descritos aquí. Para cualquier consulta sobre esta política o sobre tus datos, escribe a la dirección anterior.

## 2. Resumen

DailyFlow es una aplicación «local first». Tus tareas, tareas periódicas, rutinas, listas de verificación, estadísticas, historial y ajustes se guardan **únicamente en tu dispositivo**. No hay cuenta, ni registro, ni perfil de usuario en ningún servidor mío. No recojo, recibo, vendo ni comparto tus datos personales.

La aplicación **no contiene publicidad, ni rastreo, ni analítica**. El SDK de Firebase Analytics se eliminó deliberadamente.

Dos funciones opcionales envían datos fuera del dispositivo, y solo si las usas: **compartir en grupo / delegar** y **copia de seguridad en Google Drive**. Ambas se describen a continuación.

## 3. Datos almacenados en tu dispositivo

Se guardan localmente: tareas y sus fechas de vencimiento, reglas de repetición, rutinas, listas de verificación y sus elementos, el historial de tareas completadas, estadísticas, perfiles, la pertenencia a grupos junto con las claves criptográficas, y tus ajustes. Estos datos nunca se transmiten salvo mediante las dos funciones opcionales de las secciones 4 y 5.

El historial de tareas completadas se depura automáticamente según el periodo de retención que configures en los ajustes.

Al desinstalar la aplicación se eliminan todos estos datos.

## 4. Compartir en grupo y delegar tareas (opcional)

Si te unes a un grupo escaneando el código QR de otro dispositivo, puedes compartir tareas, rutinas y listas con el resto de miembros y delegarles tareas.

- **Cifrado de extremo a extremo.** Todo lo que sale de tu dispositivo hacia otro miembro se cifra en tu dispositivo con AES-256-GCM (un vector de inicialización aleatorio por mensaje y una etiqueta de autenticación de 128 bits).
- **La clave nunca llega a un servidor.** La clave de grupo de 256 bits se genera en tu dispositivo y se transfiere únicamente dentro del código QR que muestras a la otra persona. Nunca se sube y yo no dispongo de ella.
- **Qué ve el transporte.** Los mensajes cifrados los reenvía una Cloud Function de Google de mi propiedad (proyecto de Firebase `dailyflow-502909`) y se entregan mediante Firebase Cloud Messaging. El relé solo ve el token de mensajería del destinatario, el texto cifrado opaco, una clave de colapso y un identificador del dispositivo emisor. No puede leer el contenido, y el contenido no se guarda en ninguna base de datos mía.
- **Conservación.** Los mensajes que no pueden entregarse de inmediato los retiene Firebase Cloud Messaging como máximo durante su tiempo de vida máximo de cuatro semanas y después los descarta. La cola de envío local correspondiente en tu dispositivo se vacía con la misma periodicidad.
- **Protección frente a abusos.** Se usa Firebase App Check (Play Integrity) para evitar que otros clientes abusen del endpoint del relé.
- **Encargado del tratamiento.** Google Ireland Limited / Google LLC para Firebase Cloud Messaging y Cloud Functions. Información de privacidad de Google: <https://firebase.google.com/support/privacy>.
- **Base jurídica.** Art. 6(1)(b) del RGPD: tratamiento necesario para prestar la función de compartir que has solicitado. Si no te unes a ningún grupo, no se transmite ningún dato.

Ten en cuenta que los demás miembros del grupo pueden ver, por definición, el contenido que compartes con ellos. Comparte solo con personas en las que confíes.

## 5. Copia de seguridad en Google Drive (opcional)

Si inicias una copia de seguridad, la aplicación solicita autorización para un único ámbito de Google Drive: `https://www.googleapis.com/auth/drive.appdata`. Ese ámbito concede acceso **exclusivamente a la carpeta oculta de datos de la propia aplicación** en tu Drive. La aplicación nunca puede ver, leer ni modificar tus demás archivos de Google Drive, y no solicita tu nombre, dirección de correo ni perfil.

El archivo de copia de seguridad contiene tu base de datos local, tus ajustes y una instantánea de tu configuración de grupo. Se almacena **en tu propia cuenta de Google Drive**, bajo tu control, y está protegido por el cifrado en reposo de Google. La aplicación no lo cifra adicionalmente. Yo no tengo acceso a tu Drive ni al archivo de copia. Puedes borrarlo en cualquier momento desde el almacenamiento de datos de aplicaciones de tu cuenta de Google y revocar la autorización en <https://myaccount.google.com/permissions>.

**Base jurídica.** Art. 6(1)(a)/(b) del RGPD: eres tú quien inicia expresamente la copia.

## 6. Permisos y para qué se necesitan

| Permiso | Finalidad |
| --- | --- |
| Notificaciones | Alarmas de tareas vencidas y el resumen diario opcional |
| Alarmas exactas | Sonar exactamente a la hora fijada; una alarma de recordatorio inexacta no serviría |
| Intent a pantalla completa | Mostrar y descartar la alarma desde la pantalla de bloqueo |
| Servicio en primer plano (reproducción) | Mantener el sonido de la alarma mientras esta suena |
| Ejecutar al inicio | Reprogramar las alarmas pendientes tras reiniciar el dispositivo |
| Internet / estado de la red | Solo para el relé cifrado (sección 4) y la copia en Drive (sección 5) |
| Cámara | Escanear el código QR de invitación a un grupo. No se guarda ni se transmite ninguna foto o vídeo |

## 7. Menores

DailyFlow es una aplicación de productividad para público general. No está dirigida a menores ni recoge conscientemente datos de ellos.

## 8. Tus derechos

Conforme al RGPD tienes derecho de acceso, rectificación, supresión, limitación del tratamiento, portabilidad y oposición, así como a presentar una reclamación ante una autoridad de control.

Como no conservo datos personales sobre ti, en la práctica no hay nada que yo pueda facilitar o suprimir. Ejerces estos derechos directamente: desinstala la aplicación para borrar todos los datos locales, elimina tu copia de Drive y revoca la autorización en tu cuenta de Google, y abandona los grupos a los que te hayas unido. Si tienes dudas, escríbeme a [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com).

## 9. Cambios en esta política

Los cambios se publican en esta página con una nueva fecha de entrada en vigor. Los cambios sustanciales se indicarán además en las notas de la versión de la aplicación.
