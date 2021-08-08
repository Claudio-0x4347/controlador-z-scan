# controlador-z-scan

## Motivações
O controlador-z-scan foi meu primeiro projeto utilizando a plataforma de desenvolvimento Labview e nasceu de uma proposta de projeto de iniciação científica para o Laboratório de Biofotônica do Instituto de Física da Universidade Federal de Goiás, orientado pelo Dr. Pablo José Gonçalves. No projeto foi feito a automação da técnica z-scan utilizando o instrumento virtual (VI) para coordenar a comunicação com o osciloscópio, responsável pela aqui aquisição dos dados, e um arduino nano, responsável por coordenar a movimentação da amostra em estudo ao longo do eixo de propagação do feixe laser (eixo-z).

## Descrição da técnica 
A técnica de Varredura-Z (Z-Scan) é uma poderosa técnica de óptica não-linear que consiste na transladação de uma amostra ao longo de um eixo de propagação de um feixe laser Gaussiano focalizado, enquanto se monitora a transmitância normalizada do feixe laser em função da posição. O processo de focalização do feixe produz um perfil de intensidade variável ao longo da direção de propagação (eixo-Z). Ao interagir com a amostra o feixe passa por mudanças em sua frente de onda devido aos processos de autofocalização e autodesfocalização que provocam variações na intensidade da Luz (Efeito Kerr Óptico). Para a absorção, que foi o nosso caso, é acrescido uma lente previamente ao detector, permitindo a coleta de toda a luz e excluindo a variação da intensidade. Dessa maneira, a variação da transmitância ocorre devido aos efeitos de absorção de estados excitados que podem resultar na absorção saturada ou absorção saturada reversa.

## Requisitos para operação
Para execução do projeto é necessário:
<ul>
  <li><a href="">Kit de desenvolvimento Labview</a></li>
  <li><a href="http://sine.ni.com/apps/utf8/niid_web_display.download_page?p_id_guid=6E23DB10D9FC2B05E04400144FB7D21D">Driver DPO MSO 2000 4000 series</a></li>
  <li>Pacote Labview Interface for Arduino</li>
  <li><a href="https://store.arduino.cc/usa/arduino-nano">Arduino Nano</a></li>
  <li><a href="https://www.sparkfun.com/products/12779">Módulo de interface com o motor de passo EasyDriver </a></li>
  <li>Osciloscópio Tektronix DPO 3052</li>
</ul>
A estrutura utlizada para movimentar a amostra foi desenvolvida pelo Engenheiro Arthur Henrique Floriano Pereira e já possui acoplado a ela o motor de passo utilizado.

## Montagem
![0120-6230-rfiua-86-00027-gf2](https://user-images.githubusercontent.com/60492503/128636901-1e5c5a17-4514-4283-8043-3b1367b660aa.jpg)
![WhatsApp Image 2021-08-08 at 12 13 41](https://user-images.githubusercontent.com/60492503/128636934-d000ffde-5587-4c19-8d98-3b4bef962484.jpeg)


## Operação
<ol>
  <li>Conectar o Arduino ao computador.</li>
  <li>Com o Arduino conectado, na interface do VI definir a porta em que ele foi iniciado no sistema operacional.</li>
  <li>Conectar o Osciloscópio ao computador.</li>
  <li>Com o osciloscópio conectado, definir a porta em que ele foi iniciado no sistema operacional, o canal onde a aquisição dos dados será feito, e a medida de interesse que se deseja coletar (olhar manual caso dúvida).</li>
  <li>Inicializar o VI na seta branca no canto superior esquerdo.</li>
  <li>Com a ajuda das setas do teclado, posicionar a amostra no foco do feixe laser.</li>
  <li>Definir a unidade de medida utilizada pelo software (cm ou mm).</li>
  <li>Definir a distância máxima percorrida pela amostra a direita e esquerdad do foco (Distânica Percorrida).</li>
  <li>Definir a distância entre as posições de medidas no eixo-z (Distância entre medidas).</li>
  <li>Definir a quantidade de medidas (Número de medidas) feito para obtenção da média em cada posição.</li>
  <li>Com tudo definido, clicar em Iniciar no canto inferior direito.</li>
  <li>Esperar o sistema coletar os dados.</li>
  <li>Ao final da coleta será solicitado para o usuário o local onde se deseja salvar os dados. Os dados são salvos no formato em um arquivo de texto delimitado por tabulação.</li>
  <li>Encerre a execução clicando em Sair no canto inferior direito, para que a comunicação com os periféricos encerre de forma correta.</li>
</ol>
