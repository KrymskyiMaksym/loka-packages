# Пакеты Loka

Это реестр пакетов Loka — приложения для локальной веб-разработки на macOS.
Отсюда Loka скачивает веб-серверы, PHP, базы данных и остальные сервисы,
которые человек ставит на экране «Сервисы». Ставить что-либо отсюда вручную
не нужно.

Архивы лежат в релизе `packages` этого репозитория вместе с индексом
`index.json` и его подписью `index.json.sig`. Loka принимает индекс,
только если подпись сходится с ключом, вшитым в приложение, а каждый архив —
только если его sha256 совпадает с записью индекса. Архивы собраны для macOS
на Apple Silicon (arm64).

Адрес реестра в настройках Loka (он же умолчание):

    https://github.com/KrymskyiMaksym/loka-packages/releases/download/packages/

Индекс: serial 9 от 2026-10-26.

## Состав

В архиве `common` — общие библиотеки, с которыми собраны остальные
пакеты; расширения PHP (apcu, xdebug, redis) лежат в архиве своей ветки PHP.

Ни одна ветка PHP не связана с библиотеками под GPL: интерактивная оболочка
`php -a` (расширение readline) собрана с системной libedit macOS (BSD,
`--with-libedit`), а не с GNU Readline, а dba — без обработчика GNU dbm
(только встроенные cdb, inifile и flatfile). GNU Readline (GPL-3.0-or-later)
в архиве `common` нужна только psql из PostgreSQL и консоли `sqlite3`.
GNU dbm (GPL-3.0-or-later) остаётся в `common` отдельной библиотекой: PHP с
ней не связан.

