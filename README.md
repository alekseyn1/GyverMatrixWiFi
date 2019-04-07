![PROJECT_PHOTO](https://github.com/vvip-68/GyverMatrixWiFi/blob/master/proj_img.jpg)

# Адресная матрица на NodeMCU с управлением по WiFi
* [Описание проекта](#chapter-0)
* [Папки проекта](#chapter-1)
* [Схемы подключения](#chapter-2)
* [Материалы и компоненты](#chapter-3)
* [Как скачать и прошить](#chapter-4)
* [FAQ](#chapter-5)
* [Полезная информация](#chapter-6)

<a id="chapter-0"></a>
## Описание проекта
Этот проект основан на проекте AlexGyver ["Матрица на адресных светодиодах с управлением по Bluetooth"](https://github.com/AlexGyver/GyverMatrixBT)
#### Изменения по справнению с исходным пректом:
 - Поддержка только контроллера с большим объемом памятии наличием WiFi на борту - NodeMCU
 - Другие типы контроллеров (Arduino Mega + WiFi, Wemod D1) - не тестировались.
 - Удалена поддержка управления с кнопок
 - Удалена поддержка управления по Bluetooth
 - Удалена поддержка платы часов реального времени
 - Управление матрицей - через WiFi (локальная сеть)
 - Синхронизация времени с NTP сервером через интернет
 - Адаптированная программа управления матрицей на Andrioid
 - Изменены настройки режимов воспроизведения эффектов
 - Настройки режимов можно изменять из программы со смартфона
   - Яркость матрицы (для всех режимов)
   - Скорость эффектов - индивидуально для каждого режима
   - Наличие наложения часов на эффекты - индивидуально для каждого режима
   - Включение/исключение режима из списка автовоспроизведения
 - Настройки сохраняются в энергонезависимой памяти EEPROM
 - К режиму часов добавлен календарь
 - Настройка сервера синхронизации времени
 - Будильник "рассвет", настройки через программу на смартфоне 
 - Поддержка звука будильника  / звука рассвета звуковой платой MP3 DFPlayer
 - Настройки сетевого подключения (SSID и пароль) задаются в программе и сохраняются в EEPROM
 - Если не удается подключиться к сети (неверный пароль или имя сети) - создается точка подключения
   с именем MatrixAP, пароль 12341234, IP 192.168.4.1. Подключившись к точке доступа из приложения
   можно настроить параметры сети.    
 - Быстрое включение режимов лампы белого или заданного цвета из приложения (вся панель светится), 
   выключение панели, комбинация лампы с отображением часов, ночные часы (пониженная яркость).

## От исходного проекта сохранены следующие возможности:
#### Режимы:
 - Рисование
 - Загрузка картинок
 - Бегущая строка  
#### Эффекты:
 - "Дыхание" яркости
 - Смена цвета
 - Снегопад
 - Блуждающий кубик
 - Радуга
 - Огонь
 - The Matrix
 - Летающие частицы
 - Звездопад
 - Шумовые эффекты с разными цветовыми палитрами
 - Анимация
 - Часы  
#### Игры:
 - Змейка
 - Tетриc
 - Лабиринт  
 - Арканоид
 - Runner
 - Flappy bird
#### Возможности:
- Автоподключение к матрице при запуске
- Настройки яркости и скорости отображения
- Использование акселерометра в играх

<a id="chapter-1"></a>
## Папки
**ВНИМАНИЕ! Если это твой первый опыт работы с Arduino, читай [инструкцию](#chapter-4)**
- **libraries** - библиотеки проекта.
- **firmware** - прошивки для NodeMCU
- **schemes** - схемы подключения компонентов
- **sounds** - звуковые файлы будильника для размещения на SD-карте
- **Android** - файлы с приложениями, примерами для Android и Thunkable

<a id="chapter-2"></a>
## Схемы
![SCHEME](https://github.com/vvip-68/GyverMatrixWiFi/blob/master/schemes/scheme.jpg)

<a id="chapter-3"></a>
## Материалы и компоненты
### Ссылки оставлены на магазины
Полный список компонентов есть в статье https://alexgyver.ru/matrix_guide/
- NodeMCU http://ali.onl/1dVU http://ali.onl/1dVV
- Матрицы разные http://ali.ski/pw2ic
- Лента http://ali.ski/YdfMN
- Модульная гирлянда http://ali.ski/0h35RR
- Резисторы http://ali.ski/UEez2
- БП 5 Вольт http://ali.ski/3cNyj  http://ali.ski/qSKFK
- MP3 DFPlayer http://ali.onl/1gY1 http://ali.onl/1gY3

## Вам скорее всего пригодится
* [Всё для пайки (паяльники и примочки)](http://alexgyver.ru/all-for-soldering/)
* [Недорогие инструменты](http://alexgyver.ru/my_instruments/)
* [Все существующие модули и сенсоры Arduino](http://alexgyver.ru/arduino_shop/)
* [Электронные компоненты](http://alexgyver.ru/electronics/)
* [Аккумуляторы и зарядные модули](http://alexgyver.ru/18650/)

<a id="chapter-4"></a>
## Как скачать и прошить
* [Первые шаги с Arduino](http://alexgyver.ru/arduino-first/) - ультра подробная статья по началу работы с Ардуино, ознакомиться первым делом!
* Скачать архив с проектом
> На главной странице проекта (где ты читаешь этот текст) вверху справа зелёная кнопка **Clone or download**, вот её жми, там будет **Download ZIP**
* Установить библиотеки в  
`C:\Program Files (x86)\Arduino\libraries\` (Windows x64)  
`C:\Program Files\Arduino\libraries\` (Windows x86)
* **Подключить внешнее питание 5 Вольт**
* Подключить Ардуино к компьютеру
* Запустить файл прошивки (который имеет расширение .ino)
* Настроить IDE (COM порт, модель Arduino, как в статье выше)
* Настроить что нужно по проекту
* Нажать загрузить
* Скачать и установить на смартфон GyverMatrix
* Пользоваться  

## Настройки в коде
    LED_PIN 6           // пин ленты
    BRIGHTNESS 60       // стандартная маскимальная яркость (0-255)

    WIDTH 16            // ширина матрицы
    HEIGHT 16           // высота матрицы

    MATRIX_TYPE 0       // тип матрицы: 0 - зигзаг, 1 - последовательная
    CONNECTION_ANGLE 0  // угол подключения: 0 - левый нижний, 1 - левый верхний, 2 - правый верхний, 3 - правый нижний
    STRIP_DIRECTION 0   // направление ленты из угла: 0 - вправо, 1 - вверх, 2 - влево, 3 - вниз

    SCORE_SIZE 0        // размер букв счёта в игре. 0 - маленький (для 8х8), 1 - большой
    FONT_TYPE 1	        // (0 / 1) два вида маленького шрифта

    GLOBAL_COLOR_1 CRGB::Green    // основной цвет №1 для игр
    GLOBAL_COLOR_2 CRGB::Orange   // основной цвет №2 для игр
	
<a id="chapter-5"></a>
## FAQ
### Основные вопросы
В: Как скачать с этого грёбаного сайта?  
О: На главной странице проекта (где ты читаешь этот текст) вверху справа зелёная кнопка **Clone or download**, вот её жми, там будет **Download ZIP**

В: Скачался какой то файл .zip, куда его теперь?  
О: Это архив. Можно открыть стандартными средствами Windows, но думаю у всех на компьютере установлен WinRAR, архив нужно правой кнопкой и извлечь.

В: Я совсем новичок! Что мне делать с Ардуиной, где взять все программы?  
О: Читай и смотри видос http://alexgyver.ru/arduino-first/

В: Вылетает ошибка загрузки / компиляции!
О: Читай тут: https://alexgyver.ru/arduino-first/#step-5

### Вопросы по этому проекту

<a id="chapter-6"></a>
## Полезная информация
* [Cайт Alex Gyver](http://alexgyver.ru/)
* [Канал Alex Gyver на YouTube](https://www.youtube.com/channel/UCgtAOyEQdAyjvm9ATCi_Aig?sub_confirmation=1)
* [YouTube канал про Arduino](https://www.youtube.com/channel/UC4axiS76D784-ofoTdo5zOA?sub_confirmation=1)
* [Видеоуроки по пайке](https://www.youtube.com/playlist?list=PLOT_HeyBraBuMIwfSYu7kCKXxQGsUKcqR)
* [Видеоуроки по Arduino](http://alexgyver.ru/arduino_lessons/)
