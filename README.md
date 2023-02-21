# Multiprocessing (Многопроцессность)

### Процесс - выполняющая программа.

Параллелизм подразумевает конкурентность, конкурентность не всегда подразумевает параллелизм. 

### Утилизация - степень использования какого-либо инструмента. (Если имеется 2 ядра CPU, то они утилизированы на 100% - значит ядра постоянно выполняют какую-то работу).

Типы задач:

-CPU-bound (обработка изображение, работа с видео)

-Ввод/вывод (I/O) (браузер: выполнение HTTP/HTTPS запросы)

### Поток - сущность исполнения программ. Потоки живут внутри процесса. Каждый процесс имеет хотя бы один поток.

### Асинхронность - это возможность выполнения программой задач и процессов без ожидания их завершения.

Идея построена на том, что есть некий LOOP (петля, которая позволяет  не ждать ответа на I/O задачах, а переходить к следующей).
При правильном использовании асинхронности будет 100% утилизация ядра.

## Зачем нужна многопроцессность? 

1) Для распараллеливания вычислительных задач (запустить скрипт в нескольких процессах, по ядрам раскидывать процессы и в каждом ядре будет происходить необходимое высчитывание)

2) Системный вызов - обращение прикладной программы к ядру ОС для выполнения какой-либо операции. (Управление процессами в введении ОС, Python лишь обращается к ОС для создания нового процесса).

Системный вызов fork - нужен, чтобы "отпочковать" от одного процесса (родительского) другой (дочерний). Дочерний процесс будет являться практически полной копией родительского. 
