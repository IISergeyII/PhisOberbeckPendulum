# OberbeckPendulum

[Старая статья](https://1drv.ms/w/s!Apyu-RQDxqdLl19sx__UMgL3wEDg?e=aZCkaL)

[Новая статья](https://1drv.ms/w/s!Apyu-RQDxqdLl2Fmd754Kf6JyVYe?e=NJWkcE)

[Презентация](https://1drv.ms/p/s!Apyu-RQDxqdLl2OzlQJsOzpYF2NM?e=ZP7QPJ)

[Демонстрация работы (видео)](MainProgramDebo.mp4)

### Ссылки для служебного пользования

[Официальный практикум ИТМО](https://books.ifmo.ru/file/pdf/2181.pdf)

[Условие лабораторной работы](Lab.pdf)

[Обработка экспериментальных данных](DataProcessing.pdf)

### Arduino.c

Данный сценарий прошивает Arduino Uno R3 для получения координаты между двумя ультразвуковыми дальномерами x(t).

Отправьте команду **params** через COM-порт, чтобы получить обзор всех констант.

Для **проведения измерительного эксперимента** необходимо изменить следующие константы в коде:

* dataFrequency (100 * 10^-3 s): частота получения координаты в миллисекундах
* temperature (24 C): температура проведения эксперимента в градусах Цельсия
* betweenSensorAndStart (0 cm): расстояние между начальной координатой и начальным датчиком в сантиметрах
* distanceInOperation (70 cm): длина координатного отрезка в сантиметрах (0 <= x(t) <= distanceInOperation)
* betweenSensorAndFinish (0 cm): расстояние между конечной координатой и конечным датчиком в сантиметрах

Для **подключения датчиков и настройки устройства** необходимо изменить следующие константы в коде:

* sensorStartEcho (2): номер пина Echo начального датчика
* sensorStartTrig (3): номер пина Trig начального датчика
* sensorFinishEcho (4): номер пина Echo конечного датчика
* sensorFinishTrig (5): номер пина Trig конечного датчика
* serialSpeed (57600 bps): скорость обмена данными через COM-порт
* serialTimeout (50 * 10^-3 s): максимальное время получения данных по COM-порту
* pulseInTimeout (50 * 10^-3 s): максимальное время получения времени от датчика

### Emulator.c

Данный сценарий эмулирует лабораторную установку, принимает COM-команду "throw количество_грузов номер_риски" и выводит координату x с тактовой частотой t с новой строки. Комментарии - это строки, начинающиеся с #.