| Пакет | Ветка | Версия | Компонент | Лицензия | Исходники |
|---|---|---|---|---|---|
| apache | 2.4 | 2.4.69 | apache 2.4.69 | [Apache-2.0](licenses/apache-2.4/) | [httpd-2.4.69.tar.gz](https://dlcdn.apache.org/httpd/httpd-2.4.69.tar.gz) |
| cloudflared | stable | 2026.10.1 | cloudflared 2026.10.1 | [Apache-2.0](licenses/cloudflared-stable/) | [2026.10.1.tar.gz](https://github.com/cloudflare/cloudflared/archive/refs/tags/2026.10.1.tar.gz) |
| common | 2026.1 | 2026.1 | zlib 1.3.1 | [Zlib](licenses/zlib-1.3/) | [zlib-1.3.1.tar.gz](https://zlib.net/fossils/zlib-1.3.1.tar.gz) |
| common | 2026.1 | 2026.1 | openssl 3.5.9 | [Apache-2.0](licenses/openssl-3.5/) | [openssl-3.5.9.tar.gz](https://github.com/openssl/openssl/releases/download/openssl-3.5.9/openssl-3.5.9.tar.gz) |
| common | 2026.1 | 2026.1 | pcre2 10.49 | [BSD-3-Clause WITH PCRE2-exception](licenses/pcre2-10.49/) | [pcre2-10.49.tar.gz](https://github.com/PCRE2Project/pcre2/releases/download/pcre2-10.49/pcre2-10.49.tar.gz) |
| common | 2026.1 | 2026.1 | expat 2.6.4 | [MIT](licenses/expat-2.6/) | [expat-2.6.4.tar.gz](https://github.com/libexpat/libexpat/releases/download/R_2_6_4/expat-2.6.4.tar.gz) |
| common | 2026.1 | 2026.1 | apr 1.7.6 | [Apache-2.0](licenses/apr-1.7/) | [apr-1.7.6.tar.gz](https://dlcdn.apache.org/apr/apr-1.7.6.tar.gz) |
| common | 2026.1 | 2026.1 | apr-util 1.6.5 | [Apache-2.0](licenses/apr-util-1.6/) | [apr-util-1.6.5.tar.gz](https://dlcdn.apache.org/apr/apr-util-1.6.5.tar.gz) |
| common | 2026.1 | 2026.1 | lz4 1.10.0 | [BSD-2-Clause AND GPL-2.0-or-later](licenses/lz4-1.10/) | [lz4-1.10.0.tar.gz](https://github.com/lz4/lz4/releases/download/v1.10.0/lz4-1.10.0.tar.gz) |
| common | 2026.1 | 2026.1 | zstd 1.5.7 | [BSD-3-Clause OR GPL-2.0-only](licenses/zstd-1.5/) | [zstd-1.5.7.tar.gz](https://github.com/facebook/zstd/releases/download/v1.5.7/zstd-1.5.7.tar.gz) |
| common | 2026.1 | 2026.1 | ncurses 6.5 | [X11-distribute-modifications-variant](licenses/ncurses-6.5/) | [ncurses-6.5.tar.gz](https://ftp.gnu.org/gnu/ncurses/ncurses-6.5.tar.gz) |
| common | 2026.1 | 2026.1 | readline 8.2 | [GPL-3.0-or-later](licenses/readline-8.2/) | [readline-8.2.tar.gz](https://ftp.gnu.org/gnu/readline/readline-8.2.tar.gz) |
| common | 2026.1 | 2026.1 | icu 76.1 | [Unicode-3.0](licenses/icu-76/) | [icu4c-76_1-src.tgz](https://github.com/unicode-org/icu/releases/download/release-76-1/icu4c-76_1-src.tgz) |
| common | 2026.1 | 2026.1 | libpq 17.6 | [PostgreSQL](licenses/libpq-17/) | [postgresql-17.6.tar.bz2](https://ftp.postgresql.org/pub/source/v17.6/postgresql-17.6.tar.bz2) |
| common | 2026.1 | 2026.1 | bzip2 1.0.8 | [bzip2-1.0.6](licenses/bzip2-1.0/) | [bzip2-1.0.8.tar.gz](https://sourceware.org/pub/bzip2/bzip2-1.0.8.tar.gz) |
| common | 2026.1 | 2026.1 | gdbm 1.26 | [GPL-3.0-or-later](licenses/gdbm-1.26/) | [gdbm-1.26.tar.gz](https://ftp.gnu.org/gnu/gdbm/gdbm-1.26.tar.gz) |
| common | 2026.1 | 2026.1 | gettext 1.0 | [LGPL-2.1-or-later](licenses/gettext-1.0/) | [gettext-1.0.tar.gz](https://ftp.gnu.org/gnu/gettext/gettext-1.0.tar.gz) |
| common | 2026.1 | 2026.1 | gmp 6.3.0 | [LGPL-3.0-or-later OR GPL-2.0-or-later](licenses/gmp-6.3/) | [gmp-6.3.0.tar.xz](https://ftp.gnu.org/gnu/gmp/gmp-6.3.0.tar.xz) |
| common | 2026.1 | 2026.1 | libiconv 1.19 | [LGPL-2.1-or-later](licenses/libiconv-1.19/) | [libiconv-1.19.tar.gz](https://ftp.gnu.org/gnu/libiconv/libiconv-1.19.tar.gz) |
| common | 2026.1 | 2026.1 | libsodium 1.0.22 | [ISC](licenses/libsodium-1.0/) | [libsodium-1.0.22.tar.gz](https://download.libsodium.org/libsodium/releases/libsodium-1.0.22.tar.gz) |
| common | 2026.1 | 2026.1 | nghttp2 1.70.0 | [MIT](licenses/nghttp2-1.70/) | [nghttp2-1.70.0.tar.gz](https://github.com/nghttp2/nghttp2/releases/download/v1.70.0/nghttp2-1.70.0.tar.gz) |
| common | 2026.1 | 2026.1 | oniguruma 6.9.10 | [BSD-2-Clause](licenses/oniguruma-6.9/) | [onig-6.9.10.tar.gz](https://github.com/kkos/oniguruma/releases/download/v6.9.10/onig-6.9.10.tar.gz) |
| common | 2026.1 | 2026.1 | openldap 2.6.15 | [OLDAP-2.8](licenses/openldap-2.6/) | [openldap-2.6.15.tgz](https://www.openldap.org/software/download/OpenLDAP/openldap-release/openldap-2.6.15.tgz) |
| common | 2026.1 | 2026.1 | libpng 1.6.59 | [libpng-2.0](licenses/libpng-1.6/) | [libpng-1.6.59.tar.gz](https://download.sourceforge.net/libpng/libpng-1.6.59.tar.gz) |
| common | 2026.1 | 2026.1 | libjpeg-turbo 3.2.0 | [IJG AND BSD-3-Clause AND Zlib](licenses/libjpeg-turbo-3.2/) | [libjpeg-turbo-3.2.0.tar.gz](https://github.com/libjpeg-turbo/libjpeg-turbo/releases/download/3.2.0/libjpeg-turbo-3.2.0.tar.gz) |
| common | 2026.1 | 2026.1 | libwebp 1.6.0 | [BSD-3-Clause](licenses/libwebp-1.6/) | [libwebp-1.6.0.tar.gz](https://storage.googleapis.com/downloads.webmproject.org/releases/webp/libwebp-1.6.0.tar.gz) |
| common | 2026.1 | 2026.1 | freetype 2.15.0 | [FTL OR GPL-2.0-or-later](licenses/freetype-2.15/) | [freetype-2.15.0.tar.gz](https://download.savannah.gnu.org/releases/freetype/freetype-2.15.0.tar.gz) |
| common | 2026.1 | 2026.1 | sqlite3 3.54.0 | [blessing](licenses/sqlite3-3.54/) | [sqlite-autoconf-3540000.tar.gz](https://sqlite.org/2026/sqlite-autoconf-3540000.tar.gz) |
| common | 2026.1 | 2026.1 | tidy-html5 5.8.0 | [HTMLTIDY](licenses/tidy-html5-5.8/) | [5.8.0.tar.gz](https://github.com/htacg/tidy-html5/archive/refs/tags/5.8.0.tar.gz) |
| common | 2026.1 | 2026.1 | libxml2 2.15.4 | [MIT](licenses/libxml2-2.15/) | [libxml2-2.15.4.tar.xz](https://download.gnome.org/sources/libxml2/2.15/libxml2-2.15.4.tar.xz) |
| common | 2026.1 | 2026.1 | curl 8.23.0 | [curl](licenses/curl-8.23/) | [curl-8.23.0.tar.gz](https://curl.se/download/curl-8.23.0.tar.gz) |
| common | 2026.1 | 2026.1 | libxslt 1.1.45 | [MIT](licenses/libxslt-1.1/) | [libxslt-1.1.45.tar.xz](https://download.gnome.org/sources/libxslt/1.1/libxslt-1.1.45.tar.xz) |
| common | 2026.1 | 2026.1 | libzip 1.12.1 | [BSD-3-Clause](licenses/libzip-1.12/) | [libzip-1.12.1.tar.xz](https://libzip.org/download/libzip-1.12.1.tar.xz) |
| composer | stable | 2.10.3 | composer 2.10.3 | [MIT](licenses/composer-stable/) | [2.10.3.tar.gz](https://github.com/composer/composer/archive/refs/tags/2.10.3.tar.gz) |
| meilisearch | stable | 1.55.0 | meilisearch 1.55.0 | [MIT AND BUSL-1.1](licenses/meilisearch-stable/) | [v1.55.0.tar.gz](https://github.com/meilisearch/meilisearch/archive/refs/tags/v1.55.0.tar.gz) |
| mysql | 8.4 | 8.4.11 | mysql 8.4.11 | [GPL-2.0-only WITH Universal-FOSS-exception-1.0](licenses/mysql-8.4/) | [mysql-8.4.11.tar.gz](https://cdn.mysql.com/Downloads/MySQL-8.4/mysql-8.4.11.tar.gz) |
| nginx | 1.28 | 1.28.0 | nginx 1.28.0 | [BSD-2-Clause](licenses/nginx-1.28/) | [nginx-1.28.0.tar.gz](https://nginx.org/download/nginx-1.28.0.tar.gz) |
| php | 5.3 | 5.3.29 | php 5.3.29 | [PHP-3.01 AND Zend-2.0](licenses/php-5.3/) | [e611c85ab21c00bd81a623eafb51c8a0ac40dfef.tar.gz](https://github.com/shivammathur/php-src-backports/archive/e611c85ab21c00bd81a623eafb51c8a0ac40dfef.tar.gz) |
| php | 5.4 | 5.4.45 | php 5.4.45 | [PHP-3.01 AND Zend-2.0](licenses/php-5.4/) | [265592acdd43d84d2c33663f3f4f67432826e627.tar.gz](https://github.com/shivammathur/php-src-backports/archive/265592acdd43d84d2c33663f3f4f67432826e627.tar.gz) |
| php | 5.5 | 5.5.38 | php 5.5.38 | [PHP-3.01 AND Zend-2.0](licenses/php-5.5/) | [b37a20a42bbf86d198d0d21f8dbad7d6581c9286.tar.gz](https://github.com/shivammathur/php-src-backports/archive/b37a20a42bbf86d198d0d21f8dbad7d6581c9286.tar.gz) |
| php | 5.6 | 5.6.40 | php 5.6.40 | [PHP-3.01 AND Zend-2.0](licenses/php-5.6/) | [31b896540a30a5d170797a1171b04dd872b88c5b.tar.gz](https://github.com/shivammathur/php-src-backports/archive/31b896540a30a5d170797a1171b04dd872b88c5b.tar.gz) |
| php | 7.0 | 7.0.33 | php 7.0.33 | [PHP-3.01 AND Zend-2.0](licenses/php-7.0/) | [php-7.0.33.tar.xz](https://www.php.net/distributions/php-7.0.33.tar.xz) |
| php | 7.1 | 7.1.33 | php 7.1.33 | [PHP-3.01 AND Zend-2.0](licenses/php-7.1/) | [php-7.1.33.tar.xz](https://www.php.net/distributions/php-7.1.33.tar.xz) |
| php | 7.2 | 7.2.34 | php 7.2.34 | [PHP-3.01 AND Zend-2.0](licenses/php-7.2/) | [php-7.2.34.tar.xz](https://www.php.net/distributions/php-7.2.34.tar.xz) |
| php | 7.3 | 7.3.33 | php 7.3.33 | [PHP-3.01 AND Zend-2.0](licenses/php-7.3/) | [php-7.3.33.tar.xz](https://www.php.net/distributions/php-7.3.33.tar.xz) |
| php | 7.4 | 7.4.33 | php 7.4.33 | [PHP-3.01 AND Zend-2.0](licenses/php-7.4/) | [php-7.4.33.tar.xz](https://www.php.net/distributions/php-7.4.33.tar.xz) |
| php | 8.0 | 8.0.30 | php 8.0.30 | [PHP-3.01 AND Zend-2.0](licenses/php-8.0/) | [php-8.0.30.tar.xz](https://www.php.net/distributions/php-8.0.30.tar.xz) |
| php | 8.1 | 8.1.34 | php 8.1.34 | [PHP-3.01 AND Zend-2.0](licenses/php-8.1/) | [php-8.1.34.tar.xz](https://www.php.net/distributions/php-8.1.34.tar.xz) |
| php | 8.2 | 8.2.35 | php 8.2.35 | [PHP-3.01 AND Zend-2.0](licenses/php-8.2/) | [php-8.2.35.tar.xz](https://www.php.net/distributions/php-8.2.35.tar.xz) |
| php | 8.3 | 8.3.36 | php 8.3.36 | [PHP-3.01 AND Zend-2.0](licenses/php-8.3/) | [php-8.3.36.tar.xz](https://www.php.net/distributions/php-8.3.36.tar.xz) |
| php | 8.4 | 8.4.26 | php 8.4.26 | [PHP-3.01 AND Zend-2.0](licenses/php-8.4/) | [php-8.4.26.tar.xz](https://www.php.net/distributions/php-8.4.26.tar.xz) |
| php | 8.4 | 8.4.26 | apcu 5.1.28 | [PHP-3.01](licenses/apcu-5.1/) | [apcu-5.1.28.tgz](https://pecl.php.net/get/apcu-5.1.28.tgz) |
| php | 8.4 | 8.4.26 | xdebug 3.5.3 | [Xdebug-1.03](licenses/xdebug-3.5/) | [xdebug-3.5.3.tgz](https://xdebug.org/files/xdebug-3.5.3.tgz) |
| php | 8.4 | 8.4.26 | redis 6.3.0 | [PHP-3.01 AND BSD-2-Clause](licenses/redis-6.3/) | [redis-6.3.0.tgz](https://pecl.php.net/get/redis-6.3.0.tgz) |
| postgresql | 17 | 17.6 | postgresql 17.6 | [PostgreSQL](licenses/postgresql-17/) | [postgresql-17.6.tar.bz2](https://ftp.postgresql.org/pub/source/v17.6/postgresql-17.6.tar.bz2) |

Лицензия указана выражением SPDX. Тексты лицензий лежат в каталоге
`licenses/<компонент>-<ветка>/` и взяты из тарболов исходников тех же
версий, по которым собраны архивы. Composer, cloudflared, Meilisearch и MySQL
не собираются из исходников: в архив кладётся готовая сборка их авторов, а
ссылка в таблице ведёт на исходники той же версии.

SQLite — общественное достояние (SPDX `blessing`): отдельного файла
лицензии у него нет, посвящение автора — в комментарии в начале
`sqlite3.h`, поэтому в `licenses/sqlite3-<ветка>/` лежит этот заголовок.
