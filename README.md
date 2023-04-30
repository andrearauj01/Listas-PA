# Lista 01 - Primeira Unidade
Respostas da lista 01 da matéria de Programação Avançada. Turma 02 - 2023.1

----------------------------------------------------------------------------------------------------
1. Seja o seguinte trecho de programa:

int i=3,j=5;
int *p, *q;
p = &i;
q = &j;
1

Determine o valor das seguintes expressões: 
a) p == &i;
b) *p - *q;
c) **&p;
d) 3 - *p/(*q) + 7;

*Resposta:

a) p==&i // Verifica a condição; True = 1

b)*p-*q; // -2

c)**&p; // 3

d) 3-(*p/*q)+7 // *p/*q = 0,6 -> *p e *q são inteiros logo fica: 3-0+7 = 10

----------------------------------------------------------------------------------------------------
2. Mostre o que será impresso por programa supondo que i ocupa o endereço 4094 na memória.

int i=5, *p;
p = &i;
printf("%x %d %d %d %d", p,*p+2,**&p,3**p,**&p+4);
}

*Resposta:

// Para %x -> p: Vai imprimir o endereço dee i em hexadecimal
4094 = OFFE em hexadecimal.

//para %d ->*p+2 = 7.

//para %d -> **&p = 5

//para %d 3**p = 15

//para %d ->> **&p+4 = 9

----------------------------------------------------------------------------------------------------

3. Se i e j são variáveis inteiras e p e q ponteiros para int, quais das seguintes expressões de
atribuição são ilegais?

a) p = i;
b) q = &j;
c) p = &*&i;
d) i = (*&)j;
e) i = *&j;
f) i = *&*&j;
g) q = *p;
h) i = (*p)++ + *q;

*Resposta:

a) p=i; // ERRO

b) q = &j; // OK

c) p=&*&i; // OK

d) i = (*&)j; // ERRO

e) i = *&j; // OK

f) i = *&*&j; // OK

g) q= *p; // ERRO

h) (*p)+++*q;// OK

-----------------------------------------------------------------------------------------------------

4. Determine o que será mostrado pelo seguinte programa (compile-o, execute-o e verifique se
foram obtidas as respostas esperadas).

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
  
  /* (a) */
  
  valor = 10;
  
  p1 = &valor;
  
  *p1 = 20;
  
  printf("%d \n", valor);
  
  
  /* (b) */
  
  temp = 26.5;
  
  p2 = &temp;
  
  *p2 = 29.0;
  
  printf("%.1f \n", temp);
  
  /* (c) */
  
  p3 = &nome[0];
  
  aux = *p3;
  
  printf("%c \n", aux);
  
  /* (d) */
  
  p3 = &nome[4];
  
  aux = *p3;
  
  printf("%c \n", aux);
  
  /* (e) */
  
  p3 = nome;
  
  printf("%c \n", *p3);
  
  /* (f) */
  
  p3 = p3 +;
  
  printf("%c \n", *p3);
  
  /* (g) */
  
  p3--;
  
  printf("%c \n", *p3);
  
  /* (h) */
  
  vetor[0] = 31;
  
  vetor[1] = 45;
  
  vetor[2] = 27;
  
  p4 = vetor;
  
  idade = *p4;
  
  printf("%d \n", idade);
  
  /* (i) */
  
  p5 = p4 +1;
  
  idade = *p5;
  
  printf("%d \n", idade);
  
  /* (j) */
  
  p4 = p5 +1;
  
  idade = *p4;
  
  printf("%d \n", idade);
  
  /* (l) */
  
  p4 = p4 -2;
  
  idade = *p4;
  
  printf("%d \n", idade);
  
  /* (m) */
  
  p5 = &vetor[2] - 1;
  
  printf("%d \n", *p5);
  
  /* (n) */
  
  p5++;
  
  printf("%d \n", *p5);
  
  return(0);
  
}

*Resposta: 

a)

valor = 10; // inteiro

