---
title: Threads
localeTitle: Потоки
---
## Потоки

Последовательность программных инструкций, предоставляемых операционной системе для выполнения. Это самая маленькая синхронная последовательность, которая может быть выполнена. Будучи синхронными, инструкции в потоке являются линейными и выполняются один за другим. Если программа имеет несколько потоков, программа в целом может быть асинхронной, поскольку эти потоки выполняют свои собственные инструкции независимо друг от друга (одновременно).

Поток - это абстракция, которую используют операционные системы для представления CPU в программы. В машинных кодах или языках ассемблера нет реальной концепции потоков.

Темы - это способ программирования для одновременного выполнения нескольких задач.

Общим отличием является различие между потоками и процессами. Нить - это ребенок процесса, так сказать.  
В рамках процесса может быть любое количество дочерних потоков. Потоки могут увеличить скорость выполнения программы, увеличив процентное соотношение CPU, используемого для задачи.  
Обратите внимание, что резкое увеличение количества потоков в программе может быть очень интенсивным, и если используется 100% процессора, потоки не будут влиять на скорость выполнения.

![Потоки внутри графа процесса](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Multithreaded_process.svg/440px-Multithreaded_process.svg.png)

Предположим, у вас открыто несколько программ - доля каждой программы в времени процессора представлена ​​одним или несколькими потоками, связанными с этой программой. Когда **планировщик** операционной системы решает, что очередь на запуск программы A, ОС передает (или будет более точным, мультиплексирует) инструкции в потоке Program A в CPU, который затем выполняет эти инструкции.

Поток для определенной программы состоит из некоторых или всех скомпилированных инструкций этой программы, а также некоторой информации, необходимой для выполнения ЦПУ этими инструкциями.

**Многопоточность** - это концепция программирования, в которой программа запускает несколько потоков во время выполнения, чтобы быстрее выполнять задачи.

Вот простой пример многопоточности в python, который печатает числа с 1 по 10, создавая отдельный поток для каждого оператора печати.
```
import threading 
 
 def print_number(number): 
    print(number) 
 
 if __name__ == "__main__": 
    for i in range(1, 11): 
        threading.Thread(target=print_number, args=(i,)).start() 
```

#### Дополнительная информация:

*   [Темы (Википедия)](https://en.wikipedia.org/wiki/Thread_(computing))
*   [Понимание многопоточности](http://www.nakov.com/inetjava/lectures/part-1-sockets/InetJava-1.3-Multithreading.html)