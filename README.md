# Motion-Cam.
# Objetivo do projeto:
# Transforme seu pc Linux em um ponto de vigilancia.
# Utilzando um celular como camera.
# Gravando em quadros ou em video.
# Cada vez que algo se movimentar em frente da camera.
# Dependencia:
# Instalar make gcc dkms motiom e 
# Linux-heardes.
# Para compilar 0 driver v4l2loopback.

- Baixe o app  Droidcam do Google app.
- Instale no seu celular.
- Execute o app, ele vai colocar o endereço de rede do seu smartfone.
- Mais ou menos assim: 192.168.1.52:4747.
- ![image_1](images/Capture%2B_2019-11-14-20-22-00~3.png)

- No seu pc. Linux baixe o arquivo com comando:
- git clone https://github.com/Ivan-Carlos/Motin-Cam/
- Descompacte o arquivo, na raiz do systema, com o comando:
- cd /
- No lugar a onde estiver arquivo.
- tar xvf motion_cam.tar.gz
- Apos descompactar o arquivo, de o comando.
- cd /usr/src/ com editor, edite o arquivo manual_install.sh com o comando:
- nano manual_install.sh
- Procure a linha NETCAM="value http:\/\/http:\/\/192.168.2.52:4747\/videostream.cgi";
- Ela está no começo do arquivo, edite com numero que apareceu no celular. 
- Salve o arquivo.

- Se voce utilzar a distribuiçao `Ubuntu` talves terá que atualizar o arquivo sources.list
- nano /etc/apt/sources.list, acrecentando a duas seguintes linhas:
- deb http://archive.ubuntu.com/ubuntu/ bionic universe
- deb http://security.ubuntu.com/ubuntu/ bionic-security universe
- Salve o arquivo.
- Voce deverá observar o codename que representa o "sabor" de sua distribuição,
- No caso do exemplo acima o "sabor" é o `bionic`, voce devera substituir para o "sabor" de sua distribuição.
- Feito isto termos que instalar no seu pc linux o seguintes pacote com o comando: 
- apt install gcc linux-headers-`uname -r` motion make dkms. 
- Obs: `uname-r`está entre crazes.
- Copie exatamente como está escrito.
- Apos seguir o ritual aqui descrito, se tudo correr direito,no diretório /usr/src/ daremos o comando:
- ./manual_install.sh
- Para observar sua "camera" em tempo real digite no navegador de intenet http://127.0.0.1:8080/,
- Clicke em cima do quadro para ampliar a imagen. ou edite para  http://127.0.0.1:8081/,
- Para acompanhar o que foi gravado procure no diretório /var/lib/motion/ pelas imagens gravadas.
- Versao automatizada ./install.sh
