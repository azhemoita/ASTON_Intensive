# Вопросы и ответы:

### 1.	Назовите основные принципы ООП. Расскажите подробно о каждом.
1. **Инкапсуляция**: это процесс, который скрывает внутренние детали реализации объекта и предоставляет доступ к ним только через публичные методы. Это помогает защитить данные от случайного изменения и облегчает поддержку кода.
2. **Наследование**: позволяет создавать новый класс на основе существующего, наследуя его свойства и методы. Это способствует повторному использованию кода и упрощает его расширение.
3. **Полиморфизм**: это способность объектов разных классов обрабатывать одно и то же сообщение по-разному. Реализуется через переопределение методов и интерфейсы, позволяя использовать один интерфейс для разных типов данных.
4. **Абстракция**: это процесс выделения значимых характеристик объекта, игнорируя несущественные детали. В ООП это достигается с помощью абстрактных классов и интерфейсов.
### 2.	Расскажите про иерархию наследования. Подробно про методы класса Object.
Наследование в Java реализуется через **иерархию классов**:
<br/>Каждый класс в Java наследует от **класса Object**, который является корнем иерархии. Класс Object — вершина иерархии наследования. Все классы в Java неявно наследуются от Object. Обеспечивает базовые методы, такие как equals(), hashCode(), toString() и другие.
<br/>**Пользовательские классы** могут наследоваться от других классов, используя ключевое слово extends. Если класс не указывает явного родителя, он наследует от Object.
<br/>**Подклассы и суперклассы**. Класс, который наследует от другого класса, называется подклассом (или производным классом). Класс, от которого наследуют, называется суперклассом (или базовым классом).
<br/><br/>**Методы класса Object** включают:
1. **equals()**: сравнивает объекты на равенство. По умолчанию проверяет, ссылаются ли оба объекта на один и тот же экземпляр. Обычно переопределяется для сравнения содержимого объектов.
2. **hashCode()**: возвращает хэш-код объекта, который используется в коллекциях, таких как HashMap и HashSet. Если equals переопределен, то hashCode также должен быть переопределен, чтобы обеспечивать согласованность.
3. **toString()**: возвращает строковое представление объекта. По умолчанию возвращает строку, содержащую имя класса и хэш-код объекта. Обычно переопределяется для предоставления более информативного представления.
4. **getClass()**: возвращает объект Class, который представляет класс, к которому принадлежит данный объект. Этот метод может быть использован для получения информации о типе объекта во время выполнения.
5. **clone()**: создает копию объекта. Для использования этого метода класс должен реализовать интерфейс Cloneable, и метод clone() должен быть переопределен, чтобы обеспечить глубокое копирование (если необходимо).
6. **finalize()**: вызывается сборщиком мусора перед удалением объекта. Этот метод может использоваться для освобождения ресурсов. Однако его использование не рекомендуется, так как поведение сборщика мусора непредсказуемо.
7. **wait()**: приостанавливает выполнение текущего потока до тех пор, пока не будет вызван метод notify() или notifyAll() в том же объекте. Используется для межпоточного взаимодействия.
8. **notify()**: пробуждает один из потоков, которые ожидают на этом объекте (вызван метод wait()).
9. **notifyAll()**: пробуждает все потоки, которые ожидают на этом объекте.
### 3.	Что такое интерфейс, что такое абстрактный класс.
<br/>**Интерфейс**: это контракт, который определяет набор методов, которые класс должен реализовать. Интерфейсы не могут содержать реализации методов (до Java 8, после чего появились дефолтные методы).
<br/>**Абстрактный класс**: это класс, который не может быть инстанцирован и может содержать как абстрактные методы (без реализации), так и методы с реализацией. Он используется для создания базового класса с общими свойствами и поведением.
### 4.	Может ли интерфейс/абстрактный класс иметь конструктор, поля, статические/дефолтные методы.
Интерфейсы не могут иметь конструкторы и поля (только статические финальные переменные), но могут иметь статические и дефолтные методы.
Абстрактные классы могут иметь конструкторы, поля и статические методы.
### 5.	Что такое Enum, в чем отличие его от класса, может ли иметь методы, конструкторы, наследоваться и реализовывать интерфейсы.
Enum: это специальный класс для определения наборов констант. В отличие от обычных классов, enum не может наследоваться, но может реализовывать интерфейсы.
Enum может иметь методы и конструкторы, которые используются для инициализации значений.
### 6.	Расскажите про модификаторы доступа, к чему они применяются.
Модификаторы доступа определяют уровень доступа к классам и их членам:
<br/>**public**: доступен из любого места.
<br/>**protected**: доступен в пределах пакета и в подклассах.
<br/>**private**: доступен только внутри самого класса.
<br/>Указание без модификатора (**package-private**): доступен только в пределах одного пакета.
### 7.	Расскажите про конструкторы, с какими модификаторами они применяются, могут ли они наследоваться/переопределяться?
**Конструкторы** — это специальные методы, которые вызываются при создании объекта. Они могут быть: public, protected, private.
Конструкторы не наследуются, но могут быть переопределены в подклассах.
### 8.	Можно ли в классе заимплементировать 2 интерфейса? А если в них один и тот же метод doSmth? Как он реализуется?
Да, в классе можно заимплементировать два и более интерфейсов в языке программирования Java (и во многих других языках, поддерживающих интерфейсы). Если два интерфейса содержат метод с одинаковой сигнатурой (например, doSmth()), это не вызывает проблем. Класс, реализующий эти интерфейсы, обязан предоставить одну реализацию данного метода. Если в двух интерфейсах объявлен метод с одинаковым именем и сигнатурой (например, void doSmth();), то при реализации этих интерфейсов в классе достаточно реализовать этот метод один раз. Эта реализация будет использоваться для обоих интерфейсов. В данном примере метод doSmth из обоих интерфейсов разрешается в одну реализацию в классе MyClass. Это возможно, поскольку интерфейсы содержат только объявление метода, без реализации, и конфликтов не возникает.
А что если методы имеют разные дефолтные реализации (Java 8+)? С Java 8 интерфейсы могут содержать default-реализации методов. Если два интерфейса, которые класс реализует, имеют одинаковый метод с разными default-реализациями, возникает конфликт. В этом случае класс обязан переопределить метод и явно указать, как он должен работать. Если вы хотите использовать default-реализацию из одного из интерфейсов, это можно сделать с помощью ключевого слова super (InterfaceA.super.doSmth();).<br/>
**Вывод**: если оба интерфейса содержат метод с одинаковой сигнатурой, класс реализует его один раз, и эта реализация используется для обоих интерфейсов.
Если в интерфейсах есть разные default-реализации метода, класс обязан переопределить метод, чтобы устранить конфликт.
### 9.	Статический/динамический полиморфизм.
**Статический полиморфизм**: Реализуется через перегрузку методов на этапе компиляции (полиморфизм времени компиляции).<br/>
**Динамический полиморфизм** (с помощью абстракций): Реализуется через переопределение методов на этапе выполнения (полиморфизм времени выполнения ).
### 10.	Что является членами класса?
Членами класса являются поля (переменные экземпляра) и методы (функции), а также конструкторы и внутренние классы.
### 11.	Расскажите подробно как переопределяются/перегружаются методы классов наследников.
**Переопределение**: Изменяет реализацию метода в подклассе. Открывает возможность для динамического полиморфизма.<br/>
**Перегрузка**: Создает несколько методов с одинаковым именем, но с разными параметрами в одном классе.
### 12.	JVM, JRE, JDK.
**JVM (Java Virtual Machine)**: Исполняет Java-программы, управляет памятью и обеспечивает взаимодействие с операционной системой.<br/>
**JRE (Java Runtime Environment)**: Содержит JVM и стандартные библиотеки Java.<br/>
**JDK (Java Development Kit)**: Полный набор инструментов для разработки, включая JRE, компилятор и библиотеки.
### 13.	Расскажите что такое Classpath Java, общее правило именования пакетов java.
**Classpath**: Это параметр, указывающий, где Java ищет классы и ресурсы. Обычно включает директории и JAR-файлы.
**Именование пакетов**: Рекомендуется использовать доменное имя в обратном порядке, например, com.example.myapp.
### 14.	Расскажите про интерфейсы Comparator, Comparable и их применение.
**Comparable**: Позволяет объектам сравнивать себя с другими объектами одного типа. Используется для сортировки.
<br/>1) Определяет естественный порядок сортировки объектов.
<br/>2) Используется метод compareTo(), который сравнивает текущий объект (this) с другим объектом.
<br/>3) Класс, реализующий Comparable, обязан указать, как его объекты сравниваются друг с другом.
<br/>**Возвращает:** 0, если объекты равны; отрицательное число, если текущий объект "меньше" другого; положительное число, если текущий объект "больше" другого.
<br/>**Comparator**: Позволяет определять порядок сравнения между различными объектами. Может быть использован для кастомной сортировки.
<br/>1) Не требует изменения класса, объекты которого нужно сравнивать.
<br/>2) Используется метод compare(), который принимает два объекта и сравнивает их.
<br/>3) Можно создать несколько реализаций Comparator для разных критериев сортировки.
<br/>**Возвращает:** 0, если объекты равны; отрицательное число, если текущий объект "меньше" другого; положительное число, если текущий объект "больше" другого.
### 15.	Расскажите про класс String, пул строк.
**String**: Это неизменяемый класс для работы со строками.<br/>
**Пул строк**: Это область памяти, где хранятся строковые литералы. При создании строки, если такая строка уже существует в пуле, возвращается ссылка на существующий объект.
### 16.	Расскажите про варианты использования зарезервированных слов, таких как super, this, class, instance of.
<br/>**super**: Используется для доступа к родительским членам класса.
<br/>**this**: Ссылается на текущий объект.
<br/>**class**: Объявляет новый класс.
<br/>**instance of**: Проверяет, является ли объект экземпляром определенного класса или интерфейса.
### 17.	Java массивы, к какому типу относится, какие есть особенности, можно ли создать 0 длинны, могут ли расширяться.
Массивы являются объектами и имеют фиксированный размер после создания. Можно создать массив длиной 0.
Массивы не могут расширяться после создания.
### 18.	Назовите этапы создания/запуска блоков/конструкторов класса при наследовании.
При наследовании сначала выполняются статические блоки и инициализаторы родительского класса, затем конструкторы родительского класса, и только потом — дочернего.
### 19.	Расскажите какое будет поведение, если внутри цикла вызвать оператор break/continue?
<br/>**break**: Прерывает выполнение цикла и выходит из него.
<br/>**continue**: Пропускает текущую итерацию и переходит к следующей.
### 20.	Что такое Generics?
**Generics в Java** — это механизм обобщённого программирования, который позволяет создавать классы, интерфейсы и методы с параметризованным типом. Они обеспечивают:
<br/>1) **Безопасность типов**: предотвращают ошибки времени выполнения, связанные с преобразованием типов.
<br/>2) **Переиспользование кода**: один обобщённый класс/метод для разных типов данных.<br/>
Generics используют механизм **type erasure** (стирание типов) во время компиляции. Это означает, что информация о параметризованном типе удаляется, и в байт-коде используется базовый тип (Object или указанный ограничивающий тип).
### 21.	Расскажите про такое зарезервированное слово, как final, к чему оно применяется и как используется?
Ключевое слово final используется для создания неизменяемых сущностей. Оно применяется к:
<br/>1) **Классам**: Если класс объявлен как final, его нельзя наследовать.
<br/>2) **Методам**: Если метод объявлен как final, его нельзя переопределить в подклассе.
<br/>3) **Переменным**: Для примитивов: значение переменной нельзя изменить. Для ссылочных типов: нельзя изменить ссылку, но объект, на который она указывает, может быть изменён.
<br/>4) **Параметрам метода**: Параметры метода, объявленные как final, нельзя изменить внутри метода.
### 22.	Расскажите про Optional.
Optional — это специальный класс в Java, введённый в Java 8, который помогает избежать ошибок, связанных с использованием null. Это контейнер, который может содержать одно значение или быть пустым.
<br/>**Основные методы Optional:**
<br/> 1) Создание:
<br/>Optional.of(value) — создаёт Optional с непустым значением (если значение null, выбрасывается NullPointerException).
<br/>Optional.ofNullable(value) — создаёт Optional, который может быть пустым.
<br/>Optional.empty() — создаёт пустой Optional.
<br/>2) Проверка:
<br/>isPresent() — возвращает true, если значение присутствует.
<br/>ifPresent(Consumer) — выполняет действие, если значение присутствует.
<br/>3) Получение значения:
<br/>get() — возвращает значение (или выбрасывает исключение, если пусто).
<br/>orElse(value) — возвращает значение или заданное значение по умолчанию.
<br/>orElseGet(Supplier) — возвращает значение или вычисляет его через лямбда-выражение.
<br/>orElseThrow(Supplier) — выбрасывает исключение, если значение отсутствует.
### 23.	Что описывает и показывает Big O нотация? Как высчитывается, что фактически измеряется (привести примеры)?
Big O нотация — это способ выражения сложности алгоритма в зависимости от объёма данных (временной или пространственной). Она показывает, как изменяется время выполнения или потребление памяти при увеличении входных данных.
<br/>**Основные виды сложности:**
<br/>**O(1)** — Константная (не зависит от размера данных). Пример: доступ к элементу массива по индексу.
<br/>**O(log n)** — Логарифмическая. Пример: бинарный поиск.
<br/>**O(n)** — Линейная. Пример: одно прохождение массива.
<br/>**O(n log n)** — Логарифмически-линейная. Пример: быстрая сортировка.
<br/>**O(n²)** — Квадратичная. Пример: вложенные циклы.
<br/>**O(2ⁿ)** — Экспоненциальная. Пример: перебор всех возможных комбинаций.
### 24.	Основные алгоритмы сортировки (знать/понимать принцип работы).
<br/>**Пузырьковая сортировка (Bubble Sort)**: Сравнивает соседние элементы и меняет их местами. Сложность: O(n²). Память: O(1) (внутренняя сортировка).
<br/>**Сортировка выбором (Selection Sort)**: Находит минимальный элемент и помещает его на место. Сложность: O(n²). Память: O(1).
<br/>**Сортировка вставками (Insertion Sort)**: Вставляет элемент на своё место в отсортированной части массива. Сложность: O(n²). Память: O(1).
<br/>**Быстрая сортировка (Quick Sort)**: Выбирает опорный элемент (pivot) и делит массив на две части. Сложность: O(n log n) в среднем, O(n²) в худшем случае. Память: O(log n) (рекурсия).
<br/>**Сортировка слиянием (Merge Sort)**: Делит массив на части, сортирует их и сливает. Сложность: O(n log n). Память: O(n) (внешняя сортировка).
### 25.	Пузырьковая сортировка (сложность, память).
<br/>**Принцип работы**: сравнивает соседние элементы и меняет их местами, если они в неправильном порядке.
<br/>**Сложность**: Лучший случай: O(n) (массив уже отсортирован). Худший случай: O(n²).
<br/>**Память**: O(1) (не требует дополнительной памяти).
### 26.	Сортировка выбором (сложность, память).
<br/>**Принцип работы**: находит минимальный элемент в неотсортированной части массива и ставит его в начало.
<br/>**Сложность**: O(n²) (независимо от порядка элементов).
<br/>**Память**: O(1).
### 27.	Сортировка вставками (сложность, память).
<br/>**Принцип работы**: вставляет элементы на своё место в отсортированной части массива.
<br/>**Сложность**: Лучший случай: O(n). Худший случай: O(n²).
<br/>**Память**: O(1).
### 28.	Быстрая сортировка (сложность, память).
<br/>**Принцип работы**: выбирает опорный элемент, разделяет массив и рекурсивно сортирует части.
<br/>**Сложность**: Средний случай: O(n log n). Худший случай: O(n²).
<br/>**Память**: O(log n) (рекурсивная глубина).
### 29.	Сортировка слиянием (сложность, память).
<br/>**Принцип работы**: делит массив на части, сортирует их рекурсивно и сливает.
<br/>**Сложность**: O(n log n).
<br/>**Память**: O(n).
### 30.	Жадный алгоритм.
**Жадный алгоритм** — это стратегия принятия решений, где на каждом шаге выбирается локально оптимальное решение с надеждой, что оно приведет к глобально оптимальному результату. Жадные алгоритмы не всегда гарантируют оптимальное решение, но часто работают быстро и применимы для ряда задач.
<br/>**Примеры задач, решаемых жадным алгоритмом:**
<br/>Задача о размене монет (если номиналы монет составляют жадную систему, например, 1, 5, 10, 25).
<br/>Задача о покрытии отрезков минимальным числом точек.
<br/>Задача о рюкзаке (дробный рюкзак, а не целочисленный).
<br/>**Важные особенности:** Жадные алгоритмы работают эффективно, если задача удовлетворяет свойствам оптимальности подструктуры и жадного выбора. Если задача не удовлетворяет этим свойствам, жадный алгоритм может дать не оптимальное решение.
### 31.	Бинарный поиск.
Бинарный поиск используется для поиска элемента в отсортированном массиве. Принцип работы основан на делении массива на две части и исключении той, в которой элемент не может находиться.
<br/>**Алгоритм работы:** Проверить средний элемент массива: если он равен искомому, поиск завершён; если меньше искомого, продолжить поиск в правой половине; если больше искомого, продолжить поиск в левой половине. Повторять процесс до нахождения элемента или до того, как массив станет пустым.
<br/>**Сложность:** Временная: O(log n). Пространственная: O(1).
### 32.	Алгоритмы поиска пути: обход в глубину, обход в ширину.
<br/>**Обход в глубину (DFS - Depth First Search)**: Исследует граф (или дерево), начиная с корневой вершины, углубляясь как можно дальше вдоль каждого пути, прежде чем возвращаться назад. Реализуется с использованием рекурсии или стека.
<br/>**Обход в ширину (BFS - Breadth First Search)**: Исследует вершины графа уровня за уровнем. Реализуется с использованием очереди.<br/>
![image](https://github.com/user-attachments/assets/6dda44c6-1110-4252-a1a2-6fadbd99dcc7)
### 33.	Какие структуры данных вы знаете?
<br/>1) **Линейные структуры данных**: Массивы. Связанные списки (однонаправленные, двунаправленные). Стек. Очередь (обычная очередь, двусторонняя очередь, приоритетная очередь).
<br/>2) **Деревья**: Бинарное дерево. Двоичное дерево поиска (BST). AVL-дерево. Красно-чёрное дерево. B-дерево.
<br/>3) **Графы**: Ориентированные/неориентированные графы. Взвешенные графы.
<br/>4) **Хэш-таблицы (HashTable, HashMap).**
<br/>5) **Множества (Set)**: HashSet. TreeSet.
<br/>6) **Другие**: Дека (Deque). Trie (префиксное дерево).
### 34.	Массивы: достоинства и недостатки.
**Достоинства**: Быстрый доступ к элементу по индексу (O(1)). Простота реализации.
<br/>**Недостатки**: Фиксированный размер. Высокая стоимость операций вставки/удаления (O(n) в худшем случае).
### 35.	Связанные списки: достоинства и недостатки, временная сложность добавления/поиска/удаления элемента.
**Достоинства**: Динамический размер. Быстрая вставка/удаление (O(1), если известна позиция).
<br/>**Недостатки**: Медленный поиск (O(n)). Дополнительная память на хранение указателей.
<br/>**Сложности**: 
<br/>1) **Добавление**: O(1) (если в начало/конец).
<br/>2) **Поиск**: O(n).
<br/>3) **Удаление**: O(1) (если известен узел).
### 36.	Стек: достоинства, недостатки, временная сложность добавления/поиска/удаления элемента.
**Стек (Stack)** — структура данных, работающая по принципу LIFO (последний вошел — первый вышел).
<br/>**Достоинства:** Простота реализации. Используется для рекурсии, алгоритмов поиска, обработки выражений (например, обратная польская нотация).
<br/>**Недостатки:** Ограничение по доступу к элементам (можно работать только с вершиной). Неэффективен для хранения больших объемов данных.
<br/>**Временная сложность:** Добавление: O(1) (операция push). Поиск: O(n) (если требуется доступ к элементу, который не на вершине). Удаление: O(1) (операция pop).
### 37.	Очередь: достоинства, недостатки, временная сложность добавления/поиска/удаления элемента.
**Очередь (Queue)** — структура данных, работающая по принципу FIFO (первый вошел — первый вышел).
<br/>**Достоинства:** Хорошо подходит для задач планирования, обработки потоков данных. Простота реализации.
<br/>**Недостатки:** Ограничение доступа (работа только с началом и концом очереди). Для эффективной реализации требуется кольцевая очередь или список.
<br/>**Временная сложность:** Добавление: O(1). Поиск: O(n) (если требуется доступ к произвольному элементу). Удаление: O(1).
### 38.	Деревья: достоинства, недостатки, временная сложность, добавления/поиска/удаления элемента.
**Дерево** — иерархическая структура данных, состоящая из узлов. Каждый узел имеет родителя (кроме корня) и может иметь несколько потомков.
<br/>**Достоинства:** Быстрый поиск, вставка и удаление (в сбалансированных деревьях). Представление иерархических данных (файловая система, дерево решений).
<br/>**Недостатки:** Требует больше памяти (для указателей на дочерние узлы). Неэффективен в несбалансированном состоянии (например, в случае линейного дерева).
<br/>**Временная сложность (для сбалансированного дерева)**: Добавление: O(log n). Поиск: O(log n). Удаление: O(log n).
### 39.	На какие основные группы можно поделить типы данных?
**1) Примитивные типы данных (Primitive types):** byte, short, int, long, float, double, char, boolean.
<br/>**2) Ссылочные типы данных (Reference types):** классы, интерфейсы, массивы, перечисления (Enum).
### 40.	Какие примитивные типы вы знаете?
**1) Целочисленные типы:** byte (1 байт), short (2 байта), int (4 байта), long (8 байт).
<br/>**2) С плавающей точкой:** float (4 байта), double (8 байт).
<br/>**3) Символьный:** char (2 байта, Unicode).
<br/>**4) Логический:** boolean (1 бит, значения true/false).
### 41.	Что вы знаете о преобразовании примитивных типов данных (есть ли потеря данных, можно ли преобразовать логический тип)?
1) **Неявное (widening):** Меньший тип преобразуется в больший (например, int → long). int a = 10; long b = a; // Неявное преобразование
<br/>2) **Явное (narrowing):** Больший тип преобразуется в меньший (может быть потеря данных). double d = 10.5; int a = (int) d; // Округление, результат: 10
<br/>**Потеря данных:** При преобразовании большего типа в меньший (например, long → int) или при округлении дробных чисел (double → int).
<br/>Логический тип (boolean) нельзя преобразовать в числовой и наоборот.
### 42.	Какими значениями инициализируются переменные по умолчанию?
**Примитивы:** byte, short, int, long → 0. float, double → 0.0. char → \u0000 (нулевой символ Unicode). boolean → false.
<br/>**Ссылочные типы:** null.
### 43.	Как передается значение переменной (по ссылке/значению)?
В Java все данные передаются по значению: для примитивных типов передаётся значение, а для ссылочных типов передаётся копия ссылки, но не сам объект.
### 44.	Что вы знаете про классы-обёртки?
**Классы-обёртки (Wrapper classes)** используются для представления примитивных типов как объектов. Примеры: Integer, Double, Boolean, Character и т. д.
<br/>**Особенности:** Поддерживают методы для работы с примитивами. Используются в Generics (т. к. Generics работают только с объектами). Автоматическое преобразование (autoboxing/unboxing): Integer a = 10; // autoboxing; int b = a; // unboxing
### 45.	Определение коллекции.
**Коллекция (Collection)** — это структура данных для хранения группы объектов (элементов). В Java коллекции представлены через интерфейсы и их реализации в java.util.
### 46.	Преимущества использования коллекций.
1) Динамическое управление размером (в отличие от массивов).
<br/>2) Универсальный доступ к элементам.
<br/>3) Удобные методы для сортировки, поиска, фильтрации.
<br/>4) Богатая иерархия классов и интерфейсов.
### 47.	Какие объекты можно хранить в коллекциях?
Можно хранить любой объект (включая пользовательские классы). Примитивы хранятся через обёртки (Integer, Double и т. д.).
### 48.	Иерархия коллекций.
Иерархия коллекций в Java представлена интерфейсами и классами в пакете java.util. Она организована в виде структуры, где базовым интерфейсом является Collection, а также отдельным корнем для ассоциативных коллекций выступает интерфейс Map (он не является частью Collection).
<br/>**Основные интерфейсы:**
<br/>1) **Коллекции (Collection):**
<br/>List (упорядоченные коллекции с возможностью дублирования элементов): ArrayList, LinkedList.
<br/>Set (коллекция, которая не допускает дублирования элементов (уникальные элементы)): HashSet, LinkedHashSet, TreeSet (по умолчанию – естественный порядок или с использованием Comparator).
<br/>Queue (очередь — коллекция, работающая по принципу "первый вошел – первый вышел" (FIFO)): LinkedList (реализует Queue), PriorityQueue.
<br/>Deque (двунаправленная очередь с возможностью добавления/удаления элементов на обоих концах): ArrayDeque, LinkedList (также реализует Deque).
<br/>2) **Ассоциативные коллекции (Map) (пары "ключ-значение": ключи уникальны, значения могут повторяться)**: HashMap, LinkedHashMap, ConcurrentHashMap, TreeMap.
### 49.	Отличия Vector от ArrayList.
**Vector**: Устаревший, синхронизирован. Медленнее из-за синхронизации.
<br/>**ArrayList**: Не синхронизирован. Быстрее при работе в одном потоке.
### 50.	Что знаете о коллекциях типа List (как добавляется элемент\расширяется коллекция)?
List: упорядоченная коллекция, допускает дубликаты. Интерфейс List является частью пакета java.util и поддерживает работу с элементами по индексам, что делает его похожим на массив, но с динамическим управлением размером. При добавлении элементов размер коллекции изменяется автоматически.
<br/>**Основные реализации List:**
<br/>1) ArrayList (массив, который имеет фиксированный размер). При добавлении элемента: Если есть свободное место в массиве, элемент добавляется в конец. Если массив заполнен, создается новый массив большего размера (по умолчанию увеличивается на 50%) и все элементы копируются в новый массив. Элемент добавляется в новый массив. Динамически расширяется, если массив переполнен. По умолчанию начальная емкость ArrayList равна 10 (если вы не укажете другую емкость). При переполнении емкость увеличивается примерно на 50% (проверяется, есть ли свободное место в массиве. Если места нет, создается новый массив размером oldCapacity * 1.5. Элементы копируются из старого массива в новый). Используйте, если требуется быстрый доступ по индексу. Подходит для часто читаемых данных с редкими операциями вставки/удаления.
<br/>2) LinkedList (двусвязный список). При добавлении элемента: Если добавление происходит в конец, создается новая нода, которая становится последним элементом.
Если добавление происходит в определенный индекс, создается новая нода, ссылки соседних нод обновляются для включения новой ноды. LinkedList не требует выделения массива и не использует фиксированный размер. Он расширяется динамически, добавляя новые ноды при необходимости. Каждая новая нода выделяется в памяти отдельно и не зависит от размера предыдущих. Используйте, если требуется частое добавление/удаление в начале/середине списка. Подходит для данных с большим количеством вставок/удалений.
### 51.	Что знаете о коллекциях типа Set?
Set — это интерфейс коллекций в Java, который представляет множество уникальных элементов (не допускает дубликатов). Он является частью пакета java.util и расширяет интерфейс Collection. Коллекции типа Set используются, когда важна уникальность элементов, а порядок хранения элементов может быть не важен (в зависимости от реализации). Допускаются null значения (один null) (в зависимости от реализации). Основные реализации: HashSet (порядок не гарантируется, быстрая): O(1) для операций добавления/удаления. LinkedHashSet: порядок вставки сохраняется, допускаются null значения (один null). TreeSet (отсортированная, элементы упорядочены по естественному порядку (или с использованием компаратора), реализован на основе красно-черного дерева, не позволяет хранить null значения (вызывает NullPointerException)): O(log n).
### 52.	Что знаете о коллекциях типа Queue?
Queue — интерфейс, который наследуется от интерфейса Collection. Очереди предназначены для хранения элементов в порядке их добавления, что обеспечивает доступ к элементам по принципу "первый пришел - первый вышел" (FIFO — First In, First Out).
<br/>**Основные характеристики интерфейса Queue:**
<br/>1) Позволяет добавлять элементы в конец очереди и удалять их с начала.
<br/>2) Может иметь фиксированный или динамический размер.
<br/>3) Может поддерживать разные условия и правила для обработки (например, приоритетные очереди).
<br/>**Основные реализации:** LinkedList (FIFO) (реализует интерфейс Queue и Deque. Хранит элементы в виде двусвязного списка, что позволяет эффективно добавлять и удалять элементы), ArrayDeque (реализует интерфейс Deque и может работать как очередь, хранит элементы в массиве, обеспечивая хорошую производительность по сравнению с LinkedList в большинстве случаев), PriorityQueue (в порядке приоритета) (реализует Queue и хранит элементы в соответствии с их приоритетом. Элементы могут быть упорядочены с помощью естественного порядка или заданного компаратора), BlockingQueue (подинтерфейс Queue, который позволяет использовать очереди в многопоточных средах. Предоставляет методы для безопасного добавления и удаления элементов, блокируя потоки при необходимости. Примеры реализации: ArrayBlockingQueue, LinkedBlockingQueue, PriorityBlockingQueue).
### 53.	Что знаете о коллекциях типа Map и их принципиальное отличие?
Map — представляет собой коллекцию, которая хранит данные в виде пар "ключ-значение". Каждому ключу соответствует одно значение, и ключи должны быть уникальными. Коллекции типа Map являются частью Java Collections Framework и используются для хранения данных, доступ к которым осуществляется по ключу. Принципиальное отличие: Map не является наследником Collection.
<br/>**Основные характеристики интерфейса Map:**
<br/>1) Хранение пар "ключ-значение": каждый элемент в Map состоит из ключа и соответствующего ему значения.
<br/>2) Уникальные ключи: каждый ключ может присутствовать только один раз; если при добавлении нового значения для уже существующего ключа будет использоваться тот же ключ, предыдущее значение будет заменено.
<br/>3) Операции доступа: предоставляет методы для добавления, удаления и получения значений по ключу.
<br/>**Основные реализации Map:**
<br/>1) **HashMap** (использует хеш-таблицу для хранения данных, позволяет быстрый доступ к элементам (в среднем O(1) по времени) по ключу, но не гарантирует порядок элементов (порядок может изменяться)).
<br/>2) **LinkedHashMap** (расширяет HashMap, сохраняя порядок вставки элементов, что позволяет итерацию по элементам в порядке их добавления; позволяет сохранить порядок, но с небольшими потерями в производительности по сравнению с HashMap).
<br/>3) **TreeMap** (реализует интерфейс SortedMap и поддерживает порядок по ключам, используя красно-черную структуру дерева; позволяет доступ к элементам в отсортированном порядке по ключам).
<br/>4) **Hashtable** (подобно HashMap, но является синхронизированной (потокобезопасной) коллекцией; поддерживает только null в качестве значения, но не в качестве ключа.
<br/>**Принципиальное отличие между коллекциями типа Map и другими коллекциями (например, List и Set)**.
<br/>**Структура данных:** List и Set хранят отдельные объекты, тогда как Map хранит пары ключей и значений.
<br/>**Доступ по ключу:** в Map данные можно быстро искать и получать по ключу, в то время как в List и Set — это достигается по индексу или с помощью итератора.
<br/>**Уникальность ключей:** в Map ключи уникальны, хотя значения могут повторяться (в Set все элементы уникальны, а в List могут быть дубликаты).
### 54.	Назовите основные реализации List, Set, Map.
### 55.	Что общего у ArrayList\LinkedList, когда какой лучше использовать?
### 56.	Расскажите про HashSet.
### 57.	Расскажите про TreeSet/как сортируются элементы.
### 58.	Как задается порядок следования объектов в коллекции, как отсортировать коллекцию.
### 59.	Iterator. Как его получить(). Его методы: что и зачем?
### 60.	Iterable - что за зверь? Что за контракт описывает.
### 61.	Коллекция 10 элементов.Вызываю 9x Iterator.hasNext а затем Iterator.next. Что вернется.
### 62.	Как перебрать все ключи значения Map (можно ли через Iterable)?
### 63.	Разница Iterator, Enumerator, ListIterator.
### 64.	В каких случаях может быть выброшено ConcurrentModificationException?
### 65. Что такое Stream API?
### 66. Каковы основные преимущества использования Stream API?
### 67. Какие основные операции доступны в Stream API?
### 68. Как можно объединять несколько Stream с помощью Stream API?
### 69. Как использовать Stream API для обработки ошибок?
### 70. Как использовать методы фильтрации в Stream API, что принимает/возвращает?
### 71. Как применять Collectors.groupingBy() Stream API, что принимает/возвращает?
### 72. Как можно использовать Stream API для преобразования одного типа данных в другой, например, int[] {1,2,3}?
### 73. Отличия flatMap от Map?
### 74. Как работать с параллельными потоками с помощью Stream API?
### 75. Как использовать метод forEach в Stream API? - что принимает/возвращает?
### 76. Как использовать метод peek в Stream API? - что принимает/возвращает?
### 77. Как работает метод reduce в Stream API? - что принимает/возвращает? Варианты и методы.
### 78. Как создать бесконечный поток с помощью Stream API?
### 79. Какие ограничения есть у Stream API?
### 80. Как передать переменную в стрим что с ней можно сделать?
### 81. Как создать Optional?
### 82. Отличие Optional of() от Nullable().
### 83. В чем отличие методов ifPresent и orElse в контексте Optional?
### 84. Каким образом можно объединить два Optional в один, используя метод join?
### 85. Что проверяет ifPresent Optional?
### 86. Каким образом можно преобразовать Stream в массив или коллекцию?
### 87. В чём отличие методов orElseGet и orElse?
### 88. Каким образом можно реализовать обработку ошибок с использованием Optional и метод orElseThrow?
### 89. Какова иерархия исключений?
### 90. Дайте определение понятию “исключение”.
### 91. Какая конструкция используется в Java для обработки исключений?
### 92. Можно/нужно ли обрабатывать ошибки JVM?
### 93. Какие существуют способы обработки исключений?
### 94. О чем говорит ключевое слово throws?
### 95. В чем особенность блока finally? Всегда ли он исполняется?
### 96. Когда блок finally не будет выполнен?
### 97. Может ли не быть ни одного блока catch?
### 98. Что вы знаете об (checked/unchecked) исключениях?
### 99. Может ли один блок catch отлавливать несколько исключений (с одной и разных веток наследований порядок блоков исключений)?
### 100. Особенность RuntimeException.
### 101. Как выбрать свой: checked/unchecked?
### 102. Какой оператор позволяет принудительно выбросить исключение?
### 103. Есть ли дополнительные условия к методу, который потенциально может выбросить исключение?
### 104. Может ли метод main выбросить исключение во вне и если да, то где будет происходить обработка данного исключения?
### 105. Если оператор return содержится и в блоке catch и в finally, какой из них “главнее”?
### 106. Что вы знаете о OutOfMemoryError, SQLException? К какому типу checked или unchecked оно относится, почему?
### 107. Error? В каком случае используется Error (пример Error’а).
### 108. Как хэш SHA-1 используется в Git?
### 109. Каковы основные состояния файла в Git?
### 110. Команды git init, что создается? Как скопировать удаленный репозиторий?
### 111. Что происходит после создания коммита?
### 112. Как добавить комит и зафиксировать его?
### 113. Нужно ли отправлять коммиты на сервер для завершения рабочего процесса Git?
### 114. Что происходит при git fetch?
### 115. Что происходит при git merge?
### 116. Разрешает ли Git конфликты автоматически?
### 117. Возможен ли git pull, если в файле в рабочем каталоге есть незафиксированные изменения?
### 118. Что за команда git cherry-pick (можно ли добавить несколько комитов)?
### 119. Какова цель указателя HEAD?
### 120. В каких случаях возникает конфликт?
### 121. Как изменить историю коммитов (rebase amend)?
### 122. В чем разница между git merge и git rebase? О чем следует помнить при изменении истории веток?
### 123. Как разрешать конфликты?
### 124. Что такое git remote и git clone?
### 125. Что такое detached HEAD?
### 126. Варианты reset?
### 127. Что такое git revert?
### 128. Как снести удаленно ветку, которую запушил?
