node-red-maua

</h1>Propósito</h1>

Essa documentação tem como intuito ser uma documentação aberta para o ensino da ferramenta Node-Red.

<hr>
<h1>Sumario</h1>

<ol>
<li><a href="">Introdução ao Node-Red</a></li>
  
<li><a href="">Aprofundando nos nodos</a><ol>
<li><a href="">Exec-Queue</a></li>
<li><a href="">Cron-Plus</a></li>
<li><a href="">Catch</a></li>
<li><a href="">Switch</a></li>
<li><a href="">Range</a></li>
<li><a href="">Change</a></li></ol>
  </li>
</ol>

<br><hr><br>

<h1>Tabela de nodos</h1>

<center>
<table>
<tr>
<td>Exec-Queue</td>
<td>Permite a compilação e execução de códigos em diversas linguagens no fluxo. Podendo manipular payloads e realizar operações em formato de fila a medida que payloads chegam ao nodo. Alêm disso traz dentro de si uma interface que se aproxima a uma ide, para o desenvolvimento de códigos.</td>
</tr>
<tr>
<td>Cron Plus</td>
<td>Injeta os nodos conectados de acordo com um temporizador interno, podendo programar para realizar a cada hora, uma vez por semana, cinco vezes ao dia, ou outras repetições de tempo.</td>
</tr>
<tr>
<td>Inotify</td>
<td>Observa o estado dos arquivos de uma pasta especifica e para cada vez que ocorre uma mudança especificada na pasta sobre um arquivo ele gera um payload com o nome do arquivo, com essas mudanças podendo ser criação, edição, remoção e outras coisas que ocrrem em um arquivo.</td>
</tr>
<tr>
<td>Catch</td>
<td>Esse nodo fica observando o compartamento de outro(s) nodo(s), e em casa de falha do tipo error no(s) nodo(s) observado(s), ele capta esse erro e realiza a injeção em um nodo que você conecte nele.</td>
</tr>
<tr>
<td>Switch</td>
<td>Direciona o payload para um nodo especifico de acordo com as propriedades ou conteudo do payload.</td>
</tr>
<tr>
<td>Range</td>
<td>Esse nodo mapeia um valor númerico para um domínio de valores diferente.</td>
</tr>
<tr>
<td>Change</td>
<td>Realiza a edição das propriedades ou conteúdo de um payload.</td>
</tr>

</table>
</center>

<br><hr><br>

<h1>1.Introdução ao Node-red</h1>
<p></p>

<br><hr><br>
<h1> Aprofundando nos nodos</h1>
<h2>Exec-Queue</h2>
<p>PAra a instalação desse nodo<p>
