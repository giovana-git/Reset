# Reset
Comandos para dar reset no Switch e Router 

**RESETAR O SWITCH** 
```
1) Conectar o cabo Rollover.
2) Conectar cabo de energia. 
3) Verificar porta de comunicação:
  Windows + R 
  devmgmt.msc 
4) Abrir o PuTTy e selecionar a porta "Serial", inserir a opção "COM1" e clicar no botão "OPEN". 
5) Esperar o Switch ligar completamente (Vai aparecer a tela '>' OU vai pedir para entrar no modo de configuração guiado [yes/no] OU o equipamento vai pedir uma senha caso já esteja configurado).
6) Após o Switch ligar completamente, aperte e segure o botão "MODE" até que os dois primeiros led's fiquem laranja. 
7) Espere o Switch reiniciar e verifique se o reset funcionou
``` 

**RESETAR O ROUTER**
```
1) Abrir o Putty e conectar no Roteador com o equipamento DESLIGADO
2) Ligar o Roteador e pressionar diversas vezes o atalho "Ctrl+Pause Break", até aparecer o texto "rommon 1>"

3)Digitar os seguinte comandos NESSA SEQUÊNCIA:
	confreg 0x2142
	reset

4)Espera o roteador reiniciar e verifique se o Roteador está no registrador correto (0x2142)
	>enable
	#show version

5)Salvar as configurações de fábrica na startup-config
	#copy running-config startup-config
	ou
	#write memory
	ou
	#wr
    
6)Voltar para o registrador padrão (0x2102)
	#configure terminal
	(config)#config-register 0x2102
    
7)Reiniciar o equipamento
	(config)#exit
	#reload
	Responder "YES" para as perguntas!
```
