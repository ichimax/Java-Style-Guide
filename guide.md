# Правила оформления кода на языке Java

1. [Правила для классов](#1)
1. [Правила для методов](#2)
1. [Правила для переменных](#3)
1. [Общие правила](#4)

Перед каждой сдачей наставнику на проверку выполненное ДЗ, в обязательном порядке сверяйте форматирование своих классов, с указанными ниже правилами (делайте это до тех пор, пока не запомните их наизусть).

Применение данных техник сделает ваш код чистым, читаемым, понятным. Не пренебрегайте ими! Будьте предельно внимательными.

## <a name="1">Правила для классов<a>

- #### Имя класса должно быть существительным и состоять из одного или более слов. Оно не должно содержать глагол

неправильно:
``` java
class Sit
class SaveInteger
class CalculateSum
```

правильно:
``` java
class SortedArrayStorage
class CalculatorMain
class Resume
```

- #### Не оставляйте пустые строки после объявления класса и перед последней }

неправильно:
``` java
public class Player {

    private String name;

    public String getName() {
        return name;
    }
    // лишняя пустая строка
}
// лишняя пустая строка
```

правильно:
``` java
public class Player {

    private String name;

    public String getName() {
        return name;
    }
}
```

- #### После имени класса и перед { необходим пробел

неправильно:
``` java
public class Calculator{
```

правильно:
``` java
public class Calculator {
```

- #### Поля необходимо размещать в начале класса. При этом все они должны быть сгруппированы в одном месте

неправильно:
``` java
public class Wolf {

    private String sex;

    public String getSex() {
        return sex;
    }

    private String name;

    public String getName() {
        return name;
    }
}
```

правильно:
``` java
public class Wolf {

    private String sex;
    private String name;

    public String getSex() {
        return sex;
    }

    public String getName() {
        return name;
    }
}
```

- #### Межу блоком полей и конструктором необходима пустая строка

неправильно:
``` java
public class Resume {

    private String uuid;
    private String name
    public Resume(String uuid) {
        this.uuid = uuid;
    }
}
```

правильно:
``` java
public class Resume {

    private String uuid;
    private String name

    public Resume(String uuid) {
        this.uuid = uuid;
    }
}
```

- #### Группируйте геттеры и сеттеры по именам переменных, для которых они созданы. При этом не “приклеивайте” их друг к другу

неправильно:
``` java
public class Jaeger {

    private String mark;
    private String origin;

    public String getMark() {
        return mark;
    }
    public String getOrigin() {
        return origin;
    }

    public void setMark(String mark) {
        this.mark = mark;
    }
    public void setOrigin(String origin) {
        this.origin = origin;
    }
}
```
		
правильно:
``` java
public class Jaeger {

    private String mark;
    private String origin;

    public String getMark() {
        return mark;
    }

    public void setMark(String mark) {
        this.mark = mark;
    }

    public String getOrigin() {
        return origin;
    }
    
    public void setOrigin(String origin) {
        this.origin = origin;
    }
}
```

- #### Размещайте конструктор(ы) после всех полей

неправильно:
``` java
class BankAccount {
    private String name;

    String getName() {
        return name;
    }

    public BankAccount(String name) {
        this.name = name;
    }
}
```

правильно:
``` java
class BankAccount {
    private String name;

    public BankAccount(String name) {
        this.name = name;
    }

    String getName() {
        return name;
    }
}
```

- #### Размещайте геттеры и сеттеры в порядке следования полей, к которым они относятся

неправильно:
``` java
class Player {

    private String name;
    private int number;

    int getNumber() {
        return number;
    }

    void setNumber(int number) {
        this.number = number;
    }

    String getName() {
        return name;
    }

    void setName(String name) {
        this.name = name;
    }
}
```

правильно:
``` java
class Player {

    private String name;
    private int number;

    String getName() {
        return name;
    }

    void setName(String name) {
        this.name = name;
    }
    
    int getNumber() {
        return number;
    }

    void setNumber(int number) {
        this.number = number;
    }
}
```

- #### Размещайте конструкторы в классе в порядке, зависящем от принимаемых ими числа аргументов: от меньшего к большему

неправильно:
``` java
class Player {

    Resume(String name, int number) {}

    Resume(String name) {}

    Resume(String name, int number, String uuid) {}
}
```

правильно:
``` java
class Player {

    Resume(String name) {}

    Resume(String name, int number) {}

    Resume(String name, int number, String uuid) {}
}
```

- #### В одной строке объявляйте за раз только одну переменную

неправильно:
``` java
class Person {
    String uuid, name;
    double height, weight;
}
```

правильно:
``` java
class Person {
    String uuid;
    String name;
    double height;
    double weight;
}
```

- #### Между именем конструктора и открывающейся круглой скобкой пробел не требуется

неправильно:
``` java
Player (String name)
Resume (String uuid)
```

правильно:
``` java
Player(String name)
Resume(String uuid)
```

- #### Если геттеры не используются, то в классе их можно не писать

## <a name="2">Правила для методов</a>

- #### Имя метода должно быть глаголом или содержать глагол и состоять из одного или более слов. Первым в имени должен идти глагол

неправильно:
``` java
void endGame()
int calculation()
String playerArray()
```

правильно:
``` java
int calculate()
void clearNumbers()
void start()
```

- #### Начинайте имена методов с маленькой буквы

неправильно:
``` java
char GetLetter()
void ClearEnteredNumbers()
Player CreatePlayer()
```

правильно:
``` java
char getLetter()
void clearEnteredNumbers()
Player createPlayer()
```

- #### Между именем метода и открывающейся круглой скобкой пробел не требуется

неправильно:
``` java
public static void main (String[] args)
public int getIndex (String uuid)
System.out.println ("Math operator is wrong!")
```

правильно:
``` java
public static void main(String[] args)
public int getIndex(String uuid)
System.out.println("Math operator is wrong!")
```

- #### После сигнатуры любого метода пустая строка не ставится

неправильно:
``` java
public static void main(String[] args) {

    int number = 5;
}
```

правильно:
``` java
public static void main(String[] args) {
    int number = 5;
}
```

*я это называю программерской клаустрофобией. Ей страдают по началу все новички. В интернете полно примеров, где пустая строка ставится. Но не делайте так. Нет никаких правил или обоснований это делать

- #### Между любыми методами всегда оставляйте одну пустую строку
 
неправильно:
``` java
class Jaeger {
    private String name;
    
    public void setName(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }

    public void move() {
        // some code
    }
    public void fire() {
        // some code
    }
}
```

правильно:
``` java
class Jaeger {
    private String name;
    
    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void move() {
        // some code
    }

    public void fire() {
        // some code
    }
}
```

- #### Геттеры и сеттеры для boolean-поля именуются по специальному правилу: для геттера вместо get пишется префикс is, а имя boolean-переменной должно быть прилагательным

правильно:
``` java
class Car {

    private boolean active;

    boolean isActive() {
        return active;
    }

    void setActive(boolean active) {
        this.active = active;
    }
}
```

- #### Используйте this только при конфликте имен, например в сеттерах (и то не всегда). Если конфликта нет, писать this не нужно

будет работать, но использование this избыточно:
``` java
public int getIndex() {
    return this.index;
}

public void setEnteredNumber(int number) {
    this.enteredNumbers[index] = number;
}
```

правильно:
``` java
public void setIndex(int index) {
    this.index = index;
}
```

- #### При именовании переменных, для разделения слов, нижнее подчеркивание _ ставьте только у констант. Все остальные переменные должны именоваться с использованием camelCase

неправильно:
``` java
int hidden_number;
String player_answer;
```

правильно:
``` java
int hiddenNumber;
String playerAnswer;
```

- #### Размещайте методы в классе в порядке их вызовов, а не хаотично, как получится. Код должен читаться сверху вниз, как текст в книге

неправильно:
``` java
private boolean makeMove() {
    inputNumber();
    return compareNumbers();
}

private void inputNumber() {
    // some code
}

public void start() {
    makeMove();
}

private boolean compareNumbers() {
    return true;
}
```

правильно:
``` java
public void start() {
    makeMove();
}

private boolean makeMove() {
    inputNumber();
    return compareNumbers();
}

private void inputNumber() {
    // some code
}

private boolean compareNumbers() {
    return true;
}
```

- #### Если поле является массивом и называется, например enteredNums, то как правильно назвать его сеттер, если он принимает за раз только одно число?

неправильно:
``` java
private int[] enteredNums;
private int index;

void setEnteredNums(int enteredNums) {
    this.enteredNums[index] = enteredNums;
}
```

правильно:
``` java
private int[] enteredNums;
private int index;

void setEnteredNum(int enteredNum) {
    enteredNums[index] = enteredNum;
}
```

## <a name="3">Правила для переменных</a>

- #### Давайте переменным осмысленные и понятные имена, глядя на которые, любому читающему код, было бы понятно, какие данные они хранят

неправильно:
``` java
char a = '+';
int b = 10;
String с = "yes";
```

правильно:
``` java
char sign = '+';
int size = 10;
String answer = "yes";
```

- #### Объявляйте переменные максимально близко к месту их первого использования. Не группируйте их в начале метода

- #### Имя переменной не должно быть глаголом или содержать глагол

неправильно:
``` java
Resume[] getAll = storage.getAll();
```

правильно:
``` java
Resume[] resumes = storage.getAll();
или
Resume[] AllResume = storage.getAll();
```

- #### Перед переменной, при приведении типа, требуется пробел

неправильно:
``` java
(char)i
```

правильно:
``` java
(char) i
```

- #### Имена переменных пишите с маленькой буквы

неправильно:
``` java
int Age;
int Title;
int FullName
```

правильно:
``` java
int age;
int title;
int fullName
```

- #### Аббревиатуры в Java записываются, как имена обычных переменных

неправильно:
``` java
int RAM;
long freqCPU;
String OS;
```

правильно:
``` java
int ram;
long freqCpu;
String os;
```

- #### При использовании сокращенной формы инкремента и декремента, после имени переменной пробел не ставится

неправильно:
``` java
number ++
for(int i = 10; i > 0; i --)
```
		
правильно:
``` java
number++
for(int i = 10; i > 0; i--)
```

- #### При проверке boolean-значений явно указывать true или false не нужно

будет работать, но использование true/false избыточно:
``` java
if(male == false)
while(isNext() == true)
if(isExist(uuid) != true)
```

правильно:
``` java
if(!male)
while(isNext())
if(!isExist(uuid))
```

- #### Инициализируйте переменные (если это возможно) в строке их объявления, а не где-то ниже в коде
		
неправильно:
``` java
double num1;
char sign;
num1 = 4;
sign = '*';
```

правильно:
``` java
double num1 = 4;
char sign = '*';
```

## <a name="4">Общие правила</a>

- #### Перед и после операторов =, +, -, /, *, %, ==, !=, <, <=, >, >= требуется пробел

неправильно:
``` java
System.out.println("дата="+m+"."+d+"."+y);
int length=5;
for (int i=0;i<length;i++)
```

правильно:
``` java
System.out.println("дата = " + m + "." + d + "." + y);
int length = 5;
for (int i = 0; i < length; i++)
```

- #### Между ){ скобками требуется пробел

неправильно:
``` java
public static void main(String[] args){
for (int i = 10; i > 0; i--){
if (a > 10){
```

правильно:
``` java
public static void main(String[] args) {
for (int i = 10; i > 0; i--) {
if (a > 10) {
```

- #### Форматирование фигурных скобок

неправильно (так форматируют в C# и C++):
``` java
foo()
{
}
```

правильно:
``` java
foo() {
}
```

- #### Форматирование else и else if

неправильно:
``` java
}
else {
    System.out.println("Exit");
}
```

правильно:
``` java
} else {
    System.out.println("Exit");
}
```
	
неправильно:
``` java
}
else if (size < storage.length) {
```

правильно:
``` java
} else if (size < storage.length) {
```

плохо (зачем тратить лишнюю строку под if):
``` java
} else {
    if (number > randomNumber) {	
```
	
хорошо:
``` java
} else if (number > randomNumber) {
````
	
- #### Форматирование цикла do-while

неправильно:
``` java
do {
    // some code
}
while (answer.equals("yes"));
```

правильно:
``` java
do {
    // some code
} while (answer.equals("yes"));
```

- #### Если ветка if-else или тело цикла состоит из одного выражения, всегда заключайте их в {}. Это поможет избежать трудно уловимых багов

плохо:
``` java
if (doc.isImportant)
    send(doc);
else
    System.out.println("Throw out the trash");
    delete(doc);
```

плохо:
``` java
while(number < 5)
    System.out.println("number less");
    number++;
```

хорошо:
``` java
if (doc.isImportant) {
    send(doc);
} else {
    log.info("Throw out the trash");
    delete(doc);
}
```

хорошо:
``` java
while(number < 5) {
    System.out.println("number less");
    number++;
}
```

- #### После , и ; требуется пробел

неправильно:
``` java
public void addAttempt(int number,int i)
for (int i = 0;i < storage.length;i++)
```

правильно:
``` java
public void addAttempt(int number, int i)
for (int i = 0; i < storage.length; i++)
```

- #### После ( и перед ) скобками пробел не требуется

неправильно:
``` java
for ( int i = 0; i < 21; i++ )
compareNumber( String number )
```

правильно:
``` java
for (int i = 0; i < 21; i++)
compareNumber(String number)
```

- #### Если класс называется Player, то у его полей или методов слово Player уже использовать не нужно, т.к. и так понятно, что все, что там находится относится к Player, а не к Cat или к колбасе :)

неправильно:
``` java
public class Player {
	
    private int[] playerNumbers = new int[10];

    public int getPlayerNumber(int index) {
        return playerNumbers[index];
    }
}
```

правильно:
``` java
public class Player {
	
    private int[] numbers = new int[10];

    public int getNumber(int index) {
        return numbers[index];
    }
}
```

- #### После package и import требуется пустая строка

неправильно:
``` java
package com.webapp.storage;
import java.util.Scanner;
public class ArrayStorage {
```

правильно:
``` java
package com.webapp.storage;

import java.util.Scanner;

public class ArrayStorage {
```

- #### Размещайте комментарии над комментируемым кодом, а не справа от него. Комментарий должен начинаться с той же позиции, что и код

неправильно:
``` java
int sumOdd = 10; // сумма нечетных чисел
```

правильно:
``` java
// сумма нечетных чисел
int sumOdd = 10;
```
	
- #### При создании переменной для хранения ссылки на массив и самого массива, размещайте [] в Java-стиле, а не в Си или С++, а также не ставьте лишних пробелов

неправильно:
``` java
int numbers[]
int [] numbers
int numbers []
new int [10]
```

правильно:
``` java
int[] numbers = new int[10]
```

- #### Имя boolean-переменной должно быть прилагательным

неправильно:
``` java
boolean security
boolean answer
boolean continue
```

правильно:
``` java
boolean active
boolean current
boolean alive
```

- #### Не забывайте код, вложенный в класс, метод, цикл и другие конструкции, которые имеют тело в виде { } каждый раз сдвигать вправо на 4 пробела (или один tab) относительно начала этой конструкции

неправильно:
``` java
public class Person {

    int age = 25;

    public static void main(String[] args) {
    if (age > 20) {
    System.out.println("Человек старше 20 лет");
    }
}
}
```
		
правильно:
``` java
public class Person {

    int age = 25;

    public static void main(String[] args) {
        if (age > 20) {
            System.out.println("Человек старше 20 лет");
        }
    }
}
```

- #### Если имя переменной/метода/класса состоит из более, чем одного слова, то для именование используется camelCase

неправильно:
``` java
int playeranswer
class Guessnumbermain
void addnumber()
```

правильно:
``` java
int playerAnswer
class GuessNumberMain
void addNumber()
```

- #### Стандартное именование для счетчиков в цикле for - это i, j, k. Последние два используются для вложенных циклов
плохо:
``` java
for(a = 0; a < 3; a++) {    
}
```

плохо:
``` java
for(d = 0; d < 10; d++) {
    for(c = 0; c < 4; c++) {    
    }
}
```

хорошо:
``` java
for(i = 0; i < 3; i++) {    
}
```

хорошо:
``` java
for(i = 0; i < 10; i++) {
    for(j = 0; j < 4; j++) {    
    }    
}
```

- #### При переносе строки каждую следующую ее подстроку необходимо смещать вправо на 8 пробелов относительно первой строки

неправильно:
``` java
System.out.println("Characteristics:\n" +
"age = " + age + "\n" +
"name = " + name + "\n" +
"color = " + color);
```

правильно:
``` java
System.out.println("Characteristics:\n" +
        "age = " + age + "\n" +
        "name = " + name + "\n" +
        "color = " + color);
```
