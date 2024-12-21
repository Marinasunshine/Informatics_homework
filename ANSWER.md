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

for item in $(grep -oP "Item: \K\w+" orders.txt | sort -u); do
    echo "$item: $(grep -c "Item: $item" orders.txt)"
done > item.txt
