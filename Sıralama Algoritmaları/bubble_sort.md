![Bubble Sort](../assets/bubble_sort.png)

Bubble Sort (Kabarcık Sıralaması) algoritması, basit ve karşılaştırma temelli bir algoritmadır. Dizide bulunan her eleman yanındaki eleman ile karşılaştırılır. İlk elemanın değeri, ikinci elemanın değerinden büyükse iki eleman yer değiştirir. Sonrasında ikinci ve üçüncü elemanların değerleri karşılaştırılır. İkinci elemanın değeri üçüncü elemanın değerinden büyükse bu iki eleman da yer değiştirir. Dizi tamamen bitene kadar bu işlem sürer.

## Örnek
`15,5,1,9` dizisini Bubble Sort algoritması ile sıralamamız gerekirse;

1. <b>Birinci İterasyon</b>
    1. İlk iki eleman birbirleriyle karşılaştırılır. `5 < 15` olduğu için elemanlar yer değiştirir. Dizi `5,15,1,9` olur.
    2. İkinci ve üçüncü elemanlar birbirleriyle karşılaştırılır. `1 < 15` olduğu için elemanlar yer değiştirir. Dizi `5,1,15,9` olur.
    3. Üçüncü ve dördüncü elemanlar birbirleriyle karşılaştırılır. `9 < 15` olduğu için elemanlar yer değiştirir. Dizi `5,1,9,15` olur.

    Üç adımda birinci iterasyon tamamlandı fakat sayılar hala sıralı değil. Bu yüzden ikinci iterasyona başlayacak ve aynı işlemler tekrarlanacak

2. <b>İkinci İterasyon</b>
    1. İlk iki eleman birbirleriyle karşılaştırılır. `1 < 5` olduğu için elemanlar yer değiştirilir. Dizi `1,5,9,15` olur
    2. İkinci ve üçüncü elemanlar birbirleriyle karşılaştırılır. Sıralı oldukları için herhangi bir işlem yapılmaz.
    3. Üçüncü ve dördüncü elemanlar birbirleriyle karşılaştırılır. Sıralı oldukları için herhangi bir işlem yapılmaz.

    Böylelikle iki iterasyonda dizi içerisindeki elemanlar sıralanmış olur. 

## Örnek Kod
```c
#include <stdio.h>

void bubbleSort(int array[], int size) {
  for (int step = 0; step < size - 1; ++step) {
    for (int i = 0; i < size - step - 1; ++i) {
      if (array[i] > array[i + 1]) {
        int temp = array[i];
        array[i] = array[i + 1];
        array[i + 1] = temp;
      }
    }
  }
}

void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

int main() {
  int data[] = {15,5,1,9};

  int size = sizeof(data) / sizeof(data[0]);
  bubbleSort(data, size);
  printf("Sıralanmış Dizi:\n");
  printArray(data, size);
}
```
