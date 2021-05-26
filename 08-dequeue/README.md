
<h1 : align="center">Sequência circular em vetor dinâmico</h1>

Vamos dizer que um conjunto de dados forma uma <i>seqüência</i> se
eles são consecutivos e se a ordem relativa entre eles é importante.
Estar em seqüência não quer dizer que seja ordenado.  Quer dizer
apenas que existe o primeiro, o segundo, o terceiro etc. mas não quer
dizer que o primeiro é menor que o segundo, que o segundo é menor que
o terceiro etc.

<p>
Uma forma de armazenar uma seqüência é colocá-la consecutivamente em
um vetor de forma "circular", isto é, o primeiro elemento da seqüência
pode estar em qualquer posição.

</p><p>
Por exemplo, se a seqüência de inteiros [2,9,5,7] estiver armazenada
de forma circular em um vetor de tamanho 8, ela pode estar em uma
das configurações abaixo:

</p><pre>2 9 5 7 _ _ _ _
_ 2 9 5 7 _ _ _ 
_ _ 2 9 5 7 _ _
_ _ _ 2 9 5 7 _
_ _ _ _ 2 9 5 7
7 _ _ _ _ 2 9 5
5 7 _ _ _ _ 2 9 
9 5 7 _ _ _ _ 2 
</pre>

Em todas elas, o primeiro elemento da seqüência é o 2 e o último é o
7, mas a posição dos elementos dentro do vetor é diferente.  Nas
configurações, o sublinhado representa inteiros que fazem parte do
vetor mas não fazem parte da seqüência.

<p> Se um vetor de tamanho 8 contém a seqüência circular [2,9,5,7] na
configuração

</p><pre>2 9 5 7 _ _ _ _
</pre>

e o número 6 é adicionado ao início da seqüência, então o vetor fica
assim:

<pre>2 9 5 7 _ _ _ 6
</pre>

Depois se o número 8 é adicionado ao início da seqüência, o vetor deve
ficar assim:

<pre>2 9 5 7 _ _ 8 6
</pre>

Se o número 7 é removido do fim da seqüência, o vetor deve ficar assim:

<pre>2 9 5 _ _ _ 8 6
</pre>

E se o número 1 é adicionado ao fim da seqüência, o vetor deve ficar assim:

<pre>2 9 5 1 _ _ 8 6
</pre>


<p>
Se soubermos quais são os índices do início e do fim da seqüência (ou
equivalentemente soubermos o início e o tamanho da seqüência) então as
operações de inserção e remoção nas extremidades da seqüência podem
ser realizadas facilmente.

</p><p>
Neste trabalho você deve implementar funções para manipular uma
seqüência de strings, que devem permitir recuperar a primeira e o
última strings, inserir no início e no final da seqüência e remover a
primeira e a última strings.  As strings na seqüência podem ter
tamanhos variados, podendo ser vazias inclusive.

</p><p>
A seqüência deve estar armazenada de forma circular em um vetor
alocado dinamicamente.  O vetor deve ser redimensionado e aumentar
quando estiver cheio.  Ele deve diminuir quando estiver com muitas posições
não-ocupadas por elementos da seqüência.

</p><p>
O vetor deve começar com tamanho 64.  A política de redimensionamento
do vetor deve ser dobrar quando estiver cheio e reduzir à metade
quando estiver 1/4 ocupado.  O vetor nunca deve ficar com menos que 64
elementos. Dessa forma, durante o processamento, o número de posições
vazias do vetor não deveria exceder 3n, onde n é o número de posições
ocupadas pelos elementos da seqüência. Antes de terminar o programa
deve liberar a memória ocupada pelo vetor alocado dinamicamente.



</p><h3>Entrada</h3> 

A entrada é composta por uma sucessão de comandos, um por linha.  Os
possíveis comandos estão descritos abaixo.  

<ul>

<li>
<pre>inject string
</pre>

<p>
Insere uma string no início da seqüência.  A string é formada pelos
caracteres depois de "inject " e antes do fim-de-linha. A string pode
ser vazia.


</p></li><li>
<pre>eject
</pre>

<p>
Remove a string no início da seqüência.  Se a seqüência estiver
vazia, não faz nada.


</p></li><li>
<pre>push string
</pre>

<p>
Insere uma string no fim da seqüência. A string é formada pelos
caracteres depois de "push " e antes do fim-de-linha, descartando os
espaços no início e no fim-de-linha.  A string pode ser vazia.


</p></li><li>
<pre>pop
</pre>

<p>
Remove a string no fim da seqüência. Se a seqüência estiver vazia, não
faz nada.



