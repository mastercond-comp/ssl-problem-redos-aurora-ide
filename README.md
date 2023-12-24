# ssl-problem-redos-aurora-ide
Решение проблемы подписания пакетов Аврора IDE в RED OS (РедОС) Муром

Ошибка подключения к сборочному движку: Сбой соединения SSH.
/usr/bin/ssh: relocation error: /usr/bin/ssh: symbol EVP_KDF_ctrl version OPENSSL_1_1_1b not defined in file libcrypto.so.1.1 with link time reference

Вот такую штуку выдавал

Решил вроде наконец свою проблему с тем, что слетает подписание пакетов в QtCreator в РедОС Муром (дистрибутив на базе RedHat Linux). 

Если у кого дистрибутивы на базе Red Hat Linux - возможно это пригодится. 

Просто скопировал libcrypto.so.1.1 (у меня называлась libcrypto.so.1.1b, после копирования переименовал) из папки /usr/lib64 в папку библиотек Qt в АврораIDE (/home/имя_пользователя/AuroraOS/lib/Qt/lib) - всё заработало. 

То есть по сути имевшуюся библиотеку в Аврора IDE заменил системной. 

Имевшийся в комплекте IDE файл libcrypto.so.1.1 переименовал на всякий случай в _libcrypto.so.1.1

Помогла решить проблему следующая ссылка: https://github.com/openssl/openssl/issues/11471