p1 = &valor; // Ponteiro para inteiro

*p1 = 20;

printf("%d \n", valor) // Imprime "20"

b)
temp = 26,5; // float

p2= &temp; // ponteiro para float

*p2 = 29,0;

printf("%.1f \n",temp); // imprime "29.0"

OBS: "%.1f" imprime float com apenas 1 casa decimal depois da vírgula

c)
p3 = &nome[0]; // Armazena o endereço da primeira letra de "nome", ou seja "P".

aux = *p3; // Aux recebe o conteúdo que o ponteiro aponta;

printf("%c \n", aux); // Imprime "P".

d)
p3 = &nome[4]; // aponta para a letra "e" da palavra "Ponteiro" armazenado no Array nome.

aux = *p3; //Aux recebe "e".

printf("%c \n",aux); // Imprime "e".

e)
p3 = nome;// armazena a primeira letra "P"

printf("%c \n",*p3); // Imprime "P".


f)
p3 = p3+4; //p3 = nome [0] -> p3 = nome [0+4] = "e".

printf("%c \n", *p3); //Imprime "e".


g)
p3--; //p3 = nome[4] = "e" -> p3 = nome [4-1] = "t".

printf("%c \n", *p3);// Imprime "t"


h)
vetor[0] = 31;

vetor[1] = 45;

vetor[2] = 27;

p4 = vetor; // recebe o endereço do vetor [0] = 31;

idade = *p4;// "idade" armazena o conteudo que p4 aponta, "31".

printf("%d \n", idade);// Imprime "31".


i)
p5 = p4+1; // o mesmo que p4[0+1] ou p4[1] ou vetor [1], "45".

idade = *p5;

printf("%d \n, idade); // Imprime "45"


j)
p4 = p5+1; // p5+1 = vetor [1+1] = 27

idade = *p4;

printf("%d \n, idade); //Imprime "27".


l)
p4 = p4-2; //vetor [2-2] = vetor[0]= 31

idade = *p4;

printf("%d \n, idade); // Imprime "31"


m) 
p5 = &vetor[2]-1; //vetor [2-1]= vetor[1]= 45

printf("%d \n, *p5); // Imprime "45"


n)
p5++; // vetor[1+1]= vetor [2] = 27

printf("%d \n, *p5); // Imprime "27".

-----------------------------------------------------------------------------------------------------

5. Determine o que será mostrado pelo seguinte programa (compile-o, execute-o e verifique se
foram obtidas as respostas esperadas).

int main(void){

  float vet[5] = {1.1,2.2,3.3,4.4,5.5};
  
  float *f;
  
  int i;
  
  f = vet;
  
  printf("contador/valor/valor/endereco/endereco");
  
  for(i = 0 ; i <= 4 ; i++){
  
  printf("\ni = %d",i);
  
  printf("vet[%d] = %.1f",i, vet[i]);
  
  printf("*(f + %d) = %.1f",i, *(f+i));
  
  printf("&vet[%d] = %X",i, &vet[i]);
  
  printf("(f + %d) = %X",i, f+i);
  
  }
  
}

*Respostas: 

#include <stdio.h>

int main(void) {

float vet[5] = {1.1 , 2.2, 3.3, 4.4, 5.5};

float *f;

int i;

f = vet; // "f" recebe o endereço de vet[0]= 1.1


printf("Contador | valor | valor | Endereco | Endereco");


for( i=0;i<=4; i++) {


printf("\n i = %d",i);

printf("vet[%d] = %.1f", i, vet[i]);

printf("*(f + %d) = %.1f", i, *(f+i));

printf(" &vet[%d] = %x", i, &vet[i]);

printf("(f + %d) = %x", i, f+i);

 }
 
} 


*/// SAÍDA:

 Contador | valor | valor | Endereco | Endereco
 
 i = 0 vet[0] = 1.1 *(f + 0) = 1.1 &vet[0] = ba8d72c0(f + 0) = ba8d72c0
 
 i = 1 vet[1] = 2.2 *(f + 1) = 2.2 &vet[1] = ba8d72c4(f + 1) = ba8d72c4
 
 i = 2 vet[2] = 3.3 *(f + 2) = 3.3 &vet[2] = ba8d72c8(f + 2) = ba8d72c8
 
 i = 3 vet[3] = 4.4 *(f + 3) = 4.4 &vet[3] = ba8d72cc(f + 3) = ba8d72cc
 
 i = 4 vet[4] = 5.5 *(f + 4) = 5.5 &vet[4] = ba8d72d0(f + 4) = ba8d72d0
 

-----------------------------------------------------------------------------------------------------

6. Assumindo que pulo[] é um vetor do tipo int, quais das seguintes expressões referenciam o
valor do terceiro elemento do vetor?

*(pulo + 2);

*(pulo + 4);

pulo + 4;

pulo + 2;

*Resposta:

//pulo [3]:

pulo[0]

pulo[1]

pulo[2] -> Terceiro Elemento

pulo = pulo [0]

*(pulo+2) = pulo [0+2] = pulo[2];

-----------------------------------------------------------------------------------------------------
7. Considerando a declaração int mat[4], *p, x;, quais das seguintes expressões são válidas?
Justifique.

a) p = mat + 1;

