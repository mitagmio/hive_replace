# Замена работающего linux на HIVE OS

запуск


## Краткие пояснения
Минимум RAM: 4 Gb

Из локальной консоли не работает. Пытался сделать, но приходится несколько раз вручную перелогиниваться. Поэтому, посчитал, что смысла в подобном немного. С локальной консоли проще воспользоваться флешером.

По SSH процесс идет в два приема. После окончания подготовки (создания временной ФС и смещения туда корня), скрипт закончит работу. Для продолжения нужно открыть новую сессию SSH и запустить скрипт повторно. Первая сессия схлопнется сама (если не закрыли руками).

В начале работы пользователь должен ввести FARM_HASH и интернет-ссылку или локальный путь (или nfs путь) до zip-файла с образом Hive.
После окончания работы скрипта - происходит жесткий ребут через sysrq. После загрузки сразу начинает работать (используя FARM_HASH).

Встроена примитивная защита от дурака. Предотвращение запуска из под локальной консоли и предотвращения повторного запуска в той же SSH-сессии, после завершения первого этапа.

Проверено на Ubunta, Debian, Mint. Скорее всего будет без проблем работать на всех дистрибутивах основанных на Debian. И вероятно на других с системой инициализацией SystemD.
Под другие устаревшие схемы инициализации, типа SystemV, скорее всего, нужна дополнительная адаптация.
