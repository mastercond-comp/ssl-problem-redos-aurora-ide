# Решение проблемы подписания пакетов Аврора IDE в RED OS (РедОС) Муром
<br><br><strong>Ситуация в Аврора IDE:</strong><br><br>
<code>Ошибка подключения к сборочному движку: Сбой соединения SSH.
/usr/bin/ssh: relocation error: /usr/bin/ssh: symbol EVP_KDF_ctrl version OPENSSL_1_1_1b not defined in file libcrypto.so.1.1 with link time reference
</code><br><br>
Вот такую штуку Аврора IDE выдавала.<br><br>

Решил вроде наконец свою проблему с тем, что слетает подписание пакетов в QtCreator в РедОС Муром (дистрибутив на базе RedHat Linux). <br><br>

Если у кого дистрибутивы на базе Red Hat Linux - возможно это пригодится. <br><br>

Просто скопировал libcrypto.so.1.1 (у меня называлась libcrypto.so.1.1b, после копирования переименовал) из папки /usr/lib64 в папку библиотек Qt в АврораIDE (/home/имя_пользователя/AuroraOS/lib/Qt/lib) - всё заработало. <br><br>

То есть по сути имевшуюся библиотеку в Аврора IDE заменил системной. <br><br>

Имевшийся в комплекте IDE файл libcrypto.so.1.1 переименовал на всякий случай в _libcrypto.so.1.1<br><br>

Помогла решить проблему следующая ссылка: https://github.com/openssl/openssl/issues/11471<br><br>
