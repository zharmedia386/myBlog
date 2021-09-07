---
title: 'Materi Dasar Struktur Data'
date: 2021-09-07
tags: ['Struktur-Data', 'Algoritma']
type: post
weight: 20
---

![alt text](/images/img-6.jpg)

# Pendahuluan

Struktur data adalah suatu metode atau cara dalam menyusun, mengatur serta menyimpan berbagai data yang terdapat dalam suatu penyimpanan dalam sistem komputer. Data ini sendiri bermacam-macam, bisa berbentuk angka, simbol, huruf dan lain sebagainya.

Istilah struktur data juga berarti cara tertentu dalam menyimpan, mengatur maupun mengorganisir data, baik itu di dalam memori komputer ataupun media penyimpanan eksternal sehingga bisa dimanfaatkan secara efektif dan efisien. Kedua pengertian tersebut adalah definisi struktur data jika didasarkan pada ilmu komputer.

Sementara jika didasarkan pada teknik pemrograman, struktur data mempunyai arti yang berbeda. Yaitu tata letak data yang memuat kolom data, baik itu kolom yang bisa dilihat pengguna maupun kolom yang cuma dipakai untuk tujuan pemrograman saja sehingga tidak bisa dilihat oleh pengguna.

# Tipe Struktur Data

Lanjut dengan tipe struktur data, ini kurang lebih ada 6 yaitu tipe Graph, Tree, Queue, Stack, Linked List dan Array. Penjelasan singkat keenam tipe tersebut ialah sebagai berikut.

1. Graph

Tipe yang cukup sering digunakan dalam berbagai kesempatan. Graph sendiri merupakan struktur data yang non-linear dan terdiri dari kumpulan node. Node-node tersebut disambungkan oleh suatu garis tertentu.

Garis yang dimaksud bisa memiliki arah atau justru sebaliknya. Contoh untuk tipe ini yang sangat mudah Anda amati ialah jalur network di sebuah LAN, jalur telepon di suatu kota dan lain sebagainya.

2. Tree

Seperti namanya, tipe yang kedua ini bisa diibaratkan dengan akar di suatu pohon. Jadi, tipe ini bisa dimaknai sebagai kumpulan node dan masing-masing node tersebut tersusun dari value dan juga berbagai referensi lainnya. Nah, Tree yang terdiri atas maksimal 2 anak akan disebut sebagai Binary Tree.

Jika Anda lihat, Binary Tree mempunyai dua sub Tree yang terletak di bagian kiri serta kanan. Ciri-cirinya adalah bagian kiri mempunyai nilai root yang lebih kecil dibandingkan dengan bagian yang kanan.

Untuk mengakses data dalam Tree ini ada 3 cara yang bisa Anda lakukan, yaitu postorder, pre-order dan inorder.

3. Queue

Struktur data yang bersifat LIFO atau Last In First Out. Dalam Queue ini juga ada 3 operasi sekaligus yang bisa Anda lakukan yakni peek atau melihat data yang paling awal dari suatu Queue, dequeue atau menghapus data yang pertama dari Queue dan enqueue atau memasukkan data dalam Queue.

4. Stack

Stack ini adalah tipe yang mirip seperti Queue. Tipe ini juga mempunyai sifat LIFO karena termasuk struktur data yang linear. Selayaknya Queue, dalam Stack ini juga ada 3 jenis operasi sekaligus yang bisa dilakukan.

Operasi pertama ialah Peek atau memantau data teratas Stack. Operasi kedua ialah Push atau yang bisa diartikan sebagai memasukkan suatu data baru dalam Stack, dan operasi yang terakhir ialah Pop atau menghapus data yang paling atas dalam Stack.

5. Linked list

Jika diartikan secara kasar, maka Linked List berarti daftar yang terhubung. Ya, sesuai dengan namanya, tipe satu ini memang berupa potongan-potongan aneka macam data yang tersimpan secara acak.

Berbagai potongan data tersebut akan ada dalam memori komputer dan data yang dimaksud memiliki referensi yang saling menunjuk satu sama lain.

Jadi, sudah paham bukan kenapa tipe ini disebut sebagai Linked List? Dalam tipe satu ini, data yang pertama biasa disebut sebagai head, sementara data yang terakhir akan disebut sebagai tail.

Jika melihat jumlah data yang diinput atau dimasukkan, Linked List memiliki kemampuan untuk terhubung baik itu secara singly linked list ataupun doubly linked list.

Maksud dari singly linked list ialah data bisa diakses hanya dengan arah maju mulai dari data pertama atau head ke data terakhir atau tail. Data tersebut tidak bisa diakses sebaliknya, yakni dari tail ke head.

Sementara untuk doubly linked list, data bisa diakses dari dua arah yakni dari head ke tail atau sebaliknya, dari tail ke head. Dengan kata lain, aksesnya bisa dibuat bolak balik.

