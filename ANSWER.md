## Лабораторная работа: использование команды grep
### Ход работы
1. Создаём текстовый файл и открываем его в текстовом редакторе c помощью следующих команд:
 ```
touch orders.txt
gedit orders.txt
```
Записываем данные в файл и сохраняем.

2. Создаём файл с расширение sh и окрываем его:
 ```
touch process_orders.sh
gedit process_orders.sh
```

# 1. Найдите все заказы, в которых общая сумма (Total) превышает $100, и сохраните их в файл high_value_orders.txt
grep -E "Total: \$[1-9][0-9]{2,}" orders.txt > high_value_orders.txt

# 2. Подсчитайте, сколько раз заказывался каждый товар
# Извлечение всех наименований товаров из файла
grep -oP "Item: \K\w+" orders.txt > items.txt

# Подсчёт уникальных товаров и их количества
uniq -c items.txt > item_counts.txt

# Форматированный вывод результата
while read count item; do
  echo "Item: $item | Count: $count"
done < item_counts.txt

# 3. Выберите заказы, сделанные в первые два дня месяца (2024-12-01 и 2024-12-02), и сохраните их в файл early_orders.txt
grep -E "Date: 2024-12-0[1-2]" orders.txt > early_orders.txt

# 4. Найдите заказы, в которых имя клиента содержит son, и выведите их в терминал
grep -i "Customer: .*son" orders.txt

