# Практична 2
Виконав: Печкурм Максим

# Опис
Скільки можна сформувати чисел із р розрядів, використовуючи цифри 5 та 9, в яких три однакові цифри не стоять поруч?

Вхідні дані: ціле число р (р ≤ 30)

Вихідні дані: кількість чисел із р розрядів

# Код
```
#include <stdio.h>

int aft(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

int dilf(int a, int b) {
    return (a * b) / aft(a, b);
}

int main() {
    int p;
    printf("Введіть кількість чисел: ");
    scanf("%d", &p);

    if (p < 2 || p > 20) {
        printf("Кількість чисел повино бути між 2 та 20\n");
        return 1;
    }

    int numbers[20];
    printf("Введіть числа: ");
    for (int i = 0; i < p; i++) {
        scanf("%d", &numbers[i]);
    }

    int result = numbers[0];
    for (int i = 1; i < p; i++) {
        result = dilf(result, numbers[i]);
    }  

    printf("НСД: %d\n", result);
    return 0;
}
```
