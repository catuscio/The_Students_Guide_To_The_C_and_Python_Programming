# 단일연결리스트 코드

## Struct
```c
typedef struct node {
  struct node* next;
  int elem;
}Node;

typedef struct list {
  Node* head;
}List;
```

## Function
```c
Node* getNode(int e);

// add
void addLast(List* lst, int e);
// remove
void removeFirst(List* lst);
// get
int get(List* lst, int r);
// print
void printList(List* lst);
```

## NewNode
```c
Node* NewNode(int e)
{
  Node* p = (Node*)malloc(sizeof(Node));
  p->next = NULL;
  p->elem =e;
  
  return p;
}

## addLast
```c
void addLast(List* lst, int e)
{
  Node* p = lst->head;
  Node* q = NewNode(e);
  if (p == NULL) {
    lst->head = q;
    return 0;
  }
  while (1) {
    if (p->next == NULL) {
      break;
    }
    p = p->next;
  }
  p->next = q;
}
```

## removeFirst
```c
void removeFirst(List* lst)
{
  Node* p = lst->head;
  if (p == NULL) {
    printf("null list\n");
    return 0;
  }
  if (p->next == NULL) {
    p = NULL;
    return 0;
  }
  lst->head = p->next;
}
```

## get
```c
int get(Lit* lst, int r)
{
  Node* p = lst->head:
  for (int i = 0; i < r - 1; i++) {
    if (p->next == NULL) {
      printf("index error\n");
      return 0;
    }
    p = p->next;
  }
  return p->elem;
}
```

## printList
```c
void printList(List* lst)
{
  Node* p = lst->head;
  if (p == NULL) {
    printf("null list\n");
    return 0;
  }
  while (1) {
    printf(" %d", p->elem);
    if (p->next == NULL) {
      break;
    }
    p = p->next;
  }
  printf("\n");
}

## Error
### index error
```c
if (p->next == NULL) {
			printf("index error\n");
			return 0;
}
```

### null list
```c
if (p == NULL) {
  printf("null list\n");
  return 0;
}
```

## main
```c
void main()
{
  List A;
  A.head = NULL;
  printList(&A);
  removeFirst(&A);
  for (int i = 1; i < 8; i++) {
    addLast(&A, i);
  }
  printf("%d\n", get(&A, 8));
  
  removeFirst(&A);
  
  printList(&A);
}










