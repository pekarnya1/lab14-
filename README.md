# Домашнее задание к работе 14
## Условие задачи
32. Определение количества элементов массива меньше или равных взвешенному среднему
(среднему арифметическому всех значений за исключением максимального и
минимального значения)

## 1. Алгоритм и блок-схема
## Алгоритм

```
1. Начало.
2. Ввод данных size, n;
3. Заполняем массив size
4. Вызывается функция int task32(double* size, int n)
  - Создаём переменную сумму и макс/мин значения
  - Ищем максимальный элемент и минимальный
  - Считаем среднее арифметическоe: double avg = (sum - min - max) / (n - 2);
  - Проходимся по массиву и если число меньше ср арифм, то увеличиваем count
  - Возвращаем count
5. Печать массива printf("Результат: %d\n", task32(size, n));
6.Конец

```
   
### Блок-схема

<img width="283" height="349" alt="image" src="https://github.com/user-attachments/assets/92701164-10dd-4107-9dfb-d3fc8929e389" />






## 2. Реализация программы

```
#define _CRT_SECURE_NO_WARNINGS
#include <locale.h>
#include <stdio.h>

int task32(double* size, int n)
{
	if (n <= 2) return 0;
	double min = 99999, max = -99999, sum = 0;

	for (int i = 0; i < n; i++)
	{
		if (size[i] < min) min = size[i];
		if (size[i] > max) max = size[i];
		sum += size[i];
	}

	double avg = (sum - min - max) / (n - 2);
	int count = 0;
	for (int i = 0; i < n; i++)
	{
		if (size[i] <= avg) count++;
	}
	return count;
}

int main()
{
	setlocale(LC_CTYPE, "RUS");
	double size[100];
	int n;

	printf("Размер: ");
	scanf("%d", &n);
	for (int i = 0; i < n; i++) scanf("%lf", &size[i]);
	
	printf("Результат: %d\n", task32(size, n));
}
```

## 3. Результаты работы программы

```
Размер: 5
1
2
3
4
100
Результат: 3

```


<img width="870" height="308" alt="image" src="https://github.com/user-attachments/assets/ad12d639-db70-4841-b452-f0eefd573cb3" />


