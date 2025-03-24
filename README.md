# Narnia - OverTheWire
## Nivel 0 - Desbordamiento de Buffer (Buffer Overflow)

### 🎯 Objetivo
Modificar el valor de la variable `val` a `0xdeadbeef` mediante un desbordamiento de buffer para ejecutar `/bin/sh`.

---

### 📄 Código fuente del binario `narnia0.c`

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    long val = 0;
    char buf[20];

    printf("Buf: ");
    fgets(buf, 128, stdin);

    if(val == 0xdeadbeef) {
        printf("you have correctly got the variable to the right value\n");
        system("/bin/sh");
    } else {
        printf("val = %p :(\n", val);
    }

    return 0;

