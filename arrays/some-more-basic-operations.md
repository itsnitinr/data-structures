---
description: 'The get, set, min, max, sum and average operations.'
---

# Some More Basic Operations

### Functions : 

* getElement\(\)
* setElement\(\)
* getMin\(\)
* getMax\(\)
* getSum\(\)
* getAverage\(\)

#### getElement\(\) function: 

```c
int getElement(int a[], int n, int index) {
    if (index >= 0 && index < n) {
        return a[index];
    } else {
        return -1;
    }
}
```

#### setElement\(\) function: 

```c
void setElement(int a[], int n, int index, int value) {
    if (index >= 0 && index < n) {
        a[index] = value;
    } else {
        printf("Wrong index !");
    }
}
```

#### getMax\(\) function:

```c
int getMax(int a[], int n) {
    int max = a[0];
    for (int i = 0; i < n; i++) {
        if (a[i] > max) {
            max = a[i];
        }
    }
    return max;
}
```

#### getMin\(\) function: 

```c
int getMin(int a[], int n) {
    int min = a[0];
    for (int i = 0; i < n; i++) {
        if (a[i] < min) {
            min = a[i];
        }
    }
    return min;
}
```

#### getSum\(\) function: 

```c
int getSum(int a[], int n) {
    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum = sum + a[i];
    }
    return sum;
}
```

#### getAverage\(\) function:

```c
float getAverage(int a[], int n) {
    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum = sum + a[i];
    }
    float average = sum/n; 
    return average;
}
```

Contributed by Nitin Ranganath

