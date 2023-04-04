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

