📄 Archivos del proyecto
Archivo
Para qué sirve
Acceso
index.html
Página promocional del sorteo (la que ve el público)
Pública
control-boletos.html
Registrar quién compra cada boleto
Privado — solo Angélica, Pedro y Pablo
tablero.html
Registrar qué boletos ya están pagados
Privado — solo Angélica, Pedro y Pablo
🔗 Enlaces
Página pública (la que se comparte con todo el mundo):
Código
Control de boletos (NO compartir, solo para el equipo):
Código
Tablero de pagos (NO compartir, solo para el equipo):
Código
Estos dos últimos enlaces no aparecen en ningún botón de la página
pública a propósito. Se comparten directamente por WhatsApp entre
el equipo y cada quien los guarda como acceso directo en su celular.
☁️ Cómo funciona el guardado de datos
control-boletos.html y tablero.html no guardan la información
solo en el celular de quien los usa — están conectados a una hoja
de Google Sheets compartida, para que Angélica, Pedro y Pablo vean
siempre los mismos datos sin importar desde qué celular entren ni en
qué momento del día.
Hoja de Google Sheets: Base de datos Sorteos Lopez
Motor de conexión: un script de Google Apps Script (Code.gs)
publicado como "aplicación web", que actúa de intermediario entre
la página y la hoja de cálculo.
Cada vez que alguien registra o edita algo, se envía automáticamente
a esa hoja. Cada vez que alguien abre la página, trae lo último
guardado ahí.
Si el celular se queda sin internet, aparece un aviso en rojo — sin
conexión no se puede leer ni guardar información nueva.
Hay un botón 🔄 Actualizar arriba a la derecha de cada página
por si alguien deja la pestaña abierta mucho tiempo y quiere traer
los cambios más recientes de los demás.
🛠️ Si algún día hay que reinstalar la conexión a la nube
Por ejemplo, si se crea una hoja de cálculo nueva o el script deja
de funcionar:
Sigue las instrucciones del archivo INSTRUCCIONES.md.
Copia el código de Code.gs en un proyecto de Apps Script nuevo.
Publícalo como aplicación web (acceso: Cualquier usuario).
Copia la URL que te da y pégala en la línea const API_URL = '...'
al inicio del <script> en ambos archivos
(control-boletos.html y tablero.html — debe ser la misma URL
en los dos).
Sube los archivos actualizados a este repositorio.
⚠️ Privacidad
La hoja de Google Sheets y el script no son "públicos" en el sentido
de aparecer en buscadores, pero cualquiera que conozca la URL de la
aplicación web podría leer o escribir datos, así funcionan los
scripts gratuitos de Google. Por eso esa URL nunca debe compartirse
fuera del equipo. Si alguna vez se sospecha que se filtró, se puede
crear una nueva implementación en Apps Script para generar una URL
distinta.
