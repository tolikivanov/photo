![BigClock.jpg](https://habrastorage.org/webt/wa/cf/dh/wacfdhwpudt8xswggtkuapqndsy.jpeg)

Я никогда не хотел себе домой часы. Наручные или в телефоне — их вполне достаточно, чтоб ориентироваться во времени. А вот о какой-нибудь подсветке в комнату я периодически помышляю. При этом у меня, как и у многих других, стоит лампа на столе и с потолка свисает скушная люстра.

Сидеть в самоизоляции и полумраке — та ещё перспектива. Так светодиодная лента и картонные упаковки из Икеа на ресайклинг стали отличным условием «дано» для светодиодного табло, которое я полюбил.
<cut text="— Какого табло?"/>

Просто светильника — мало. Такой у меня уже есть. Я хотел, чтобы новый нёс какую-нибудь информацию. Например, мог отображать уровень температуры в комнате или что-то ещё...

Часы. Большие часы. Слышу доносящиеся откуда-то голоса, а воображение начинает выстраивать всяческие образы.

Самым простым и понятным мне показался вариант в виде семисегментных индикаторов. А что? Сделаю каркас из гофрокартона, нарежу отрезков светодиодной ленты и закреплю их на нём в форме восьмёрки. Звучит несложно.

## Что для этого понадобится

Есть 100 вариантов, где можно достать железо для этого проекта. Никаких особых, редких или проприетарных модулей в нём нет; главное — концепция. Я, однако, работаю в Амперке, поэтому взял всё необходимое в конторе. Чего и вам желаю.
Итак, мой комплект: 

### Материалы:
-   [Светодиодная лента 12 В](https://amperka.ru/product/white-led-strip-sealed?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Контроллер Ардуино](https://amperka.ru/product/arduino-uno?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   4× [Octofet (сборка из 8-ми MOSFET транзисторов)](https://amperka.ru/product/zelo-p-fet?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Модуль часов реального времени](https://amperka.ru/product/troyka-rtc?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Блок питания 12В](https://amperka.ru/product/power-supply-adapter-robiton-tn2000s?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   Картон;
-   Листы бумаги 80 г/м²;
-   Провода.

### Инструменты:
-   [Паяльник](https://amperka.ru/product/soldering-iron-goot-30w?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Кусачки](https://amperka.ru/product/side-cutting-pliers?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Набор отвёрток](https://amperka.ru/product/screw-kit?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Олово](https://amperka.ru/product/solder-08mm-small?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Флюс](https://amperka.ru/product/flux-lti120?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   [Провод USB](https://amperka.ru/product/usb-cable?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content);
-   Клей-карандаш;
-   Канцелярский нож;
-   Ножницы;
-   Линейка;
-   Карандаш.

## Как собрать

Я как ниндзя вырезал канцелярским ножом основу для будущего индикатора.

![ninja-cut.gif](https://habrastorage.org/webt/lk/xh/3c/lkxh3cji5ebvbkvegmks9qigmfg.gif)

Подсвечивать каждый сегмент будет 10-сантиметровый отрезок светодиодной ленты, к которому я припаял пару проводов.

![led-wire.jpg](https://habrastorage.org/webt/9s/e3/2m/9se32mf_gn-wrurkmk8lg1efp2m.jpeg)

На одну из сторон индикатора (теперь она будет тыльной) наклеил дополнительные «прямоугольнички», вырезанные из того же картона вдоль рёбер жёсткости. Сквозь эти рёбра я пущу провода от сегментов.

Сейчас мне это кажется простым решением, а тогда я уже начинал аккуратненько замахиваться микроскопом по гвоздю, чтобы спрятать бухту торчащих проводов. 

![Wire-chanel.jpg](https://habrastorage.org/webt/m6/m-/sh/m6m-shyfkmu0wcmx9zdfkim40jy.jpeg)

Рассеиватель для сегмента я сделал в форме цилиндра, который вырезал и свернул из обычной офисной бумаги А4 и склеил клеем-карандашом.

![cylinder.gif](https://habrastorage.org/webt/li/gs/nw/ligsnwndzfemk6bkbc88gazag6c.gif)

Готовые цилиндры приклеил к каркасу индикатора и пропустил провода в отверстия.

![join-cylinder.jpg](https://habrastorage.org/webt/mi/uf/cw/miufcwe57e2s4nka8ooomwh5m78.jpeg)

После того, как все цилиндры приклеены, можно заняться кабель-менеджментом и спрятать все провода внутрь заранее подготовленных каналов.

![cable-management.gif](https://habrastorage.org/webt/wn/a5/hw/wna5hwvnrrcpxk4rcuca_tpizys.gif)

Торцы цилиндров я закрыл заглушками, вырезанными всё из того же картона. 

![stub.jpg](https://habrastorage.org/webt/r9/mf/ah/r9mfahojfbpez1a8yjd02j4iyza.jpeg)

Столько резки, склейки и прочего... Я начинал не выдерживать, поэтому резал эти кругляшки уже лазерным станком.

![laser-cut.jpg](https://habrastorage.org/webt/wd/7k/qn/wd7kqnalo6zitrqlycjnlq6lrcs.jpeg)

Иначе стоит запастись терпением, вырезая такое количество деталей канцелярским ножом.

## Управление

Когда индикатор собран — самое время подумать, как им рулить.
И тут меня поджидало несколько «сюрпризов».

### Сюрприз первый. Ток

[Привычными индикаторами](https://amperka.ru/product/7-segment-led?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), каждый сегмент которых потребляет всего 20-30 мА, можно управлять напрямую контроллером. Например, с входов-выходов популярной Arduino Uno можно снять до 40 мА.

Каждый из сегментов моего индикатора потребляет в два раза больше допустимого тока Uno. Для управления ими придётся дополнительно использовать [транзисторы](https://amperka.ru/product/troyka-mosfet-p-channel?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) или [реле](https://amperka.ru/product/troyka-mini-relay?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), способные пропустить через себя такой ток.

![commutation.jpg](https://habrastorage.org/webt/4i/zb/fs/4izbfsfaolbkat5h4lkj2yopvdk.jpeg)

Реле — шумно и громоздко для такой задачи, а вот силовые ключи на MOSFET-транзисторах — кажется, то, что нужно.

### Сюрприз второй. Контакты

Чтобы управлять одним индикатором, понадобится 7 выходов микроконтроллера. Четыре индикатора и разделитель — это 29, а у Ардуино Уно выходов всего 20.

В [готовых индикаторных сборках](https://amperka.ru/product/troyka-quad-display?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) используют [выходные сдвиговые регистры](https://amperka.ru/product/74hc595-shift-out-register?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) — микросхемы для увеличения количества цифровых выходов. Они управляются тремя пинами, а на выходе дают целых восемь.

![display.jpg](https://habrastorage.org/webt/1x/sz/z_/1xszz_6vk6llwfo0_xuar63dx4c.jpeg)

### Третий сюрприз. Габариты

Собрав схему из восьми силовых ключей и сдвигового регистра, становится очевидно — такое управление много радости не принесёт.

![a-lot-of-fets.jpg](https://habrastorage.org/webt/un/yl/bf/unylbfzrmtgtymy76lsgrcnnmsi.jpeg)

### Решение всех проблем!

С подобными задачами лучше всего справится [модуль Octofet](https://amperka.ru/product/zelo-p-fet?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content). Это компактная сборка из сдвигового регистра и 8-ми полевиков, каждый из которых может пропустить через себя пару ампер, выглядит гораздо веселее.

![octofet.jpg](https://habrastorage.org/webt/uo/8w/un/uo8wunadvyzqx4c1o36yi64_nhe.jpeg)

## Подключение

Провода от каждого сегмента индикатора я подключил к клеммникам выходов Octofet’а.

![Connection.png](https://habrastorage.org/webt/dy/c1/3n/dyc13nrns22j6d8g6qfjljjaxfw.png)

А сам Octofet, чтобы не болтался, закрепил на основании, которое тоже вырезал из картона.

![connectOctofet.jpg](https://habrastorage.org/webt/xj/n3/jz/xjn3jzqhysjfxl70qiud46cjbl0.jpeg)

Подключать модули к Ардуино я буду через [Troyka Shield](https://amperka.ru/product/arduino-troyka-shield?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content). Остаётся просто соединить всё шлейфами. 

![Arduino-Test-Connection.png](https://habrastorage.org/webt/xs/dk/r9/xsdkr9o9kzkoleut8sv6ipoa13q.png)

Теперь, в зависимости от состояния транзисторов в сборке, на индикаторе должны будут загораться необходимые сегменты, тем самым отображая цифру.

![bitmap.gif](https://habrastorage.org/webt/g7/hi/fg/g7hifgxzfkxbmhb91je0sl-ceyw.gif)

## Прошивка

Программировать контроллер буду через [Arduino IDE](http://wiki.amperka.ru/%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-arduino-ide).
Для работы с Octofet’ом и часами реального времени дополнительно надо будет скачать и установить пару библиотек.
  - [Библиотека OctoFet](https://github.com/amperka/AmperkaFet)
  - [Библиотека TroykaRTC](https://github.com/amperka/TroykaRTC)
  - [Как устанавливать библиотеки в Arduino IDE](http://wiki.amperka.ru/%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5:%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B8#%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B8)

Чтобы проверить, всё ли правильно собрано, в Arduino нужно загрузить тестовый скетч.

```cpp
// библиотека для работы с модулями по интрефейсу SPI
#include <SPI.h>
// библиотека для работы со сборкой силовых ключей
#include <AmperkaFET.h>
// пин выбора устройства на шине SPI
#define PIN_CS  2

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
    // ...определяем, должен ли он быть включён. Для этого
    // считываем бит (англ. read bit), соответствующий текущему
    // сегменту «i». Истина — он установлен (1), ложь — нет (0)
    boolean enableSegment = bitRead(mask, i);
    // включаем/выключаем сегмент на основе полученного значения
    mosfet.digitalWrite(i, enableSegment);
  }
}
```
Если всё сделано верно, заветные цифры начнут загораться на индикаторе.

![singleDigit.gif](https://habrastorage.org/webt/9u/uz/pm/9uuzpm8jotcnbrcrtp0bqqgbnvq.gif)

Теперь можно соединить оставшиеся три индикатора в одну цепочку, добавить [модуль часов реального времени](https://amperka.ru/product/troyka-rtc?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) и разделительный сегмент в виде точки.

![fullSchem.png](https://habrastorage.org/webt/n_/5x/dz/n_5xdz_tigg0fvdfu3z5g3rlcga.png)

### Исходный код

Осталось научить получившийся четырёхразрядный индикатор показывать текущее время. 

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
    // ...определяем, должен ли он быть включён. Для этого
    // считываем бит (англ. read bit), соответствующий текущему
    // сегменту «i». Истина — он установлен (1), ложь — нет (0)
    boolean enableSegment = bitRead(mask, i);
    // включаем/выключаем сегмент на основе полученного значения
    mosfet.digitalWrite(module, i, enableSegment);
  }
}
```

> Чтобы после прошивки и включения часов время считывалось с модуля RTC,
> закомментируйте оба метода `clock.set()` и загрузите код снова;

То, что получилось, мне очень нравится. Зацените сами!

![i-did-it.jpg](https://habrastorage.org/webt/e7/tg/xi/e7tgxip1b7ndrzo5ccseo7dcllm.jpeg)

Добавлю сюда [кнопку](https://amperka.ru/product/troyka-button?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) или даже [ИК-приемник](https://amperka.ru/product/troyka-ir-receiver?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), чтобы дистанционно включать и выключать свет обычным пультом от телека или кондиционера. И будет вообще огонь!

Это лишь пример того, как поступил я. Вы можете сделать девайс по-своему. Добавьте сюда, что угодно! [Модуль Bluetooth](https://amperka.ru/product/troyka-ble?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content) для настройки и управления, или звуковое оповещение [зуммером](https://amperka.ru/product/troyka-buzzer?utm_source=habr.ru&utm_campaign=post-2020-06-02-paper8&utm_medium=content), чтобы превратить часы в будильник. А лучше и то, и другое.

На этом у меня всё!

Пока!