# Implementasi Struktur Data

Contoh berikut implementasi yang ditulis dalam bahasa C dengan menggunakan alokasi secara dinamis

## 1. ADT Stack

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <malloc.h>
#include <stdbool.h>

typedef char Infotype;
typedef struct elmt *address;

typedef struct elmt{
  Infotype data;
  address next;
}Node;

typedef struct{
  address Top;
}Stack;

void CreateStack(Stack *S){
  S->Top = NULL;
}

address Alokasi(Infotype X){
  address P = (address)malloc(sizeof(Node));
  P->data = X;
  return P;
}

bool isEmpty(Stack S){
  if(!S.Top){
    return false;
  }
  else{
    return true;
  }
}

int CountElement(Stack S){
  int result = 0;
  address P = S.Top;
  if(!S.Top){
    while(!S.Top->next){
      P = P->next;
      result++;
    }
  }
  return result;
}

void Push(Stack *S, Infotype input){
  address P = Alokasi(input);
  P->next = S->Top;
  S->Top = P;
}

void Pop(Stack *S){
  address P = S->Top;
  printf("\nNode '%c' sudah dihapus\n",P->data);
  S->Top = S->Top->next;
  P->next = NULL;
  free(P);
}

void ReadElement(Infotype *input){
  printf("Isi Node : ");
  scanf("%c",input);
  fflush(stdin);
}

void PrintElement(Stack S){
  printf("PRINT ELEMENT\n");
  int i = 1;
  while(S.Top != NULL){
    printf("Huruf ke-%d : %c\n",i,S.Top->data);
    S.Top = S.Top->next;
    i++;
  }
}

int main(){
  Stack S;
  Infotype data;

  // Membuat Stack Baru
  CreateStack(&S);

  printf("READ ELEMENT\n");

  // Menambah Node pada Stack - Operasi Push
  ReadElement(&data);
  Push(&S,data);

  // Menambah Node pada Stack - Operasi Push
  ReadElement(&data);
  Push(&S,data);

  // Menambah Node pada Stack - Operasi Push
  ReadElement(&data);
  Push(&S,data);

  // Menghapus Node pada Stack - Operasi Pop
  Pop(&S);

  printf("\n");

  // Menampilkan Seluruh Isi Node ke Layar
  PrintElement(S);

  return 0;
}
```

## 2. ADT Queue

```c
/* Antrian Masuk Ruangan */
#include <stdlib.h>
#include <stdio.h>
#include <stdbool.h>
#include <malloc.h>
#include <string.h>

// Kamus data
typedef struct{
  char nama[20];
}Pelanggan;

typedef Pelanggan Infotype;
typedef struct elmt *address;

typedef struct elmt{
  Infotype data;
  address Next;
}Node;

typedef struct{
  address Front;
  address Rear;
}Queue;

// Algoritma
void CreateQueue(Queue *Q){
  Q->Front = NULL;
  Q->Rear = NULL;
}

address Alokasi(Infotype X){
  address P = (address)malloc(sizeof(Node));
  strcpy(P->data.nama,X.nama);
  return P;
}

bool isEmpty(Queue Q){
  if(Q.Front)
    return true;
  else
    return false;
}

int CountElement(Queue Q){
  int result = 0;
  address P = Q.Front;
  while(!Q.Front){
    Q.Front = Q.Front->Next;
    result++;
  }
  return result;
}

void EnQueue(Queue *Q, Infotype input){
  address P = Alokasi(input);
  Q->Rear->Next = P;
  Q->Rear = P;
}

void DeQueue(Queue *Q){
  address P = Q->Front;
  P = P->Next;
  P->Next = NULL;
  free(P);
}

void ReadElement(Infotype *input){
  printf("Nama Pelanngan : ");
  scanf("%[^\n]c",input->nama);
  fflush(stdin);
}

void PrintElement(Queue Q){
  address P = Q.Front;
  int i = 1;
  printf("PRINT ELEMENT\n");
  while(!P){
    printf("Pelanggan ke-%d : %s\n",i,P->data.nama);
    P = P->Next;
    i++;
  }
}

int main(){
  Queue Q;
  Infotype data;

  // Membuat Antrian Baru
  CreateQueue(&Q);

  printf("READ ELEMENT\n");

  // Menambah Antrian Baru di Rear
  ReadElement(&data);
  EnQueue(&Q,data);

  // Menambah Antrian Baru di Rear
  ReadElement(&data);
  EnQueue(&Q,data);

  // Menghapus Antrian di Front
  // DeQueue(&Q);

  printf("\n");

  // Menampilkan Seluruh Isi Antrian Baru
  PrintElement(Q);

  return 0;
}
```

# Referensi

- [QWords](https://qwords.com/blog/apa-itu-struktur-data/)
