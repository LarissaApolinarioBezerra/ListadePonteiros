# ListadePonteiros
Nome: Larissa Apolinario Bezerra
Matrícula:
Nome: Laisa Kaylane
Matrícula:

Questão 1 -

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

---------------------------------------------------------------------

Questão 2 -

#include <stdio.h>
int main(){ 
int i=5, *p;
p = &i;
printf("%x %d %d %d %d", p,*p+2,**&p,3**p,**&p+4); 
return 0;
{
-> A saida será: "0000FFE 7 5 15 9"

--------------------------------------------------------------------

Questão 3 -

--------------------------------------------------------------------

Questão 4 -

--------------------------------------------------------------------

Questão 5 -

#include <stdio.h>

int main(void){
  float vet[5] = {1.1,2.2,3.3,4.4,5.5};
  float *f;
  int i;
  f = vet;
  printf("contador /valor /valor /endereco /endereco");
  for(i = 0 ; i <= 4 ; i++){
  printf("\ni = %d",i);
  printf(" vet[%d] = %.1f",i, vet[i]);
  printf(" *(f + %d) = %.1f",i, *(f+i));
  printf(" &vet[%d] = %X",i, &vet[i]);
  printf(" (f + %d) = %X",i, f+i);
  }
}

// Os resultados obtidos estão de acordo com o esperado, pois deviam imprimir na tela: 
// o título (contador / valor / valor / endereço / endereço), os contadores (cada um de acordo com seu loop), o valor dado para as expressões e o endereço de cada array.
//O endereço pode variar, resultando nos seguintes endereços v[0]= 580A68B0; v[1]= 580A68B4; v[2]= 580A68B8; v[3]= 580A68BC e v[4]= 580A68C0.

-> Saída:
contador /valor /valor /endereco /endereco
i = 0 vet[0] = 1.1 *(f + 0) = 1.1 &vet[0] = 580A68B0 (f + 0) = 580A68B0
i = 1 vet[1] = 2.2 *(f + 1) = 2.2 &vet[1] = 580A68B4 (f + 1) = 580A68B4
i = 2 vet[2] = 3.3 *(f + 2) = 3.3 &vet[2] = 580A68B8 (f + 2) = 580A68B8
i = 3 vet[3] = 4.4 *(f + 3) = 4.4 &vet[3] = 580A68BC (f + 3) = 580A68BC
i = 4 vet[4] = 5.5 *(f + 4) = 5.5 &vet[4] = 580A68C0 (f + 4) = 580A68C0

--------------------------------------------------------------------

Questão 6 -

*(pulo + 2);
*(pulo + 4);
pulo + 4;
pulo + 2;

-> Resposta = *(pulo+2)

--------------------------------------------------------------------

Questão 7 - 

#include <stdio.h>

int main(void){
  int mat [4];
  int *p,x;
  
  p = mat + 1; //A expressão é válida, visto que o ponteiro p irá receber o endereço mat[1], que representa a segunda posição do vetor
  p = mat++; // A expressão não é válida, pois não podemos incrementar um valor do tipo int, logo devemos utilizar ele para incrementar o valor guardado em alguma das posições
  p = ++mat; // A expressão também não é válida, pelo mesmo motivo que a anterior, porque mudar a ordem do incremento não altera em nada nesse caso
  x = (*mat)++; // A expressão é válida, já que estamos pegando o valor que está guardado no endereço mat[0] e incrementando-o
  }

  ------------------------------------------------------------------

  Questão 8 -
  
 int main(){
  int vet[] = {4,9,13};
  int i;
  for(i=0;i<3;i++){
  printf("%d ",*(vet+i));
  }
}

-> O programa declara um vetor de numeros inteiros e declara com tres valores "4, 9 e  13". Então, cria um laço de repetição o qual irá printar os valores do vetor "vet[]".
   O laço de repetição iniciará com uma variavel auxiliar i com o valor zero, e quebrará o laço quando a variavel for maior que tres, aumentando em 1 o valor de I a cada repetição.
    Desta maneira, ao utilizar "(*vet+i)" o programa caminhará pela memoria do vetor "vet[]" de 4 em 4 bits, printando os numeros "4, 9 e 13";



int main(){
  int vet[] = {4,9,13};
  int i;
  for(i=0;i<3;i++){
  printf("%X ",vet+i);
  }
}

-> O segundo programa é semelhante com o primeiro, mas com a utilização da linha "%X, vet+i" (diferente da questao anterior "%d ",*(vet+i)") 
   o programa mostrará para o usuario os endereços de cada numero do vetor, e nao seus valores.

----------------------------------------------------------------------------

  