b) p = mat++;

c) p = ++mat;

d) x = (*mat)++;

*Respostas:

a) Válido, está armazenando o endereço do segundo elemento do array mat[], ou seja, mat[1];

b) Não é válido, não incrementa ponteiros.

c) Não é válido, não incrementa ponteiros.

d) Válido, incrementa o endereço do inicio do array mat[], nesse caso mat[0+n]

-----------------------------------------------------------------------------------------------------

8. O que fazem os seguintes programas em C?

a)

int main(){

  int vet[] = {4,9,13};
  
  int i;
  
  for(i=0;i<3;i++){
  
  printf("%d ",*(vet+i));
  
  }
  
}

b) 

int main(){

  int vet[] = {4,9,13};
  
  int i;
  
  for(i=0;i<3;i++){
  
  printf("%X ",vet+i);
  
  }
  
}

*Resposta:

a) Programa para imprimir cada valor armazenado no array vet[];

*// SAÍDA: 4 9 13

b) Programa que imprime o endereço de memória de cada valor armazenado no array set[].

*//SAÍDA: e89df2dc e89df2e0 e89df2e4

-----------------------------------------------------------------------------------------------------
9. Seja x um vetor de 4 elementos, declarado da forma TIPO x[4];. Suponha que depois da
declaração, x esteja armazenado no endereço de memória 4092 (ou seja, o endereço de x[0]).
Suponha também que na máquina seja usada uma variável do tipo char ocupa 1 byte, do tipo
int ocupa 2 bytes, do tipo float ocupa 4 bytes e do tipo double ocupa 8 bytes. Quais serão os
valores de x+1, x+2 e x+3 se:

◦ x for declarado como char?

◦ x for declarado como int?

◦ x for declarado como float?

◦ x for declarado como double?

*Resposta:

       | Para X+1 | Para X+2 | Para X+3 |
       
Char   |  4093    |  4094    |  4095    |

Int    |  4094    |  4096    |  4098    |

Float  |  4096    |  409A    |  409E    |

Double |  409A    |  40A2    |  40AA    |

-----------------------------------------------------------------------------------------------------

10. Implemente um programa de computador para testar estas suposições e compare as respostas
oferecidas pelo programa com as respostas que você idealizou.

#include <stdio.h>

int main(){

char x_char[]= "abcd";

int  x_int[4]= {1,2,3,4}, i;

float  x_float[4]= {1.0, 1.1, 1.2, 1.3};

double  x_double[4]= {1.01, 1.02, 1.03, 1.04};

for(i=0; i<4; i++){

	printf("\n para x[%d] \n", i);
  
	printf("\n x_char[%d] = %p", i, &x_char[i]);
  
	printf("\n x_int [%d] = %p", i, &x_int[i]);
  
	printf("\n x_float [%d] = %p", i, &x_float[i]);
  
	printf("\n x_double [%d] = %p\n", i, &x_double[i]);
  
	printf("\n--------------------------------------------------\n");
  
 }
 
}

