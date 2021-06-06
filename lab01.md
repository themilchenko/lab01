# ***Laboratory work 1***

`Цель работы`:
лабораторная работа посвещена изучению 
утилит для разработки проектов

>Выполнение `Tutorial`:

```
export GITHUB_USERNAME=themilchenko
export GIST_TOKEN=8544a7f318fa9619b33318b92a2b32e799045021
alias edit=<nano|vi|vim|subl>

mkdir -p ${GITHUB_USERNAME}/workspace
cd ${GITHUB_USERNAME}/workspace
pwd
cd ..
pwd

mkdir -p workspace/tasks/
mkdir -p workspace/projects/
mkdir -p workspace/reports/
cd workspace

wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
tar -xf node-v6.11.5-linux-x64.tar.xz
rm -rf node-v6.11.5-linux-x64.tar.xz
mv node-v6.11.5-linux-x64 node

ls node/bin
echo ${PATH}
export PATH=${PATH}:`pwd`/node/bin
echo ${PATH}
mkdir scripts
cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
source scripts/activate

gem install gist

(umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```

>Результат выполнения ЛР:

- `export LAB_NUMBER=01`
  
- `git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}`
  >>```Cloning into 'tasks/lab01'...
  >>remote: Enumerating objects: 74, done.
  >>remote: Counting objects: 100% (3/3), done.
  >>remote: Compressing objects: 100% (3/3), done.
  >>remote: Total 74 (delta 0), reused 0 (delta 0), pack-reused 71
  >>Unpacking objects: 100% (74/74), done.
- `mkdir reports/lab${LAB_NUMBER}`
- `cp tasks/lab${LAB_NUMBER}/README.md`
- `reports/lab${LAB_NUMBER}/REPORT.md`

>Выполнение ДЗ

- `Скачайте библиотеку boost с помощью утилиты wget.`
>`wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`
>>```--2021-06-05 19:10:26--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
>>Распознаётся sourceforge.net (sourceforge.net)… 216.105.38.13
>>Подключение к sourceforge.net (sourceforge.net)|216.105.38.13|:443... соединение установлено.
>>HTTP-запрос отправлен. Ожидание ответа… 301 Moved Permanently
>>Адрес: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [переход]
>>--2021-06-05 19:10:27--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
>>Повторное использование соединения с sourceforge.net:443.
>>HTTP-запрос отправлен. Ожидание ответа… 302 Found
>>Адрес: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [переход]
>>--2021-06-05 19:10:27--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
>>Повторное использование соединения с sourceforge.net:443.
>>HTTP-запрос отправлен. Ожидание ответа… 302 Found
>>Адрес: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABgu6Hzl_M-iM5sL9B70Vrp7-mkHPrebSjuv4ltP1edpCkAtke5GF1MFFyHB4tMmARBpFmDRoXoHQvP68AcWHVY1KCVpg%3D%3D&use_mirror=deac-ams&r= [переход]
>>--2021-06-05 19:10:27--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABgu6Hzl_M-iM5sL9B70Vrp7-mkHPrebSjuv4ltP1edpCkAtke5GF1MFFyHB4tMmARBpFmDRoXoHQvP68AcWHVY1KCVpg%3D%3D&use_mirror=deac-ams&r=
>>Распознаётся downloads.sourceforge.net (downloads.sourceforge.net)… 216.105.38.13
>>Подключение к downloads.sourceforge.net (downloads.sourceforge.net)|216.105.38.13|:443... соединение установлено.
>>HTTP-запрос отправлен. Ожидание ответа… 302 Found
>>Адрес: https://deac-ams.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz [переход]
>>--2021-06-05 19:10:29--  https://deac-ams.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz
>>Распознаётся deac-ams.dl.sourceforge.net (deac-ams.dl.sourceforge.net)… 185.34.27.55
>>Подключение к deac-ams.dl.sourceforge.net (deac-ams.dl.sourceforge.net)|185.34.27.55|:443... соединение установлено.
>>HTTP-запрос отправлен. Ожидание ответа… 200 OK
>>Длина: 111710205 (107M) [application/x-gzip]
>>Сохранение в: «boost_1_69_0.tar.gz»
>>
>>boost_1_69_0.tar.gz                                100%[================================================================================================================>] 106,53M  12,2MB/s    за 6,4s
>>
>>2021-06-05 19:10:36 (16,6 MB/s) - «boost_1_69_0.tar.gz» сохранён [111710205/111710205]```

- `Разархивируйте скаченный файл в директорию ~/boost_1_69_0`
>`tar -xf boost_1_69_0.tar.gz`

-`Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.`
> `tree -aL 1 | wc -l`
>> 6

- `Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.`
> `tree -aR | wc -l`
>> 66834 

- `Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).`
> `find . -name "*.cpp" | wc -l`
>> 13774
> 
> `find . -name "*.h" -o -name "*.hpp" | wc -l`
>> 15208
>
> `find . -not -name "*.cpp" -o -not -name "*.h" -o -not -name "*.hpp" -type f| wc -l`
>> 66832

- `Найдите полный пусть до файла any.hpp внутри библиотеки boost.`
> `find . -name 'any.hpp'`
>> ```./boost_1_69_0/boost/fusion/include/any.hpp
>>./boost_1_69_0/boost/fusion/algorithm/query/any.hpp
>>./boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
>>./boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
>>./boost_1_69_0/boost/proto/detail/any.hpp
>>./boost_1_69_0/boost/type_erasure/any.hpp
>>./boost_1_69_0/boost/hana/fwd/any.hpp
>>./boost_1_69_0/boost/hana/any.hpp
>>./boost_1_69_0/boost/any.hpp
>>./boost_1_69_0/boost/xpressive/detail/utility/any.hpp```

- `Выведите в консоль все файлы, где упоминается последовательность boost::asio.`
> `find . -name 'any.hpp'`
>> ```./boost_1_69_0/boost/beast/experimental/core/impl/timeout_socket.hpp
>>./boost_1_69_0/boost/beast/experimental/core/impl/flat_stream.ipp
>>./boost_1_69_0/boost/beast/experimental/core/impl/timeout_service.ipp
>>./boost_1_69_0/boost/beast/experimental/core/flat_stream.hpp
>>./boost_1_69_0/boost/beast/experimental/core/ssl_stream.hpp
>>./boost_1_69_0/boost/beast/experimental/core/timeout_service.hpp
>>./boost_1_69_0/boost/beast/experimental/core/timeout_socket.hpp
>>./boost_1_69_0/boost/beast/experimental/core/detail/impl/timeout_service.ipp
>>./boost_1_69_0/boost/beast/experimental/core/detail/service_base.hpp
>>./boost_1_69_0/boost/beast/experimental/core/detail/flat_stream.hpp
>>./boost_1_69_0/boost/beast/experimental/core/detail/timeout_service.hpp
>>./boost_1_69_0/boost/beast/experimental/test/impl/stream.ipp
>>./boost_1_69_0/boost/beast/experimental/test/stream.hpp
>>./boost_1_69_0/boost/beast/experimental/http/impl/icy_stream.ipp
>>  ...

