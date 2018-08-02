Estesia Pad In
--------------

Projeto baseado no [rhizome](https://github.com/sebpiq/rhizome) e usado no espetáculo estesia+batebit.

Os celulares da plateia se conectam ao computador que está rodando o servidor do rhizome e, ao apertar os botões da interface gráfica, o celular do usuário envia mensagens de controle para o computador. O patch do Max recebe as mensagens de controle e converte para MIDI, que pode controlar disparos de notas em programas de áudio (Ableton Live, GarageBand, Logic etc.).
A plateia funciona como uma grande entrada de dados para o estesia+batebit. O público toca diretamente o som do palco.

Instruções
--------------

- abrir o Terminal e `cd` para este diretório
- começar o servidor rhizome com: `sudo rhizome config.js`
- adiciona-se a senha de administrador
- abrir em um browser: `http://localhost` (se o browser for rodado do mesmo computador que está o rhizome) ou `http://192.168.X.XXX` (se estiver em outro computador da rede: substitua os `X` pelo IP do computador que estiver rodando o rhizome)
- rodar o max com o `osc-trace.maxpat` que faz a conversão de OSC do rhizome para MIDI.

para evitar que o usuário tenha de colocar o número da porta, estamos usando a porta 80 que é a padrão para requisições http.
dessa forma, o usuário precisa apenas digitar `http://localhost` no browser.
se você deseja alterar a configuração de porta, modifique o arquivo `config.js` na pasta do projeto.
lembre-se de modificar tanto para `http` quanto para `websocket`.
para portas que tenham número menor 1024, é preciso ser administrador, por isso deve-se usar o comando `sudo rhizome config.js` para rodar o servidor.