-----------------------------------------------------------------------------------------------------
11.Suponha que as seguintes declarações tenham sido realizadas:

float aloha[10], coisas[10][5], *pf, value = 2.2;

int i=3;

Identifique quais dos seguintes comandos é válido ou inválido:

aloha[2] = value;

scanf("%f", &aloha);

aloha = value";

printf("%f", aloha);

coisas[4][4] = aloha[3];

coisas[5] = aloha;

pf = value;

pf = aloha;

*Resposta:

a) aloha[2] = value; // Válido

b) scanf("%f", &aloha); // Válido

c) aloha = value"; // Inválido

d) printf("%f",aloha); // Válido

e) coisas [4][4]= aloha [3]; // Válido

g) pf = value; // Inválido

h) pf = aloha; // Válido

-----------------------------------------------------------------------------------------------------

12. O que é um ponteiro para uma função? Pesquise na Internet referências sobre o assunto e
escreva um pequeno programa exemplificando o uso deste recurso.


*Resposta:

Ponteiro para uma função é um ponteiro que armazena o endereço de memória de uma função, assim podemos associar ele a uma função e usar como seu nome dentro do programa.

||Código:||

#include <stdio.h>

int soma(int a, int b){

    return a+b;
    
}

int sub(int a, int b){

    return a-b;
    
}

int main(){

    int x,y,if_soma,if_sub;
    
    char tipo;
    
    int(*p_soma)(int,int);
    
    int(*p_sub)(int,int);
    
    p_soma=soma;
    
    p_sub=sub;
    
    printf("-------------------------CALCULADORA-------------------------\n\n");
    
    printf("Digite qual o tipo de operação na calculadora voce deseja [-,+]: \n");
    
    scanf("%c",&tipo);
    
    printf("\nDigite o primeiro valor [X]: \n");
    
    scanf("%d",&x);
    
    printf("\nDigite o segundo valor [Y]: \n");
    
    scanf("%d",&y);
    
    if(tipo== '+'){
    
        if_soma= p_soma(x,y);
        
        printf("_____________________________________________________\n");
        
        printf("\n%d + %d = %d",x,y,if_soma);
        
    }
    
     if(tipo== '-'){
     
        if_sub= p_sub(x,y);
        
        printf("_____________________________________________________\n");
        
        printf("\n%d - %d = %d",x,y,if_sub);
        
    }
    
}

-----------------------------------------------------------------------------------------------------
13. Implemente em linguagem C uma função em um programa de computador que leia n valores do
tipo float e os apresente em ordem crescente. Utilize alocação dinâmica de memória para
realizar a tarefa.

*Resposta:

||Código||

#include <stdio.h>

#include <stdlib.h>

int main(){

  int i,n,j;
  
  float*x,aux;
  
  printf("Digite o valor de N:");
  
  scanf("\n%d",&n);
  
  x= (float*) malloc( n*sizeof(int));
  
  
  printf("\nDigite os valores que deseja: \n");
  
  for(i=0; i<n; i++){
  
      printf("Digite o %dº valor = ",i+1);
      
      scanf("%f",&x[i]);
      
  }
  
  printf("\n-------------------------------------------------------- \n");
  
  for(i=0; i<n; i++){ 
  
    for(j=i+1;j<n;j++){
    
        if(x[i]<x[j]){
        
            x[i]=x[i];
            
        } else{
        
            aux=x[i];
            
            x[i]=x[j];
            
            x[j]=aux;
            
        }
        
    }
    
    }
    
    for(i=0;i<n;i++){
    
        printf("%0.2f |",x[i]);
        
    }
 free(x);   
}

-----------------------------------------------------------------------------------------------------

