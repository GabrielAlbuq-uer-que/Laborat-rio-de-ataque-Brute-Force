# Laboratório de ataque Brute Force:
Ataque realizado em laboratório de máquina virtual, visando o melhor aprendizado do método de intrusão e invasão com a técnica brute force, utilizando a ferramenta Medusa.
# Parte 1: Escaneamento de portas #
 - Para realizar o scam das portas utilizei o comando Nmap, com a sintaxe
 -     nmap -Sn 192.168.12.0/24(ip de variação de cada rede)
   <img width="1915" height="777" alt="SCAN NMAP" src="https://github.com/user-attachments/assets/075723eb-a17a-4989-a2f6-d1abe45cd1d8" />
   Após encontrarmos o alvo em destino verifico a necessidade de verificar se está ligado.

# Parte 2: Verificando Atividade da máquina
 - Para Verificar a atividade da máquina, ligado ou desligado, utilizo do comando ping, para enviar pacotes, assim, conseguindo verificar que a máquina está ativa. Sintaxe utilizada:
 -      ping 192.168.12.20 (ip da máquina alvo)
   <img width="1917" height="930" alt="PING NA MAQUINA" src="https://github.com/user-attachments/assets/ef6a39f8-53b8-4be2-9ef3-5717226565be" />
   Agora, tentaremos utilizar uma lista de usuários e senhas para testar a intrusão na máquina com o Comando Medusa no Kali.

# Parte 3: Criando usuários e senhas para teste
 - Para criar as listas de usuários utilizamos o bloco de notas e salvamos os arquivos com o **.txt** no final.
   <img width="1908" height="923" alt="SENHAS E USUARIOS PARA TESTE" src="https://github.com/user-attachments/assets/c37c1c5e-419c-4683-8e04-0db06f4918ca" />

# Parte 4: Testes de intrusão
 - Agora iremos utilizar a ferramenta Medusa, utilizada para testes de brute force, com listas de usuários e senhas.
    ## Parte 4.1: Utilizando listas com o Medusa
   - Para isso iremos utilizar o comando:
   -      medusa -h (ip da máquina alvo) -U (lista de usuários).txt -P (lista de senhas) -M ftp
   -  Com resultados de :
   -  <img width="650" height="762" alt="teste completo para encontrar a senha" src="https://github.com/user-attachments/assets/0ac07845-147d-4f01-bda0-847e6d0c46ee" />

  ## Parte 4.2: Utilizando o Password Spaying
  - Agora para fins de testes utilizei o método de Password Spaying, que consiste em testas uma senha para um grupo de usuários.
  -     medusa -h (ip da máquina alvo) -U (lista de usuários).txt -p '(senha para o grupo de usuários)' -M ftp
  - Com informações obtidas:
  - <img width="1917" height="925" alt="Teste do password spay" src="https://github.com/user-attachments/assets/1d63c68d-c96b-4067-afc3-ad19691507fb" />

# Parte 5: Ataque de Brute Force na interface Web
  - Utilizando a ferramente do Metasploit 2, dvwa, que é um ambiente web de login, para testes de brute force. Utilizei o comando:
  -     medusa -h (ip da máquina alvo) -U (lista de usuários).txt -p '(senha para o grupo de usuários)' -M web-form -m URL-PATH: "/dvwa/login.php" -m FORM-DATA: "username^USER^&password=^PASS^&Login=Login" -m PAGE-MATCH:"Login failed"
  - Com resultados :
  - <img width="1918" height="957" alt="INVASAO WEB " src="https://github.com/user-attachments/assets/51bc5d13-b0c3-4ecc-86da-7f73769e5b0c" />
