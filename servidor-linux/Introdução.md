
Bem-vindo ao guia de suporte técnico! Este material foi criado para ajudá-lo a resolver problemas comuns e utilizar os principais recursos tecnológicos da empresa de forma simples e rápida.


## RTMP

1. <span style="color: #cfecff;"><b>A câmera não se comunica com o servidor.</b></span>

Esse cenário ocorreria se a câmera não resolvesse DNS ou se não tivesse comunicação com a internet no geral. Para distinguir, no configurador da câmera, basta trocar o DNS do servidor pelo IP dele. Se não funcionar, é possível testar em outro servidor. Por exemplo, com o DNS do Connect Demo:

```
Link onde possui DNS -> `rtmp://connect-491.servicestream.io:1936/stream/teste  
Link onde possui DNS -> `rtmp://177.129.0.76:1936/stream/teste
```


Caso ainda a câmera não esteja abrindo conexão, é possível verificar se a câmera esta resolvendo DNS. Acesse o configurador da câmera e em <b>REDE</b> verifique qual DNS esta configurado e teste. 

<b><span style="color: #cfecff;">Comando para testar DNS:</span></b>

Entrada:
``` nslookup IPservidor DNScâmera```
Saída:
```
Server: 127.0.0.53 
Address: 127.0.0.53#53 
Non-authoritative answer: 
Name: connect-491.servicestream.io 
Address: 177.129.0.76```
```
<span style="color: red;">Observação: </span>Se o resultado for negativo, irá retornar <b>timeout</b>

Caso retorne <b>timeout</b> altere o DNS da câmera para o do <b>Google 8.8.8.8</b> e teste novamente a câmera.

<hr>

## RTSP

As câmeras RTSP terão algumas validações ligeiramente diferentes das câmeras RTMP. Primeiro, no link de uma câmera, note se o IP é público ou privado (se tiver um DNS, provavelmente será público, mas vale testar com um <b>ping</b> fora do servidor do cliente). 

<span style="color: red;">Observação: </span> Se o IP/DNS não pingar fora do servidor, será privado e não público. Ou possui possibilidade do cliente ter desativado o <i><b>ping</b></i> do IP.

Testes inicias, validar se o Link irá abrir no VLC, se o IP for privado, tem a possibilidade de utilizar o comando <i><b>ffprobe</b></i> para ver se vai abrir conexão com o servidor, ou abrir o Link RTSP na mesma rede onde a câmera esta. 

Comando ->  ```ffprobe -loglevel debug "LINK RTSP"```

## E quando nada funcionar?

Se uma câmera não funciona, algumas validações que podem ser feitas são:

- RTSP: Testes de rede desse servidor específico para a câmera (como o `ping`, `telnet`)
- RTMP: Verificar possibilidade de cadastro da câmeras em outro servidor, se em nenhum servidor funcionar, verifique outras questões, como: alinhe com a equipe de servidor se os serviços de RTMP estão okay, atualização de firmware,  
- Qualquer protocolo: Desativar e ativar a câmera na plataforma (isso reinicia o processo dela).



Esse documento não cobre todos os cenários de câmeras off-line, porém os mais comuns podem ser solucionados a partir das informações aqui presentes.