14. Reimplemente o programa da questão anterior utilizando a função qsort() do C. Comente o seu
código, explicando o que faz cada uma das linhas.

||CÓDIGO||

#include <stdio.h>

#include <stdlib.h>

int crescente (const void* a, const void* b ){ // vai receber dois valores para comparar
    
    if (*(int*) a == *(int*)b){
        return 0; // se o elemento for igual ao outro, ele vai retornar zero e não vai fazer a alteração da ordem
    }
    
    if (*(int*) a < *(int*)b){
        return -1;// se o elemento a for menor que o b ele vai deixar o elemento a antes do b
    }
    
    if (*(int*) a > *(int*)b){
        return 1;/ / se o elemento b for menor que o a ele vai deixar o elemento b antes do a
    }
    
}

int main(){

  int n,i; //Declarando as variáveis: N para o tamanho do vetor e i para a variável contadora dos For
  
  float*x;// Declarando o Vetor X
  
  printf("Digite o valor de N:");
  
  scanf("\n%d",&n);// Recebendo o tamanho do vetor X
  
  x= (float*) malloc( n*sizeof(int));// Criando o vetor do tamanho desejado
  
  
  printf("\nDigite os valores que deseja: \n");
  
  for(i=0; i<n; i++){ //Colocando valores dentro do vetor
  
      printf("Digite o %dº valor = ",i+1);
      
      scanf("%f",&x[i]);//
      
  }
  
  qsort(x,n,sizeof(float),crescente); // usando a função qsort para ordenar os valores do vetor X; qsort(vetor,tamanho dele, tamanho dos tipos de elementos do vetor, nome da função que compara.
  
  printf("\n-------------------------------------------------------- \n");
  
  for(i=0;i<n;i++){
    
        printf("%0.2f |",x[i]); //Lendo cada valor do vetor depois de ser ordenado
        
    }
    
 free(x);   
}

-----------------------------------------------------------------------------------------------------

15. Utilize a ideia do ponteiro para função pela função qsort() para implementar sua própria função
de ordenação, mas que seja capaz de ordenar apenas inteiros do tipo int. Para isso, sua função
deverá receber, entre outros argumentos, um ponteiro para a função de comparação que
determinará como os elementos do array serão ordenados.

||CÓDIGO||

#include <stdio.h>

#include <stdlib.h>

void crescente(int a, int *b){

int aux;
    
    for(int i=0; i<a; i++){

    for(int j=i+1;j<a;j++){

    if(b[i]<b[j]){
    
        b[i]=b[i];
        
    } else{
    
        aux=b[i];
        
        b[i]=b[j];
        
        b[j]=aux;
        
    }
    
}

}
  
    
}

void decrescente (int a, int *b){

int aux;
    
    for(int i=0; i<a; i++){

    for(int j=i+1;j<a;j++){

    if(b[i]>b[j]){
    
        b[i]=b[i];
        
    } else{
    
        aux=b[i];
        
        b[i]=b[j];
        
        b[j]=aux;
        
    }
    
}

}
  
    
}



int main(){
void(*pf[]) (int, int*)= {crescente,decrescente};

int n,i,o;
int *x;
printf("Digite a quantidade de numeros desejados: \n");

scanf("%d",&n);

printf("\n-------------------------------------------------------- \n");

x = (int*) malloc( n*sizeof(int));

for(i=0; i<n; i++){

  printf("Digite o %dº valor = ",i+1);
  
  scanf("%d",&x[i]);

}

printf("\n-------------------------------------------------------- \n");

printf("Digite qual ordenação você deseja [0 para crescente e 1 para decrescente]: \n");

scanf("%d",&o);

(*pf[o])(n,&x[0]);

printf("\n-------------------RESULTADO----------------------- \n");

for(int i=0;i<n;i++){

    if(i!=n-1){
    printf(" %d |",x[i]);
    } else{
       printf(" %d",x[i]); 
    }
}

free(x);
}








