# Угадай число

Проект содержит 2 реализации игры "Угадай число" с разными способами взаимодействия между процессами.

## Сборка
```bash
mkdir build
cd build
cmake ..
make 
```

## Запуск программ
Версия с сигналами (задание 1):
```bash
./prk5_1 <максимальное_число> 
```

Версия с каналами FIFO (задание 2):
```bash
./prk5_2 <максимальное_число> 
```

Где <максимальное_число> - верхняя граница диапазона чисел.


##Описание программ
###1. Версия с сигналами
Использует сигналы реального времени (SIGRTMIN) для передачи чисел;
SIGUSR1/SIGUSR2 для подтверждения/отклонения догадки;
10 раундов с переменой ролей процессов.

###2. Версия с именованными каналами
Использует два FIFO-канала для двусторонней связи;
Структура сообщений содержит число, флаг угадывания и флаг завершения;
Автоматическая очистка каналов при завершении.
