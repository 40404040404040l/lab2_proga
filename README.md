# lab2_proga

Учебная лабораторная работа по программированию на Java с использованием библиотеки `ru.ifmo.se.pokemon`.

Проект моделирует покемон-битву 3 на 3. Для каждого покемона и каждой атаки создан отдельный класс, а запуск боя происходит из `Battleground.java`.

## Что реализовано

- класс `Battleground` для создания и запуска боя;
- команда союзников:
  - `Corsola`;
  - `Vulpix`;
  - `Ninetales`;
- команда противников:
  - `Poliwag`;
  - `Poliwhirl`;
  - `Politoed`;
- собственные классы атак в пакете `Moves`;
- собственные классы покемонов в пакете `Pokemons`;
- подключение внешней библиотеки `Pokemon.jar`.

## Стек

- Java
- IntelliJ IDEA project/module
- библиотека `ru.ifmo.se.pokemon`

## Структура

```text
.
├── Pokemon.jar
└── untitled/
    ├── src/
    │   ├── Battleground.java
    │   ├── Moves/
    │   │   ├── BellyDrum.java
    │   │   ├── ConfuseRay.java
    │   │   ├── Facade.java
    │   │   ├── IcicleSpear.java
    │   │   ├── NastyPlot.java
    │   │   ├── QuickAttack.java
    │   │   ├── Recover.java
    │   │   ├── Refresh.java
    │   │   ├── Rest.java
    │   │   ├── Scald.java
    │   │   ├── Waterfall.java
    │   │   └── WillOWisp.java
    │   └── Pokemons/
    │       ├── Corsola.java
    │       ├── Ninetales.java
    │       ├── Politoed.java
    │       ├── Poliwhirl.java
    │       ├── Poliwag.java
    │       └── Vulpix.java
    └── untitled.iml
```

## Запуск в IntelliJ IDEA

1. Откройте папку `untitled` как Java-проект.
2. Убедитесь, что `Pokemon.jar` подключен как library.
   В проекте это уже прописано в `untitled/untitled.iml`.
3. Запустите файл:

```text
untitled/src/Battleground.java
```

## Запуск из командной строки

Из корня репозитория:

```bash
cd untitled/src
javac -cp ../../Pokemon.jar Battleground.java Pokemons/*.java Moves/*.java
java -cp ".:../../Pokemon.jar" Battleground
```

Для Windows используйте `;` вместо `:` в classpath:

```bash
java -cp ".;../../Pokemon.jar" Battleground
```

## Логика боя

`Battleground` создает объект `Battle`, добавляет союзников и противников, а затем запускает симуляцию:

```java
Battle field = new Battle();

field.addAlly(new Corsola("Corsola", 1));
field.addAlly(new Vulpix("Vulpix", 1));
field.addAlly(new Ninetales("Ninetales", 1));

field.addFoe(new Poliwag("Poliwag", 1));
field.addFoe(new Poliwhirl("Poliwhirl", 1));
field.addFoe(new Politoed("Politoed", 1));

field.go();
```

## Примечания

- `Pokemon.jar` должен лежать в корне репозитория.
- Скомпилированные `.class` файлы не нужны для понимания проекта: основная логика находится в `untitled/src`.
- Проект ориентирован на учебную задачу: показать работу с классами, наследованием, пакетами и внешней библиотекой.