- `Скомпилирутйе boost.`

- `Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.`
> `mv boost_compil/ boost-libs`

- `Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.`
> `du -h`
>> ```8,0K	./boost_1_69_0/tools/inspect/doc
>> 16K	./boost_1_69_0/tools/inspect/build/msvc
>> 20K	./boost_1_69_0/tools/inspect/build
>> 204K	./boost_1_69_0/tools/inspect
>> 8,0K	./boost_1_69_0/tools/check_build/test
>> 12K	./boost_1_69_0/tools/check_build
>> 4,0K	./boost_1_69_0/tools/quickbook/test/xinclude/sub
>> 84K	./boost_1_69_0/tools/quickbook/test/xinclude
>> 52K	./boost_1_69_0/tools/quickbook/test/snippets
>> 80K	./boost_1_69_0/tools/quickbook/test/unit
>> 4,0K	./boost_1_69_0/tools/quickbook/test/python/sub1
>> 4,0K	./boost_1_69_0/tools/quickbook/test/python/sub2
>> 84K	./boost_1_69_0/tools/quickbook/test/python
>> 4,0K	./boost_1_69_0/tools/quickbook/test/include/glob2/glob2-1
>> 8,0K	./boost_1_69_0/tools/quickbook/test/include/glob2
>> 4,0K	./boost_1_69_0/tools/quickbook/test/include/sub
>> 4,0K	./boost_1_69_0/tools/quickbook/test/include/glob1/glob1-1
>> 8,0K	./boost_1_69_0/tools/quickbook/test/include/glob1
>> 556K	./boost_1_69_0/tools/quickbook/test/include
>> 52K	./boost_1_69_0/tools/quickbook/test/versions
>>                  ...

- `Найдите топ10 самых "тяжёлых".`
> `find . -type f -exec du {} + | sort -rn | head`
>> ```231072	./boost_1_69_0.tar.gz
>> 23096	./boost_1_69_0/libs/math/doc/math.pdf
>> 7512	./boost_1_69_0/status/expected_results.xml
>> 6096	./boost_1_69_0/libs/gil/io/test_images/raw/RAW_CANON_D30_SRGB.CRW
>> 5520	./boost_1_69_0/libs/asio/doc/reference.qbk
>> 5472	./boost_1_69_0/libs/algorithm/test/search_test_data/0001.corpus
>> 4552	./boost_1_69_0/boost/typeof/vector200.hpp
>> 4512	./boost_1_69_0/libs/contract/doc/html/contract.docbook
>> 4400	./boost_1_69_0/libs/math/test/ellint_rg.ipp
>> 4096	./boost_1_69_0/libs/intrusive/doc/autodoc.xml