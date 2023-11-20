# cabbage_run

## ФИО

Шилов Андрей Викторович

## Подробное текстовое описание алгоритмов генерации комнат и их содержимого

Алгоритм основан на процедурной генерации 5 стен (пол, правая, левая, передняя и задняя стена) - каждая стена это результат работы двух циклов for ставящих мэш блок на соответсвующие координаты 
Количесво блоков в стене опредалеется случайно перед генерацией комнаты и зависит от уровня 

После того как сами стены и пол сгенерировались, начинаем генерировать ловушки: статические(неподвижные) и движущиеся. Так же в цикле for отвечающим за количесво получаем рандомные координапты на полу и спавним ловушку на это местоположение. Количесво ловушек так же зависит от уровня и его сложности. Сначала раставляем блоки, потом добавляем движущиеся ловушки. После этого смотрим на сгенерированный заранее максимальный уровень (от 6 до 10) и провереям, что если это последний уровень то генерируем объект завершения игры (золотой шар), а если будут еще уровни, то генерируем две двери: от угла СЛЕВА **ОБЫЧНАЯ** свтелая дверь, ведущая к уровню без востановления хп и СПРАВА **СЛОЖНАЯ** темная дверь, ведущая к более сложному уровню, где можно востановить хп. Соответсвенно, если в предыдущей комнате игрок прошел через сложную дверь, то было установлено значение isHard = True и тогда при генерации текущего уровня мы генерируем предмет для востановления здоровья (золотая статуя).

При генерации ловушек учиывается как уровень (по счету), пройденный игроком, так и коэффицент сложности, который накапливается если выбирать Сложные двери

## Описание принципа изменения уровня сложности в вашей игре

Увеличивается размер комнаты и количество ловушек (сначала пропорционально увеличению уровня, потом рост комнаты останавливается, а ловушки только прибавляются), так в последних комнатах ловушек становится многократно больше изначального количества и выбрать оптимальный путь уже совсем не просто 

При переходе на новый уровень увечличивается значение перемнной **level** в GameInsnance, при выборе сложной двери - значение **hadr**

## Описание всех значимых реализованных сверх условия дополнений

Помимо генерации комнаты, есть стартовое меню с кнопками **начала** и **завершения** игры, меню проигрыша с вариантами кнопок **сыграть заново** и **перейти в меню**,
победное меню с кнопкой **перейти в основное меню**

## Ссылки на готовые проекты, из которых были взяты части кода с пояснениями 

Все возможные видео на ютубе

В основе смотрел плейлист https://www.youtube.com/watch?si=PxAEqxTqGn_UdGZ1&v=XgIDH42RHWQ&feature=youtu.be
ХП -> https://www.youtube.com/watch?v=kZVIa2uWOiM
создание персонажа и его движений -> плейлист https://www.youtube.com/watch?v=TuJtz3Mqxsk&list=PL-jhyBQNFD45anyATNhx2kREaK9QbdF9U&index=2

## Пример игры 

![](/video/1.MOV)
