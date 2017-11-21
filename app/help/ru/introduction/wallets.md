# Кошелек

Как Вы уже могли заметить, это веб-приложение, которое работает в браузере. Соединение устанавливается с доверенным узлом сети, который служит шлюзом в остальную часть экосистемы.

## Модель аккаунта

Если Вы зарегистрировались с использованием имени пользователя и пароля, Вы обладаете облачным кошельком. И хотя технически ничего не хранится в облаке, мы используем термин Облачный кошелек, потому что Вы можете использовать эти данные (имя пользователя и пароль) для получения доступа к своему аккаунту из любого веб-браузера в любой момент. Облачный кошелек позволяет получить доступ только к одному аккаунту за раз. Обычно это является оптимальным вариантом для новых пользователей. While it is possible to change the auto-generated password, we do not recommend doing so at this time. The team is working on a responsible way to manage the password change that requires no technical knowledge. We will make an announcement once it's released.

## Модель кошелька

The local wallet creates a database within your browser. This means that access to your funds it tied to **that browser only**. If you attempt to access your local wallet from any other computer, or any other browser, it will fail unless you actively import your backup file from the original browser backup file. The process actually easy. See managing [backups](/help/introduction/backups).

## Безопасность

Будьте уверены, что наши сервера никогда не получат доступа к Вашим средствам, потому как ни один из Ваших приватных ключей никогда не покидает браузер. Вместо этого они зашифрованы с помощью Вашей фразы-пароля и хранятся в локальной базе данных Вашего браузера. As such, you should make sure to have a proper [Backup](../introduction/backups.md) in the event something happens to your computer or browser.

## Управление

Пользовательский интерфейс способен содержать и предоставлять доступ к нескольким кошелькам, каждый из которых может содержать несколько аккаунтов и соответствующие им средства. Вы можете добавлять, создавать резервную копию и переключаться между существующими кошельками в меню `Настройки->Кошельки`.