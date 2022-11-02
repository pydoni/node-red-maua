node-red-maua

</h1>Propósito</h1>

Essa documentação tem como intuito ser uma documentação aberta para o ensino da ferramenta Node-Red.

<hr>
<h1>Sumario</h1>

<ol>
<li><a href="">Introdução ao Node-Red</a></li>
  
<li><a href="">Aprofundando nos nodos</a><ol>
<li><a href="">Inject</a></li>
<li><a href="">Cron-Plus</a></li>
<li><a href="">Exec-Queue</a></li>
<li><a href="">Debug</a></li>
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
<td>Inject</td>
<td>Realiza uma injeção no nodo seguinte ativando ele.</td>
</tr>
<tr>
<td>Cron Plus</td>
<td>Injeta os nodos conectados de acordo com um temporizador interno, podendo programar para realizar a cada hora, uma vez por semana, cinco vezes ao dia, ou outras repetições de tempo.</td>
</tr>
<tr>
<td>Exec-Queue</td>
<td>Permite a compilação e execução de códigos em diversas linguagens no fluxo. Podendo manipular payloads e realizar operações em formato de fila a medida que payloads chegam ao nodo. Alêm disso traz dentro de si uma interface que se aproxima a uma ide, para o desenvolvimento de códigos.</td>
</tr>
<tr>
<td>Debug</td>
<td>Exibe no terminal do Node-RED, o conteúdo do payload que chegar nele.</td>
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
<p>O Node-RED é uma ferramenta web que permite conectar hardwares, softwares, APIs e serviços onlines de forma organizada e conectada. Ele é baseado em Node.Js e extremamente leve, com um ambiente altamente customizavel e com uma comunidade aberta que desenvolve constantemente modulos para ele. </p>
<p>O ambiente base dele é feito para trabalhar em equipe com um controle de versão embutido que entrega tudo que o git entrega. Com ele é possível gerar fluxos de automatização de códigos, desenvolver APIs, controlar dispositivos eletrônicos e muito mais. Tudo isso através de nodos que representam blocos que realizam ações diversas como rodar um código, ativar algo em um tempo determinado ou ativar um nodo em determinada condição.</p>
<p>Os nodos são utilizados para montar fluxos que se comunicam através de mensagens, chamadas payloads, os nodos podem gerar esses payloads e eles são ativado na maioria dos casos quando recebem um payload. O payload por sua vez é um objeto JSON que pode carregar qualquer coisa que você programar, com os seus argumentos sendo chamados de topic dentro do Node-RED, o payload também pode ser uma string simples se não for dado argumentos a ele.</p>
<p>Uma aplicação base do Node-RED seria para a automatização de um fluxo de manipulação de dados que ocorre todo dia em determinada hora. Para a realização desse fluxo primeiro teriamos um nodo do tipo Cron-Plus que pode ser programado para realizar injeções de payload em determinada hora, após ele realizar a injeção ele ativa um nodo do tipo Exec-Queue, que executa um código que o desenvolvedor colocou dentro dele, após o termino esse nodo envia um payload para o próximo nodo que é um nodo de debug, que apresenta no terminal do Node-RED o conteúdo desse payload que indica o termino do fluxo.</p>

<b>Como instalar o Node-RED</b>
<p>
</p>


<br><hr><br>
<h1>2.Aprofundando nos nodos</h1>

<h2>Inject</h2>
<img width=300 src="https://nodered.org/docs/user-guide/images/node_inject.png">
<p> Esse nodo permite que você execute manualmente a ativação de um fluxo a qual esse nodo está conectado, é possível também configurar um payload dentro dele, que será repassado para o próximo nodo.</p>
<p><b>Exemplo de aplicação:</b>
Imagine que você tem um fluxo de códigos que é não tem necessidade de ser ativado com alguma frequência, você pode utilizar esse nodo para ativar ele assim que for necessário.

<b>Instalação</b>
<ul>
<li>Nodo base, não necessita de instalação </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://nodered.org/docs/user-guide/nodes#inject </li>
</ul>

</p>
<br><hr>
<h2>Cron-plus</h2>
<img width=300 src="https://i.imgur.com/sLZKhYh.jpg">
<p>O Cron-Plus é um nodo da comunidade, baseado no comando cron do linux, que é conhecido por ser uma ferramenta de agendamento de processos, o qual você pode utilizar para ativar processos de forma recorrente em intervalos de tempo especifico. Essa configuração pode ser realizada de duas formas diferentes, a primeira é própria do Cron-Plus e é chamada de Easy Expression Builder, sendo uma interface gráfica que te auxilia a definir o tempo em que o Cron-Plus seguira, a segunda é uma sintaxe própria do cron que em poucos caracteres consegue definir qualquer intervalo de tempo, por ser mais complexa requer um estudo aprofundado no comando original que deu luz a esse nodo.</p>

<p><b>Exemplo de aplicação:</b>
Imagine que você tem um fluxo que precise rodar a cada três horas ou toda segunda-feira às uma da manhã, o Cron-Plus pode ser programado para dar partida nesse fluxo no tempo determinado.
</p>
<b>Instalação</b>