</p></li><li>
<pre>print-first
</pre>

<p>
Imprime a string no início da seqüência.  Se a seqüência estiver
vazia, não faz nada.


</p></li><li>
<pre>print-last
</pre>

<p>
Imprime a string no fim da seqüência.  Se a seqüência estiver vazia,
não faz nada.



</p></li><li>
<pre>is-empty
</pre>

<p>
Imprime -yep se a seqüência estiver vazia e -nope se não estiver.


</p></li><li>
<pre>exit
</pre>

<p>
Termina o programa.  
</p></li></ul>


<h3>Saída</h3>

A saída deve conter as linhas geradas pelos comandos print-first e
print-last.



<h3>Exemplo</h3>

<p>
Entrada:
</p><pre>is-empty
pop
print-last
push Mas um dia
push desses   
push eu vou fugir de casa e
push   nao
push volto
is-empty
print-first
print-last
is-empty
eject
pop
pop
print-first
print-last
is-empty
pop
pop
eject
eject
is-empty
exit

</pre>

Saída:
<pre>-yep
-nope
Mas um dia
volto
-nope
desses   
eu vou fugir de casa e
-nope
-yep
</pre>



<h3>Outro exemplo</h3>

<p>
Entrada:
</p><pre>push    ... No fim tu hás de ver que as coisas mais leves são as
push    únicas que o vento não conseguiu levar ...
is-empty
print-last
print-first          
push um dia desses choverá   
is-empty
print-last
print-first
push    Talvez amanhã ou talvez num amanhã, mas choverá!   
is-empty
print-last
print-first
is-empty
exit
</pre>

Saída:
<pre>-nope
   únicas que o vento não conseguiu levar ...
   ... No fim tu hás de ver que as coisas mais leves são as
-nope
um dia desses choverá   
   ... No fim tu hás de ver que as coisas mais leves são as
-nope
   Talvez amanhã ou talvez num amanhã, mas choverá!   
   ... No fim tu hás de ver que as coisas mais leves são as
-nope
</pre>


<h3>Envio</h3>

O programa deve ser composto por um arquivo main.c e por um par de
arquivos darray.h e darray.c.  O darray.h tem as definições do array e
das funções que manipulam o array.  O darray.c deve ter as definições
das funções.

<p>
Você deve enviar ao sqtpm apenas o arquivo darray.c que você
implementar.  Os arquivos main.c e darray.h estão prontos e listados
abaixo.  O darray.h descreve o comportamento esperado das funções.
Eles serão usados automaticamente pelo sqtpm nesta forma.

</p><p>
Antes de sair programando o seu darray.c, use alguns minutos para
entender o main.c e o darray.h.

</p><p>
Para compilar o programa no seu computador, compile primeiro o darray.c:

</p><pre>gcc -c darray.c
</pre>

Depois compile tudo junto:

<pre>gcc main.c darray.o -o darray
</pre>

Se você usa um IDE, vai precisar criar um projeto e incluir os três arquivos.


<h3>Nota</h3>
Essa estrutura de dados seqüência com as operações push(), pop(),
inject() e eject() também é chamada de double ended queue ou deque.



<h3>Sobre organização do código e comentários</h3>

<ul>
<li>
Faça um programa organizado, bem indentado e que seja fácil de ler.
</li><li>
Adicione comentários que vão ser úteis para entender o programa se
você for relê-lo daqui a alguns anos: comentar cada linha vai ser
redundante; documentar blocos de código e a estratégia usada na
solução vai ser muito útil.
</li></ul>


  
<hr>
<h3>darray.h</h3>
<pre>/**
  darray.h
  Declarations for a sequence of strings stored in an array that swells and
  shrinks by a factor of 2 as needed.
**/


#ifndef DARRAY_H
#define DARRAY_H


typedef struct darray {

  char** data; // The array of pointers to char, that is, the array of string.

  int first; // The index of the first element in the sequence.
  int size;  // The sequence size.

  int capacity; // The array size.
  int min_cap;  // The minimum array size.

} darray;



/**
   Allocate a darray and the array of pointers to strings with
   initial capacity.  Set the initial state of the darray properly.

   capacity is the initial array size.  It is also the minimum array size.

   It returns the address of a new darray.  On failure it returns NULL.
**/
darray* da_alloc(int capacity);



/**
  Release all the strings in a darray and the darray itself.
**/
void da_free(darray* A);



