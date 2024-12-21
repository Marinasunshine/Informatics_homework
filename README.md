# Лабораторная работа: использование команды grep

Grep (Global Regular Expression Print) — это мощный инструмент командной строки для поиска текстовых данных в файлах. Он используется для поиска строк, соответствующих заданному шаблону или регулярному выражению, и вывода их в стандартный поток вывода.

Основной синтаксис выглядит так:
```
grep [опции] шаблон файл
````
* шаблон — текст или регулярное выражение, по которому производится поиск
* файл — имя файла или список файлов, в которых нужно выполнить поиск
* опции — дополнительные параметры, которые уточняют, как выполняется поиск

### Задание 0 для разминки

1. Создадим файл `example.txt` со следующим содержимым:
    ```
    Cats are great pets
    Dogs are loyal companions
    Birds can be noisy
    Fish are calming to watch
    Reptiles are unique
    Taking care of animals is rewarding
    Feeding pets regularly is essential
    Grooming helps maintain pet health
    Vet visits keep pets healthy
    ```
2. Найдём строки, содержащие слово `pets` (регистр букв должен учитываться):

    ```
    grep "pets" example.txt
    ```
4. Повторим поиск, игнорируя регистр букв, с помощью ключа `-i`:

   ```
    grep -i "pets" example.txt
    ```
6. Найдём строки, содержащие слово `are` в начале строки:

    ```
    grep "^are" example.txt
    ```
8. Используем ключ `-v`, чтобы найти строки, которые не содержат слово `Dogs`:

    ```
    grep -v "Dogs" example.txt
    ```
10. Теперь найдём строки, содержащие слова, заканчивающиеся на `ing`:

     ```
    grep "ing\b" example.txt
    ```
Все выводы мы видим в терминале, поэтому с помощью `--color` можно сделать их цветными. Например:
```
grep --color=auto "pets" example.txt
```
### Задание 1

Конечно же, grep имеет намного больше возможностей, поэтому эту команду часто используют в bash-скриптах для автоматизации задач. 
Создайте файл `orders.txt` со следующим содержимым:
```
Order ID: 1001 | Customer: John Doe | Item: Book | Quantity: 3 | Total: $120.00 | Date: 2024-12-01
Order ID: 1002 | Customer: Jane Smith | Item: Pen | Quantity: 10 | Total: $12.00 | Date: 2024-12-02
Order ID: 1003 | Customer: Emily Johnson | Item: Notebook | Quantity: 5 | Total: $25.00 | Date: 2024-12-02
Order ID: 1004 | Customer: Michael Brown | Item: Backpack | Quantity: 1 | Total: $50.00 | Date: 2024-12-03
Order ID: 1005 | Customer: Chris Davis | Item: Marker | Quantity: 20 | Total: $200.00 | Date: 2024-12-03
Order ID: 1006 | Customer: Patricia Wilson | Item: Book | Quantity: 2 | Total: $30.00 | Date: 2024-12-04
Order ID: 1007 | Customer: Daniel Garcia | Item: Chair | Quantity: 1 | Total: $300.00 | Date: 2024-12-05
Order ID: 1008 | Customer: Sarah Martinez | Item: Desk | Quantity: 1 | Total: $250.00 | Date: 2024-12-05
```
Создайте скрипт process_orders.sh, который выполняет следующие задачи:
1. Найдите все заказы, в которых общая сумма (`Total`) превышает $100, и сохраните их в файл `high_value_orders.txt`.
2. Подсчитайте, сколько раз заказывался каждый товар (например, `Book`, `Pen` и т. д.).
3. Используя регулярные выражения, выберите заказы, сделанные в первые два дня месяца (`2024-12-01` и `2024-12-02`), и сохраните их в файл `early_orders.txt`.
4. Найдите заказы, в которых имя клиента содержит `son`, и выведите их в терминал.

Сделайте скрины с результатом работы скрипта

### Как успешно сдать работу?

Создать свой репозиторий из шаблона этого. Как это делается - "Use this template" -> "Create a new repository" и сделайте его public. 

Находясь уже в своем репозитории - создайте новый файл формата .md и там оформляйте отчет. В отчете опишите все шаги которые вы делали, чтобы получить финальный результат работы.

Что вам нужно знать, чтобы успешно защитить работу: что такое grep и для чего используется, использование ключей grep, основы регулярных выражений, логика работы скрипта.

### Дополнительные материалы

1. [Команда GREP в Linux](https://zomro.com/rus/blog/faq/509-grep-command-in-linux)
2. [Документация GREP](https://man7.org/linux/man-pages/man1/grep.1.html)
3. [Ответ на ваш вопрос по опциям и регулярным выражениям также можете найти здесь](https://stackoverflow.com/)
4. [Место, где точно есть ответ](https://www.google.ru/webhp)
   