<ul>
<li>Via terminal: npm install node-red-contrib-cron-plus </li>
<li>Via Manage Palette, pesquisar node-red-contrib-cron-plus e instalar </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://flows.nodered.org/node/node-red-contrib-cron-plus </li>
<li>Entendendo o comando Cron: https://rockcontent.com/br/blog/cron/ </li>
<li>Para a criação de crons via sintaxe: https://crontab.guru/ </li>
</ul>

<br><hr>
<h2>Exec-Queue</h2>
<img width=300 src="https://i.imgur.com/h6PzDci.jpg">
<p></p>

<p><b>Exemplo de aplicação:</b>

</p>
<b>Instalação</b>

<ul>
<li>Via terminal: npm install node-red-contrib-exec-queue </li>
<li>Via Manage Palette, pesquisar node-red-contrib-exec-queue e instalar </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://flows.nodered.org/node/node-red-contrib-exec-queue </li>
</ul>
<br><hr>
<h2>Debug</h2>
<img width=300 src="https://nodered.org/docs/user-guide/images/node_debug.png">
<p> Com o nodo de Debug você consegue monitorar o conteúdo de um payload, sendo útil para monitorar o funcionamento de nodos e verificar se o payload está sendo passada da forma apropriada.</p>
<p><b>Exemplo de aplicação:</b>
Em um fluxo quando você precisa de verificar que ele chegou até o final corretamente, você pode utilizar o debug para monitorar a saída do ultimo nodo do fluxo em questão, pois caso ocorra algum problema no caminho o nodo final nunca terá uma saída.

<b>Instalação</b>
<ul>
<li>Nodo base, não necessita de instalação </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://nodered.org/docs/user-guide/nodes#debug </li>
</ul>

</p>

<br><hr>
<h2>Catch</h2>
<img width=300 src="https://i.imgur.com/07fMHbP.jpg">
<p> O nodo de Catch funciona como a lógica try catch de programação, ele fica observando um ou mais nodos e quando ocorre um erro em um ou mais nodos que ele tenha sido configurado para observar, ele ira realizar uma injeção com payload de erro em um outro nodo.</p>
<p><b>Exemplo de aplicação:</b>
Você tem um fluxo que se falhar você precisa reverter algumas coisas, então coloca um nodo de catch observando o nodo que pdoe falhar, se a falhar ocorrer ele realiza uma injeção em um outro nodo que é responsável por reverter o que é necessário.

<b>Instalação</b>
<ul>
<li>Nodo base, não necessita de instalação </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://nodered.org/docs/user-guide/handling-errors </li>
</ul>

</p>
<br><hr>
<h2>Switch</h2>
<img width=300 src="https://nodered.org/docs/user-guide/images/node_switch.png">
<p> O nodo de Switch funciona como o tradicional Switch lógico, dentro dele você pode realizar diversas comparações com o conteúdo do payload que ele recebe, e com base nessas comparações redirecionar o payload para um nodo especifico.</p>
<p><b>Exemplo de aplicação:</b>
Um payload contém o nome de um arquivo, você precisa checar o tipo do arquivo então o switch analisa o payload e verifica se dentro do nome do arquivo existe a string ".jpg" se existir você envia o payload para um outro nodo responsável por tratar payloads que do tipo jpg, já se existir a string ".txt" ele redireciona o payload para um nodo que irá tratar os arquivos do tipo txt.

<b>Instalação</b>
<ul>
<li>Nodo base, não necessita de instalação </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://nodered.org/docs/user-guide/nodes#switch </li>
</ul>

</p>
<br><hr>
<h2>Range</h2>
<img width=300 src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSBp4grwypxRmw9zIdNuIa-X5oD_C49BLtaGQ&usqp=CAU">
<p> O nodo de Range realiza um mapeamento no conteúdo do payload convertendo o domínio de seu conteúdo.</p>
<p><b>Exemplo de aplicação:</b>
Imagine que um payload contenha o valor 30, e seu valor pode variar na origem de 0 a 100, porém você quer converter ele para um domínio onde o seu valor só pode variar entre 20 a 80, o nodo de range realiza a transformação do valor para o novo domínio resultando em 38.

<b>Instalação</b>
<ul>
<li>Nodo base, não necessita de instalação </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: http://noderedguide.com/node-red-lecture-3-example-3-5-scaling-input-with-the-range-node/#more-1928 </li>
</ul>

</p>
<br><hr>
<h2>Change</h2>
<img width=300 src="https://nodered.org/docs/user-guide/images/node_change.png">
<p> O nodo de change tem um funcionamento simples, nele você pode configurar para ele alterar, adicionarou remover, qualquer conteúdo que exista dentro do payload</p>
<p><b>Exemplo de aplicação:</b>
Um payload pode conter um topic que você queira remover sem alterar os outros, então o nodo de Change entra em ação realizando a alteração do payload quando ele tiver esse topic extra.

<b>Instalação</b>
<ul>
<li>Nodo base, não necessita de instalação </li>
</ul>

<b>Links Auxiliares</b>
<ul>
<li>Documentação do nodo: https://nodered.org/docs/user-guide/nodes#change </li>
</ul>

</p>
