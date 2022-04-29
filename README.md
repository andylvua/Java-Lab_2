[![Java CI with Maven](https://github.com/andylvua/JavaLabs/actions/workflows/maven.yml/badge.svg)](https://github.com/andylvua/JavaLabs/actions/workflows/maven.yml)
# Лабораторна робота 2
## Опис завдання
1. Реалізувати ієрархію класів до завдання з лабораторної №2 (секція Зимова школа)
2. При записі програми потрібно використовувати домовленості щодо оформлення коду java code convention.
3. Класи потрібно грамотно розкласти по пакетах.
4. Робота з консоллю або консольне меню повинні бути мінімальними.
5. Важливо: необхідно реалізувати лише ієрархію класів, код пошуку елементів у списках чи колекціях не входить у 2-гу роботу
6. Також слід створити обʼєкти реалізованих вами класів у окремому класі Main, який міститиме main метод
7. Слід додати своє прізвище в таблицю до завдання 2 коло обраного варіанту (обирати слід самостійно)
8. Якщо вільних варіантів в документі більше не буде - слід написати викладачу та отримати варіант від нього

# Лабораторна робота 3
## Опис завдання
1. Необхідно створити клас - Менеджер, що міститиме логіку (приклад для варіанту 1):
> Реалізувати пошук товарів, котрі можна купити для дівчинки в осінній період та реалізувати можливість сортування знайдених товарів:
> - за ціною
> - за розмірами
> <!-- end -->
> <br/>
> Реалізація сортування має передбачати можливість сортувати як за спаданням, так і за зростанням.



2. Для сортування слід використати вбудовані методи сортування, доступні в мові Java
3. Сортування слід реалізувати в окремому методі
4. Код немає містити статичних методів/атрибутів. Дозволено лише один статичний метод - void
5. Код має використовувати перелічувальний тип (Enum) (за потреби)

# Лабораторна робота 4
## Опис завдання
Перетворити проєкт з кодом 2-3 роботи таким чином, щоб його збірку можна було виконувати з-за допомоги maven.

При цьому варто зробити команду merge попередніх робіт в master

**Важливо**: збірку проєкту слід виконувати з консолі командою mvn clean package

Згенерувати pom.xml можна з використанням команди maven (слід виконувати з консолі):
``` java
mvn archetype:generate 
-DgroupId=ua.lviv.iot 
-DartifactId=work 
-Dversion=1.0-SNAPSHOT 
-DarchetypeArtifactId=maven-archetype-quickstart 
-DarchetypeVersion=1.0 
-DinteractiveMode=false
```

# Питання на захист
* this keyword
* super keyword
* final keyword
* Блоки ініціалізації
* enum - why they are used? how they differ from final static fields?
* Interface vs Abstract class
* Inheritance in Java: extends, implements keywords
* Make class abstract
* Make method abstract in Java
* Create interface in Java
* how to make variable to be a constant
* Constructors vs initialization blocks
* What is immutability?
* Explain what is package in Java
* What happens when the main() isn't declared as static?
* What is the difference between JDK, JRE, and JVM?
* Can a constructor return a value?
* Explain Method Overloading in Java. Provide an example based on your code
* Can we overload a static method?
* Why is the delete function faster in the linked list than an array?
* What is pom.xml?
* Explain pom.xml sections
* How to add new dependency in pom.xml?
* How maven dispatches dependencies?

# Лабораторна робота 5
## Опис завдання
В 5 лабораторній роботі слід написати модульні тести для коду лабораторної роботи №4
і досягти рівня покриття тестами 80%.

Очевидно, що ідеалом є покриття на рівні 100% (тобто кожна лінія коду покрита тестами). </br>
Також очевидно, що написання тестів потребує значну кількість часу, якого завжди бракує. <br>
Одним з варіантів уникнення цієї проблеми є підхід TDD.

Для даної лабораторної компромісним значенням буде покриття тестами на рівні 80%

# Лабораторна робота 6
## Опис завдання
Дана робота присвячена роботі з файлами й операції запису, і також базується на основі
лабораторних 3, 5-6. Для реалізованої ієрархії класів в 3-й лабораторній слід реалізувати
запис списку обʼєктів, які присутні в менеджері, в CSV-файл. Звертаю увагу, що код слід
реалізувати лише після здачі 3, 5-6 лабораторних (здаються окремо, при спробі здачі
всіх робіт одночасно студент отримає доповнення до його задачі 3).

Нехай в рамках лабораторної 3 було реалізовано клас CrocodileManager,
який містить список обʼєктів, похідних від класу Crocodile. Для кожного класу,
похідного від Crocodile і в самому класі Crocodile слід реалізувати два методи:

``` java
pubic String getHeaders() { ... }
```
> Повертає стрічку з атрибутів, присутніх в даному класі, розділеному через кому
``` java
pubic String toCSV() { ... }
```
> Повертає значення атрибутів (значення полів), даного об'єкта, розділеного комами

Реалізація методу toCSV в дочірніх класах має викликати також цей метод із батьківського класу.
Поля, які оголошені в батьківському класі, мають конвертуватись в стрічку, розділену комами,
в батьківському класі, наприклад:

``` java
class Crocodile {
private String origin;
    pubic String getHeaders() { 
         return “origin”;
    }
}

class Alligator extends Crocodile  {
private int maxSpeed;
    pubic String getHeaders() { 
         return super.getHeaders() + “,” + “maxSpeed”;
    }
}
```

Для реалізації запису у файл слід реалізувати окремий клас ```Writer```
(наприклад - CrocodileWriter), який міститиме метод
```public void writeToFile(List<Crocodile> crocodiles)```.
Виклик даного методі слід реалізувати з тестів.

Код має відповідати **code convention**.

Також, в **pom.xml** слід додати плагіни ```checkstyle``` і ```spotbugs``` та перевірити код цими аналізаторами
Також слід виправити всі помилки, які будуть знайдені spotbugs та зменшити кількість помилок, на які вкаже checkstyle

Для перевірки якості коду слід виконати команду ```mvn clean site```
