# ListadePonteiros
- Larissa Apolinario
- Laisa Kaylane


Questão 1 -
Código:

#include <stdio.h>
#include <math.h>

int main(void) {
  int i = 3, j = 5;
  int *p, *q;
  int dif, exp;
  p = &i;
  q = &j;

  if (p == &i){
    printf ("True \n");
  }
  else {
    printf ("False \n");
  }

  dif = *p - *q;
  printf ("A diferença entre *p e *q é %d \n", dif);

  printf ("%d \n", **&p);

  exp = (3 - *p)/(*q + 7);
  printf ("O valor da expressão é %d \n", exp);

  return 0;
}
-> Saída:
True 
A diferença entre *p e *q é -2 
3 
O valor da expressão é 0
