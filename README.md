# Ações a serem realizadas no Servidor

#### A descrição completa desse projeto pode ser obtida [aqui](http://www.repositorio.ufc.br/handle/riufc/25186).
#### Uma atualização desse projeto pode ser encontrada [aqui](https://github.com/Renato2012/NuvemOportunistica2.0).


* Instale as dependencias com o script abaixo.
```
sudo ./dependencias.sh
```

* Siga os passos a seguir para instalar sua nuvem!

#### Passo 1:
Execute o script a seguir para instalar e configurar o KVM no seu servidor.
```
./conf_cliente.sh <senha_adm> <senha_one> <nome_maquina> <ip>
```

#### Passo 2:
Instale o Gerenciador OpenNebula na máquina a ser o servidor de forma autocontida usando a hierarquia de diretórios: */srv/cloud/one/*.

#### Passo 3:
Copie a pasta cliente para o diretório home do oneadmin, mude o dono e grupo.
```
sudo cp -r cliente/ /home/oneadmin/
sudo chown -Rf oneadmin.oneadmin /home/oneadmin/cliente/
```

#### Passo 4:
Ligue todas as máquinas da rede que deseja que faça parte da nuvem. 
Execute o script para procurar e salvar uma lista com os endereços IPs e outra com os endereços MACs de sua rede. 
Será solicitado uma interface de rede, digite: **br0**. Esse Script se encontra na pasta */home/oneadmin/cliente/*
```
./procuraMACS.sh
```

* Este script irá gerar os arquivos:
listaDeIPs.txt -- contendo os IPs;
listaDeMACs.txt -- contendo os MACs.

#### Passo 5:
Execute o script a seguir para instalar o kvm nos clientes e configura-los.
```
./conexao_oneadmin.sh
```

## Author

* **Renato Araújo**
