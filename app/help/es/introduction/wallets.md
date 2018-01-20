# Billetera

Como puede que haya notado, esta aplicación es una aplicación web que opera a través de un navegador. Una conección es establecida a un nodo confiable en la red que sirve como puerta al resto del ecosistema.

## Billetera en la Nube

Si usted registró un nombre de usuario y contraseña, usted tiene una billetera en la nube. Aunque nada esté técnicamente almacenado en la nube, nosotros usamos el término Billetera en la Nube ya que usted puede usar estas credenciales (nombre de usuario y contraseña) desde cualquier navegador web en cualquier momento para acceder a su cuenta. La billetera en la nube solo permite acceder a una cuenta a la vez. Esta es generalmente la decisión correcta para nuevos usuarios. Aunque es posible cambiar la contraseña generada automáticamente, nosotros no recomendamos realizarlo en este momento. El equipo está trabajando en una forma responsable de administrar el cambio de contraseña que no requiera de conocimiento técnico. Realizaremos un anuncio en su lanzamiento.

## Billetera Local

La billetera local crea una base de datos en su navegador. Esto quiere decir que el acceso a sus fondos está atado **únicamente a ese navegador**. If you attempt to access your local wallet from any other computer, or any other browser, it will fail unless you actively import your backup file from the original browser backup file. The process actually easy. See managing [backups](/help/introduction/backups).

## Security

Rest assured that our servers do not have access to your funds because none of your private keys ever leave your browser. Instead, they are encrypted with your passphrase and are stored in your local browser's database. As such, you should make sure to have a proper [Backup](../introduction/backups.md) in the event something happens to your computer or browser.

## Management

The user interface is capable of carrying and accessing several separated wallets each containing possible several accounts and corresponding funds. You can create, backup, and switch existing wallets in `Settings->Wallets`.