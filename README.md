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

