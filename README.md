# Hackathon FrontendBlocker

Diese Erweiterung sperrt das Frontend von [Magento](http://www.magento.com/), lässt aber das Backend in Betrieb.

## Das Problem

Hin und wieder hat ein Ladenbetreiber im Backend Wartungsarbeiten durchzuführen, wobei er von Kundenaktivitäten nicht gestört werden darf. Von Haus aus ermöglicht Magento leider nicht, das Frontend zu sperren, ohne dabei nicht auch das Backend zu schließen.

## Die Lösung

Die Datei 'maintenance.flag' bewirkt, dass sowohl das Frontend und das Backend von Magento gesperrt sind. Das ist beispielsweise der Fall, wenn mit dem "Magento Connect Manager" die Software aktualisiert wird. Im Gegensatz dazu wird über die Datei 'frontend_off.flag' nur das Frontend gesperrt.

Um das zu bewerkstelligen, muss ein Patch auf die Datei 'index.php' eingespielt werden. Wenn die Datei 'frontend_off.flag' beispielsweise in 'frontend_on.flag' umbenannt wird, bewirkt die Datei nichts. Dies kann beispielsweise mittels SSH geschehen:
* mv frontend_off.flag frontend_on.flag

oder mittels FTP oder über den Dateimanager der Webspace-Verwaltung. Allerdings gibt man mit dem dafür notwendigen Passwort auch die Kontrolle über die gesamte Installation aus der Hand.

Man kann jedoch auch mit der Extension "Hackathon FrontendBlocker" über den "Magento Connect Manager" die Datei 'frontend_off.flag' in das Hauptverzeichnis schreiben. Deinstalliert man die Extension "Hackathon FrontendBlocker" wieder, wird die Datei 'frontend_off.flag' wieder entfernt.

Der nötige Patch kann mit
* patch -p1 index.php < frontend_blocker.patch

eingespielt werden. Oder aber, man editiert die "index.php" selbst.

Das ist alles, Freunde!<br />
MaWoScha

# English
This extension locks the frontend of [Magento](http://www.magento.com/), but leaves the backend in operation.

## The problem
Every now and then has a shop operator to perform maintenance in the backend, which he must not be disturbed by customer activity. Innately Magento does not allow, unfortunately, to terminate your frontend without taking care not to include also the backend.

## The solution
The file 'maintenance.flag' causes both the frontend and the backend of Magento are locked. This is for example the case if the "Magento Connect Manager" software is updated. In contrast, only the frontend is via the file 'frontend_off.flag' locked.

To accomplish this, a patch must be copied to the 'index.php' file. If the file 'frontend_off.flag' example in 'frontend_on.flag' renamed, the file does nothing. This can happen, for example, via SSH:
* mv frontend_off.flag frontend_on.flag

or via FTP or via the file manager of the web space management. However, you are using the password necessary also in control of the entire installation out of hand.

However, it is also with the extension "Hackathon FrontendBlocker" over the "Magento Connect Manager" the file 'frontend_off.flag' write to the root directory. I uninstall the extension "Hackathon frontend Blocker" again, the file 'frontend_off.flag' re away.

The necessary patch can with
* patch -p1 index.php < frontend_blocker.patch

be imported. Or else, you have to edit the "index.php" itself.

That's all, folks!<br />
MaWoScha


# Español
Esta extensión bloquea el extremo delantero de [Magento](http://www.magento.com/), pero deja la parte de atrás en funcionamiento.

## El problema
Cada tiene de vez en cuando un operador de la tienda para realizar el mantenimiento en el backend, la cual no debe ser perturbada por la actividad del cliente. Innatamente Magento no permite, por desgracia, a finalizar su interfaz sin tener cuidado de no incluir también el backend.

## La solución
El archivo 'maintenance.flag' hace que tanto el frontend y el backend de Magento están bloqueados. Este es por ejemplo el caso si el software "Magento Connect Manager" se actualiza. En contraste, sólo el frontend es a través del archivo 'frontend_off.flag' bloqueado.

Para lograr esto, un parche se debe copiar en el archivo 'index.php'. Si se rebautiza el archivo 'frontend_off.flag' en 'frontend_on.flag', el archivo no hace nada. Esto se puede realizar, por ejemplo, a través de SSH:
* mv frontend_off.flag frontend_on.flag

o vía FTP o a través del administrador de archivos en la gestión del espacio web. Sin embargo, no es recomendable perder el control de toda la instalación dando la contraseña necesaria en otras manos.

Sin embargo, también es con la extensión "Hackathon FrontendBlocker" sobre el "Magento Connect Manager" el archivo 'frontend_off.flag' escritura en el directorio raíz. Desinstalando la extensión "Hackathon FrontendBlocker" se remueve también el archivo 'frontend_off.flag'.

El parche necesario se puede realizar con
* patch -p1 index.php < frontend_blocker.patch

O si bien, se modifica "index.php" a mano con un editor.

Eso es todo, amigos!<br />
MaWoScha