/**
   Add a copy of a string to the end of the sequence.

   If the array is full, it tries to double its capacity and then adds the
   string.

   On success it returns 1.  When resizing the array is not possible it will not
   push and will return 0.
**/
int da_push(darray* A, char* string);



/**
   Remove a string from the end of the sequence and return a pointer to it.

   If the array is 1/4 full, this function halves its capacity and then removes
   the string.  The capacity will never be smaller than the initial capacity.
**/
char* da_pop(darray* A);



/**
   Add a copy of a string to the beginning of the sequence.

   If the array is full, it tries to double its capacity and then adds the
   string.

   On success it returns 1.  When resizing the array is not possible it will not
   inject and will return 0.
**/
int da_inject(darray* A, char* string);



/**
   Remove a string from the beginning of the sequence and return a pointer to it.

   If the array is 1/4 full, this function halves its capacity and then removes
   the string.  The capacity will never be smaller than the initial capacity.
**/
char* da_eject(darray* A);



/**
   Return a pointer to the first string in the sequence.
**/
char* da_first(darray* A);



/**
   Return a pointer to the last string in the sequence.
**/
char* da_last(darray* A);



/**
   Return 1 if the sequence is empty, otherwise return 0.
**/
int da_is_empty(darray* A);


#endif
</pre>
<hr>

<h3>main.c</h3>

<pre>#include &lt;stdlib.h&gt;
#include &lt;stdio.h&gt;
#include &lt;errno.h&gt;
#include &lt;string.h&gt;
#include "darray.h"


ssize_t getdelim(char **linep, size_t *n, int delim, FILE *fp) {
  int ch;
  size_t i = 0;
  if (!linep || !n || !fp) {
    errno = EINVAL;
    return -1;
  }
  if (*linep == NULL) {
    if (NULL == (*linep = malloc(*n = 128))) {
      *n = 0;
      errno = ENOMEM;
      return -1;
    }
  }
  while ((ch = fgetc(fp)) != EOF) {
    if (i + 1 &gt;= *n) {
      char *temp = realloc(*linep, *n + 128);
      if (!temp) {
        errno = ENOMEM;
        return -1;
      }
      *n += 128;
      *linep = temp;
    }
    (*linep)[i++] = ch;
    if (ch == delim)
      break;
  }
  (*linep)[i] = '\0';
  return !i &amp;&amp; ch == EOF ? -1 : i;
}


ssize_t getline(char **linep, size_t *n, FILE *fp) {
  return getdelim(linep, n, '\n', fp);
}


int main(void) {

  char cmd[10];
  char* line = NULL;
  size_t len = 0;
  ssize_t read;

  darray* D = da_alloc(64);
  if (!D) {
    printf("Unable to allocate D.\n");
    exit(1);
  }

  while (1) {
    scanf("%s%*c",cmd);

    if (strcmp(cmd,"push") == 0) {
      read = getline(&amp;line, &amp;len, stdin);
      if (read == -1) {
        perror("getline at push");
        exit(errno);
      }
      line[read-1] = '\0';

      int st = da_push(D,line);
      if (!st) {
        printf("Unable to resize at push.\n");
        exit(1);
      }
    }

    else if (strcmp(cmd,"pop") == 0) {
      if (!da_is_empty(D)) {
        char* str = da_pop(D);
        free(str);
      }
    }

    else if (strcmp(cmd,"inject") == 0) {
      read = getline(&amp;line, &amp;len, stdin);
      if (read == -1) {
        perror("read at inject");
        exit(errno);
      }
      line[read-1] = '\0';

      int st = da_inject(D,line);
      if (!st) {
        printf("Unable to resize at inject.\n");
        exit(1);
      }
    }

    else if (strcmp(cmd,"eject") == 0) {
      if (!da_is_empty(D)) {
        char* str = da_eject(D);
        free(str);
      }
    }

    else if (strcmp(cmd,"print-first") == 0) {
      if (!da_is_empty(D))
        printf("%s\n",da_first(D));
    }

    else if (strcmp(cmd,"print-last") == 0) {
      if (!da_is_empty(D))
        printf("%s\n",da_last(D));
    }

    else if (strcmp(cmd,"is-empty") == 0) {
      if (da_is_empty(D))
        printf("-yep\n");
      else
        printf("-nope\n");
    }

    else if (strcmp(cmd,"exit") == 0) {
      da_free(D);
      free(line);
      return 0;
    }

    else {
      printf("Ups, invalid command %s\n",cmd);
      exit(1);
    }
  }

  return 0;
}

</pre>
<hr>

<p>
Não se esqueça do princípio KISS!

</p><hr></form></div></div>

</body></html>
