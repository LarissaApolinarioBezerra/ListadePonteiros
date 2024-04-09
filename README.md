# ListadePonteiros

Nome: Larissa Apolinario Bezerra
Matrícula: 20230038525

Nome: Laisa Kaylane Fernandes Medeiros
Matrícula: 20230021475

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

#include <stdio.h>

int main(void) {
  int i, j;
  int *p, *q;
  
 p = &i; //o programa irá rodar porém com há um erro
 
  *q = &j; // não há erro
  p = &*&i; // não há erro
  i = (*&)j; // há erro, pois é ilegal (falta uma expressão no parênteses)
  i = &&j; // não há erro
  q = *p; // também possui um erro, mas o programa ainda rodará
  i = (*p)++ + *q; // não há erro
  
}

--------------------------------------------------------------------

Questão 4 -

int main() {
  int valor;
  int *p1;
  float temp;
  float *p2;
  char aux;
  char *nome = "Ponteiros";
  char *p3;
  int idade;
  int vetor[3];
  int *p4;
  int *p5;
  
a)valor = 10;
  p1 = &valor;
  *p1 = 20;
  printf("%d \n", valor); -> saida: 20

b)temp = 26.5;
  p2 = &temp;
  *p2 = 29.0;
  printf("%.1f \n, temp); -> saida: 29.0

c)p3 = &nome[0];
  aux = *p3;
  printf("%c \n", aux); -> saida: P

d)  p3 = &nome[4];
  aux = *p3;
  printf("%c \n", aux); -> saida: e

e) p3 = nome;
  printf("%c \n", *p3); -> saida: P

f)p3 = p3 +4;
  printf("%c \n", *p3); -> saida: e

g) p3--;
   printf("%c \n", *p3); -> saida: t

  vetor[0] = 31;
  vetor[1] = 45;
  vetor[2] = 27;

h)p4 = vetor;
  idade = *p4;
  printf("%d \n", idade); -> saida: 31

i) p5 = p4 +1;
  idade = *p5;
  printf("%d \n", idade); -> saida: 45

j) p4 = p5 +1;
  idade = *p4;
  printf("%d \n", idade); -> saida: 27

l)p4 = p4 -2;
  idade = *p4;
  printf("%d \n", idade); -> saida: 31

m) p5 = &vetor[2] - 1;
  printf("%d \n", *p5); -> saida: 45

n) p5++;
  printf("%d \n", *p5); -> saida: 27

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
   
----------------------------------------------------------------------------------------

Questão 9 -


---------------------------------------------------------------------------------------

Questão 10 -

O programa tem um erro de compilação devido à tentativa de atribuir um valor inteiro ('3') a um ponteiro para uma constante ('int const *x'). Além disso, mesmo que a atribuição fosse corrigida, o programa tenta modificar o valor apontado por 'x' ao tentar incrementá-lo ('++(*x)'), o que não é possível devido à qualificação 'const'. Portanto, a saída do programa é indeterminada devido ao erro de compilação.

----------------------------------------------------------------------------------------

Questão 11 -



----------------------------------------------------------------------------------------

Questão 12 -

#include <stdio.h>

int main(void){
  float aloha [10], coisas[10][5], *pf, value = 2.2;
  int i=3;

  aloha[2] = value; // A expressão é válida, pois o valor de value será armazenado na posição 3 do vetor aloha
  scanf("%f", &aloha); // A expressão é válida, porém se o vetor não for preenchido, pode aparecer valores aleatórios
  aloha = value; // A expressão não é válida, pois um vetor não pode receber um valor sem especificar o endereço da posição do vetor
  printf("%f", aloha); // A expressão é válida
  coisas[4][4] = aloha[3]; // A expressão é válida
  coisas[5] = aloha; // Não é válida, porque não podemos atribuir a uma variável um vetor
  pf = value; // Não é válida, pois a variável pf é do tipo ponteiro e só recebe valores do tipo inteiro
  pf = aloha; // A expressão é válida 
  
  ----------------------------------------------------------------------------------

  Questão 13 -

  Um memory leak ocorre em um programa quando alocamos memória dinamicamente (usando funções como malloc, calloc ou realloc), mas não liberamos essa memória quando não precisamos mais dela. Isso resulta em uma perda gradual de memória RAM disponível para o sistema operacional. Exemplo 1: #include <stdlib.h>

int main() {
    while (1) {
        int *ptr = (int *)malloc(sizeof(int));
        // Não há liberação de memória
    }
    return 0;
} // Neste exemplo, o programa entra em um loop infinito e aloca repetidamente memória dinâmica sem liberá-la. Isso eventualmente levará a um esgotamento da memória disponível. Exemplo 2: #include <stdlib.h>

int main() {
    int *ptr = (int *)malloc(sizeof(int));
    // Não há liberação de memória
    return 0;
} // Neste exemplo, o programa aloca memória dinâmica no início, mas não libera antes de terminar sua execução. Isso resulta em uma perda de memória, pois a memória alocada não está mais acessível. Exemplo 3: #include <stdlib.h>

int main() {
    while (1) {
        int *ptr = (int *)malloc(sizeof(int));
        free(ptr); // Libera a memória, mas dentro do loop, então a alocação é feita novamente
    }
    return 0;
} // Neste exemplo, embora a memória seja liberada dentro do loop, ela é imediatamente realocada. Isso cria uma situação em que a memória é continuamente alocada e liberada, mas nunca disponibilizada para outros fins, resultando em um uso ineficiente da memória.
____________________________________________________________

Questão 14 -

Um ponteiro para uma função é um ponteiro que armazena o endereço de memória de uma função. Isso permite que você chame a função indiretamente, usando o ponteiro como se fosse o próprio nome da função. Exemplo: #include <stdio.h>

// Definindo uma função simples
int soma(int a, int b) {
    return a + b;
}

int main() {
    int (*ptr)(int, int); // Declarando um ponteiro para uma função que recebe dois inteiros e retorna um inteiro
    ptr = soma; // Atribuindo o endereço da função 'soma' ao ponteiro

    int resultado = (*ptr)(3, 4); // Chamando a função através do ponteiro
    printf("O resultado da soma é: %d\n", resultado);

    return 0;
}
