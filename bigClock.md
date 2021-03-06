# Big Clocks

Светодиодная лента и картонные упаковки из Икеа на ресайклинг – отличное "дано" для светодиодного табло.

![BigClock.jpg](https://github.com/tolikivanov/photo/raw/master/BigClock.jpg)

Какого табло?
<cut />

Любую информацию, состоящую из цифр (время, цену, курс рубля), можно показать с помощью семисегментных индикаторов. Они хорошо читаются даже на большом расстоянии и просты в управлении.

Как "скрафтить" из картона и светодиодной ленты по-настоящему большие индикаторы и запустить на них часы – расскажу в этой статье.

## Что для этого понадобится
### Материалы:
-   Картон;
-   [Светодиодная лента, 12 В](https://amperka.ru/product/white-led-strip-sealed?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   Листы бумаги 80 г/м2;
-   Провода;
-   [Контроллер Ардуино](https://amperka.ru/product/arduino-uno?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   4 х [Octofet (сборка из 8-ми MOSFET транзисторов)](https://amperka.ru/product/zelo-p-fet?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Модуль часов реального времени](https://amperka.ru/product/troyka-rtc?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Блок питания 12В](https://amperka.ru/product/power-supply-adapter-robiton-tn2000s?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);

### Инструменты:
-   Канцелярский нож;
-   Ножницы;
-   [Кусачки](https://amperka.ru/product/side-cutting-pliers?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   Клей-карандаш;
-   [Отвертки, шлицевая и крест](https://amperka.ru/product/screw-kit?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Паяльник](https://amperka.ru/product/soldering-iron-goot-30w?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Олово](https://amperka.ru/product/solder-08mm-small?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Флюс](https://amperka.ru/product/flux-lti120?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Провод USB](https://amperka.ru/product/usb-cable?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   Линейка;
-   Карандаш;

## Как собрать

Канцелярским ножом вырезаем из картона корпус будущих индикаторов.

![ninja-cut.gif](https://github.com/tolikivanov/photo/raw/master/ninja-cut.gif)

На одну из сторон (теперь она будет тыльной) наклеим вдоль рёбер жёсткости дополнительные "прямоугольнички", вырезанные из того же картона. Сквозь них пустим провода.

![Wire-chanel.jpg](https://github.com/tolikivanov/photo/raw/master/Wire-chanel.jpg)

Для подсветки сегмента будущего индикатора хватит 10 сантиметров отрезка светодиодной ленты. Припаяем к нему пару проводов.

![led-wire.jpg](https://github.com/tolikivanov/photo/raw/master/led-wire.jpg)

Рассеивателем для ленты станет цилиндр, вырезанный и свёрнутый из обычной офисной бумаги А4 и склеенный клеем-карандашом.

![cylinder.gif](https://github.com/tolikivanov/photo/raw/master/cylinder.gif)

Теперь приклеим цилиндры к каркасу, пропустив провода в отверстия.

![join-cylinder.jpg](https://github.com/tolikivanov/photo/raw/master/join-cylinder.jpg)

После того, как все цилиндры приклеены, можно заняться кабель-менеджментом и спрятать все провода внутрь заранее подготовленных каналов.

![cable-management.gif](https://github.com/tolikivanov/photo/raw/master/cable-management.gif)

Торцы цилиндров закроем заглушками, вырезанными всё из того же картона.

![stub.jpg](https://github.com/tolikivanov/photo/raw/master/stub.jpg)

То же самое осталось провернуть ещё для 3-х цифр.

## Управление
### Проблема №1. Ток

[Привычными индикаторами](https://amperka.ru/product/7-segment-led?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), каждый сегмент которых потребляет всего 20-30 мА, можно управлять напрямую контроллером. Например, с входов-выходов популярной Arduino Uno можно снять до 40 мА.

Для управления светодиодными лентами с большим током между пинами контроллера и каждым сегментом дополнительно придется использовать [транзисторы](https://amperka.ru/product/troyka-mosfet-p-channel?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) или [реле](https://amperka.ru/product/troyka-mini-relay?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), способные пропустить через себя такой ток.

![commutation.jpg](https://github.com/tolikivanov/photo/raw/master/commutation.jpg)

Реле – шумно и громоздко, а вот силовые ключи на MOSFET транзисторах – кажется, то, что нужно.

### Проблема №2. Контакты

Чтобы управлять одним индикатором понадобится 7 выходов микроконтроллера. Четыре индикатора и разделитель – это 29, а у Ардуино Уно выходов всего 20.

В [готовых индикаторных сборках](https://amperka.ru/product/troyka-quad-display?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) используют [выходные сдвиговые регистры](https://amperka.ru/product/74hc595-shift-out-register?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) — микросхемы для увеличения количества цифровых выходов. Она управляется тремя пинами, а на выходе даёт целых восемь.

![display.jpg](https://github.com/tolikivanov/photo/raw/master/display.jpg)

### Проблема №3. Габариты

Хоть я и психанул с размером будущих часов, но схема на отдельных модулях – это слишком уж громоздко.

![a-lot-of-fets.jpg](https://github.com/tolikivanov/photo/raw/master/a-lot-of-fets.jpg)

### Решение

Гораздо более элегантно будет смотреться [модуль OctoFet](https://amperka.ru/product/zelo-p-fet?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) - готовая сборка из сдвигового регистра и 8-ми полевиков, каждый из которых рассчитан на напряжение до 30 вольт и может пропустить через себя до 3-х ампер.

![octofet.jpg](https://github.com/tolikivanov/photo/raw/master/octofet.jpg)

## Подключение

Провода от каждого сегмента индикатора подключим к клеммникам выходов Octofet-а.

![Connection.png](https://github.com/tolikivanov/photo/raw/master/Connection.png)

Сам Octofet, чтобы не «болтался», закрепим на основании, которое можно вырезать всё из того же картона.

![connectOctofet.jpg](https://github.com/tolikivanov/photo/raw/master/connectOctofet.jpg)

Подключать модули к Ардуино удобно через [Troyka Shield](https://amperka.ru/product/arduino-troyka-shield?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content). Остается просто соединить всё шлейфами.

![Arduino-Test-Connection.png](https://github.com/tolikivanov/photo/raw/master/Arduino-Test-Connection.png)

## Прошивка

Программировать контроллер будем через [Arduino IDE](http://wiki.amperka.ru/%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-arduino-ide).
Для работы с Octofet-ом и часами реального времени нужно дополнительно скачать и установить пару библиотек.
  - [Библиотека OctoFet](https://github.com/amperka/AmperkaFet)
  - [Библиотека TroykaRTC](https://github.com/amperka/TroykaRTC)
  - [Как устанавливать библиотеки в Arduino IDE](http://wiki.amperka.ru/%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5:%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B8#%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B8)

В зависимости от состояния транзисторов в сборке, на индикаторе будут загораться необходимые сегменты, тем самым отображая цифру.

![bitmap.gif](https://github.com/tolikivanov/photo/raw/master/bitmap.gif)

Загрузим тестовый пример для одного индикатора в Ардуино.

```cpp
// библиотека для работы с модулями по интрефейсу SPI
#include <SPI.h>
// библиотека для работы со сборкой силовых ключей
#include <AmperkaFET.h>
// пин выбора устройства на шине SPI
#define PIN_CS  7

// кол-во сегментов в индикаторе
#define SEGMENT_COUNT       8
 
// префикс «0b» означает, что целое число за ним записано в
// в двоичном коде. Единицами мы обозначим номера сегментов
// индикатора, которые должны быть включены для отображения
// арабской цифры. Всего цифр 10, поэтому в массиве 10 чисел.
// Нам достаточно всего байта (англ. byte, 8 бит) для хранения
// комбинации сегментов для каждой из цифр.
byte numberSegments[10] = {
  0b11101110, 0b00100100, 0b11110010, 0b10110110, 0b00111100,
  0b10011110, 0b11011110, 0b00100110, 0b11111110, 0b10111110,
};

// создаём объект mosfet для работы со сборкой силовых ключей
// передаём номер пина выбора устройства на шине SPI
FET mosfet(PIN_CS);
 
void setup()
{
  // начало работы с силовыми ключами
  mosfet.begin();
}
 
void loop()
{
  // определяем число, которое собираемся отображать. Пусть им
  // будет номер текущей секунды, зацикленный на десятке
  int number = (millis() / 1000) % 10;
  // получаем код, в котором зашифрована арабская цифра
  int mask = numberSegments[number];
  // для каждого из 7 сегментов индикатора...
  for (int i = 0; i < SEGMENT_COUNT; ++i) {
    // ...определяем: должен ли он быть включён. Для этого
    // считываем бит (англ. read bit), соответствующий текущему
    // сегменту «i». Истина — он установлен (1), ложь — нет (0)
    boolean enableSegment = bitRead(mask, i);
    // включаем/выключаем сегмент на основе полученного значения
    mosfet.digitalWrite(i, enableSegment);
  }
}
```
Если всё подключено верно, мы увидим заветные цифры.

![singleDigit.gif](https://github.com/tolikivanov/photo/raw/master/singleDigit.gif)

Теперь можно соединить все индикаторы в одну цепочку, добавить [модуль часов реального времени](https://amperka.ru/product/troyka-rtc?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) и разделительный сегмент в виде точки.

![fullSchem.png](https://github.com/tolikivanov/photo/raw/master/fullSchem.png)

### Исходный код

Загрузим в плату Ардуино прошивку для вывода текущего времени.

```cpp
// библиотека для работы с модулями по интерфейсу SPI
#include <SPI.h>
// библиотека для работы I²C
#include <Wire.h>
// библиотека для работы со сборкой силовых ключей
#include <AmperkaFET.h>
// библиотека для работы с часами реального времени
#include <TroykaRTC.h>

// пин выбора сборки устройств на шине SPI
#define PIN_CS  2
 
// префикс «0b» означает, что целое число за ним записано в
// в двоичном коде. Единицами мы обозначим номера сегментов
// индикатора, которые должны быть включены для отображения
// арабской цифры. Всего цифр 10, поэтому в массиве 10 чисел.
// Нам достаточно всего байта (англ. byte, 8 бит) для хранения
// комбинации сегментов для каждой из цифр.
byte numberSegments[10] = {
  0b11101110, 0b00100100, 0b11110010, 0b10110110, 0b00111100,
  0b10011110, 0b11011110, 0b00100110, 0b11111110, 0b10111110,
};
 
// создаём объект mosfet для работы со сборкой силовых ключей
// передаём номер пина выбора устройств на шине SPI
// и количество устройств подключённых в цепочке
FET mosfet(PIN_CS, 4);

// создаём объект для работы с часами реального времени
RTC clock;

void setup() {
   Serial.begin(9600);
  // начало работы с силовыми ключами
  mosfet.begin();
    // инициализация часов
  clock.begin();
  // метод установки времени и даты в модуль вручную
  // clock.set(10,25,45,27,07,2005,THURSDAY);    
  // метод установки времени и даты автоматически при компиляции
  clock.set(__TIMESTAMP__);
}

void loop() {
  // запрашиваем данные с часов  
  clock.read();

  // делим минуты и часы на разряды и отображаем на индикаторах
  showDigit (0, clock.getHour() / 10);
  showDigit (1, clock.getHour() % 10);
  showDigit (2, clock.getMinute() / 10);
  showDigit (3, clock.getMinute() % 10); 

  // мигаем разделителем
  mosfet.digitalWrite(1, 0, HIGH);  
  delay(1000);
  mosfet.digitalWrite(1, 0, LOW);
  delay(1000);
}

void showDigit (int module, int digit ){
  // получаем код, в котором зашифрована арабская цифра
  int mask = numberSegments[digit];
  // для каждого из 7 сегментов индикатора...
      for (int i = 0; i < 8; ++i) {
    // ...определяем: должен ли он быть включён. Для этого
    // считываем бит (англ. read bit), соответствующий текущему
    // сегменту «i». Истина — он установлен (1), ложь — нет (0)
    boolean enableSegment = bitRead(mask, i);
    // включаем/выключаем сегмент на основе полученного значения
    mosfet.digitalWrite(module, i, enableSegment);
  }
}
```

> Чтобы после прошивки и включения часов время считывалось с модуля RTC -
> закоментируйте оба метода `clock.set()` и загрузите код снова;

![main.jpg](https://github.com/tolikivanov/photo/raw/master/main.jpg)

Это лишь пример того, как можно сделать подобные индикаторы. Добавьте [модуль Bluetooth](https://amperka.ru/product/troyka-ble?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) для настройки и управления, или звуковое оповещение [зумером](https://amperka.ru/product/troyka-buzzer?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), чтобы превратить часы в будильник. А лучше и то, и другое.

А на этом у меня всё!
Пока!
