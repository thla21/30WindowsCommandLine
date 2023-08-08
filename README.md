# 30WindowsCommandLine


#### Abrindo e Gerenciando arquivos/pastas

Sempre abra o prompt de comando no modo administrador

```cmd
runas /user:Administrator cmd

```

Ocultar arquivos zip ou rar dentro de uma imagem

```cmd
copy /b image.extension+folder.zip image.extension
```


#### criptografar arquivos em uma pasta

```cmd
cipher /E
```


#### Ocultar uma pasta de todos

```cmd
attrib +h +s +r foldername
```

Para exibi-lo, use este comando:

```cmd
attrib h s r foldername
```


#### Show all wifi passwords

Primeiro apresente a lista de redes WiFi:

```cmd
netsh wlan show profile
```

Segundo, apresente as senhas

```cmd
netsh wlan show profile wifinetwork key=clear |
findstr “Key Content”
```

Para visualiar toda a rede WiFi:

```cmd
for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan
show profiles') do @if "%j" NEQ "" (echo SSID: %j &
netsh wlan show profiles %j key=clear | findstr "Key
Content") & echo.
```


#### Save Output of a Command to a File

```cmd
command >> output.txt
```


#### Create a batch file

```cmd
for /F "tokens=2 delims=:" %a in ('netsh wlan show
 profile') do @(set wifi_pwd= & for /F "tokens=2 delims=:
usebackq" %F IN ( netsh wlan show profile %a key^=clear
^| find "Key Content" ) do @(set wifi_pwd=%F) & echo %a :
!wifi_pwd!)
```


### Informações do sistema

## Exibir operação e configuração detalhadas do sistema
informação

```cmd
systeminfo
```

#### Copie arquivos com segurança entre hosts remotos

```cmd
scp file.txt root@serverip:~/file.txt
```


#### Abra o CMD dentro de um diretório do Windows

```cmd
CMD” in the search bar
```

