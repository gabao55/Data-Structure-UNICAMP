<h1 align="center">Contatos</h1>

Neste trabalho você deve fazer um programa que mantém uma coleção de
contatos de pessoas.

<p>
Seu programa deve ser capaz de organizar até 1.000 contatos.  Ele deve
inserir, remover e recuperar contatos da coleção.

</p><p>
Cada contato tem nome, endereço, telefone e data de aniversário. O
nome tem até 50 caracteres, o endereço até 100, o telefone até 12
dígitos e a data de aniversário tem o formato dd/mm/aa.

</p><p>
Cada operação sobre a coleção é especificada por um caractere que
indica qual é a operação e é seguido de linhas específicas para a
operação.

</p><p>
As operações podem ser:

</p><ul>
<li>
<b>i</b> para inserção. As quatro linhas seguintes conterão nome,
endereço, telefone e data de aniversário. Depois de inserir o contato
seu programa deve imprimir uma mensagem como exemplificada abaixo.  Se
a coleção já tiver 1.000 contatos então esse novo contato não deve ser
inserido e o programa deve imprimir

<pre>O contato nao foi inserido.
</pre>

em uma linha e mais uma linha em branco.

</li><li>
<b>r</b> para remoção. A linha seguinte tem um nome.  Seu programa
deve remover todos os registros que tenham nome exatamente igual ao
que foi dado. O programa deve imprimir o número de registros
removidos.

</li><li>
<b>b</b> para busca.  A linha seguinte tem um nome.  Seu programa deve
imprimir todos os registros que tenham nome contendo alguma parte que
é igual ao nome digitado, um por linha com campos separados por
tabulação, na ordem em que foram inseridos.  O formato está
exemplificado abaixo.

</li><li>
<b>p</b> para impressão. Seu programa deve imprimir todos os registros
na coleção, um por linha com campos separados por tabulação, na ordem
em que foram inseridos.

</li><li>
<b>f</b> para finalizar o programa.
</li></ul>


<h3>Entrada e saída</h3>

A entrada abaixo contém 11 operações:

<pre>i
Fulano
Rua A, 1 - Centro
11212134512
31/11/31
p
b
Fulana
i
Fulana
Rua B, 2 - Centro
11212134512
01/01/50
p
b
Fulana
r
Fulano
p
r
Fulana
p
f
</pre>

A saída esperada é

<pre>Contato para Fulano inserido.

Listagem:
(1) Fulano	Rua A, 1 - Centro	11212134512	31/11/31

Resultado da busca:
Nenhum contato.

Contato para Fulana inserido.

Listagem:
(1) Fulano	Rua A, 1 - Centro	11212134512	31/11/31
(2) Fulana	Rua B, 2 - Centro	11212134512	01/01/50

Resultado da busca:
(2) Fulana	Rua B, 2 - Centro	11212134512	01/01/50

Contatos de Fulano removidos: 1.

Listagem:
(1) Fulana	Rua B, 2 - Centro	11212134512	01/01/50

Contatos de Fulana removidos: 1.

Listagem:
Nenhum contato.

</pre>

e tem uma linha no final.



<h4>Outro exemplo</h4>

<p>
<b>Entrada:</b>

</p><p>
</p><pre>i
O primeiro Fulano
Rua A, 1 - Centro
11212134512
31/11/31
i
Nao eh...
Rua B, 1 - Centro
11212134512
31/11/31
i
Mais um Fulanozinho.
Rua C, 1 - Centro
11212134512
31/11/31
i
Fulano
Rua A, 1 - Centro
11212134512
31/11/31
i
Ainda outro Fulanozinho.
Rua C, 1 - Centro
11212134512
31/11/31
i
umFulanozinho.
Rua C, 1 - Centro
11212134512
31/11/31
i
Fulanozinho de Tal.
Rua C, 1 - Centro
11212134512
31/11/31
b
Fulano
r 
Fulano
p
f
</pre>

<p>
<b>Saída:</b>
  
</p><pre>Contato para O primeiro Fulano inserido.

Contato para Nao eh... inserido.

Contato para Mais um Fulanozinho. inserido.

Contato para Fulano inserido.

Contato para Ainda outro Fulanozinho. inserido.

Contato para umFulanozinho. inserido.

Contato para Fulanozinho de Tal. inserido.

Resultado da busca:
(1) O primeiro Fulano	Rua A, 1 - Centro	11212134512	31/11/31
(3) Mais um Fulanozinho.	Rua C, 1 - Centro	11212134512	31/11/31
(4) Fulano	Rua A, 1 - Centro	11212134512	31/11/31
(5) Ainda outro Fulanozinho.	Rua C, 1 - Centro	11212134512	31/11/31
(6) umFulanozinho.	Rua C, 1 - Centro	11212134512	31/11/31
(7) Fulanozinho de Tal.	Rua C, 1 - Centro	11212134512	31/11/31

Contatos de Fulano removidos: 1.

Listagem:
(1) O primeiro Fulano	Rua A, 1 - Centro	11212134512	31/11/31
(2) Nao eh...	Rua B, 1 - Centro	11212134512	31/11/31
(3) Mais um Fulanozinho.	Rua C, 1 - Centro	11212134512	31/11/31
(4) Ainda outro Fulanozinho.	Rua C, 1 - Centro	11212134512	31/11/31
(5) umFulanozinho.	Rua C, 1 - Centro	11212134512	31/11/31
(6) Fulanozinho de Tal.	Rua C, 1 - Centro	11212134512	31/11/31

</pre>



<h3>Requisitos adicionais</h3>
<ul>
  <li> Seu programa deve usar um vetor de <tt>struct</tt> para
  armazenar os contatos.
  </li><li> Cada funcionalidade (inserir, buscar, remover, imprimir) deve
  ser implementada por uma função distinta.
  </li><li> Não deve haver variáveis globais, isto é, nenhuma variável pode
  ser definida fora de alguma função.
</li></ul>


<h3>Sugestões</h3>

<ul>
<li>
Observe que não há necessidade de armazenar a lista de operações.
Basta realizar a operação logo que ela for lida na entrada.
</li><li>
Comece fazendo um programa que apenas lê a entrada, identifica as
operações e imprime os dados.  Depois adicione as funções que realizam
as operações.
</li></ul>


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

<pre>"Ninety-percent of everything is CRUD".
</pre>
<hr></form></div></div>

</body></html>
