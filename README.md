# Definição
O Ansible basicamente é uma ferramenta open-source de automação, geralmente utilizada para configurar sistemas e provisionar recursos de nuvem. Ele é capaz de simplificar tarefas repetitivas, além de aumentar a eficiência operacional e facilitar a gestão de infrestruturas complexas. De forma resumida, ele permite escrever e executar inúmeras tarefas nos servidores definidos, de modo que é possível reaproveitar muitas delas para diferentes hosts.

# Como o Ansible funciona?
Ele opera usando um modelo de automação baseado em playbooks e roles.
* **Playbooks:** elas são escritas em YAML e descrevem uma série de tarefas que devem ser executadas nos servidores.
	*  **Declarativo:** significa que você pode especificar o estado desejado do sistema.
	*  **Tasks e módulos:** as tasks, ou tarefas, são executadas usando os módulos do Ansible, que nada mais são do que pequenos programas em Python que realizam ações específicas, como instalação de pacotes, manipulação de arquivos de configuração e dentre outros.

* **Inventário:** basicamente é onde fazemos a configuração dos hosts, que são os servidores que desejamos executar as playbooks.

* **Orquestração:**
	* **Paralelismo:** o Ansible é capaz de executar tarefas em paralelo em vários servidores, o que aumenta a produtividade e eficiência.
	* **Rolling updates:** facilita atualizações em servidores de forma controlada.

* **Roles:** basicamente é uma função específica, sendo a melhor forma de organizar suas playbooks, pois elas podem ser reutilizadas em várias playbooks simultaneamente. Dentro de roles temos também subpastas, onde os nomes são intuitivos:
	* **tasks:** definem as tarefas que serão executadas, ou seja, representam as ações que serão realizadas pelo Ansible.
	* **files:** armazena arquivos que geralmente são copiados para o servidor de destino.
	* **templates:** contém arquivos Jinja2, que são usados para gerar arquivos de configuração dinâmicos no servidor.
	* **handlers:** ações a serem realizadas em eventos específicos, como reiniciar o serviço após uma alteração na configuração.
	* **meta:** armazena informações sobre a Role, como dependências de outras Roles ou sistemas operacionais suportados.
	* **defaults:** definem variáveis padrão para essa role em questão.
	* **vars:** definem variáveis específicas da role.

## Instalação 
* Atualização do sistema:
```
sudo apt update  # ou use yum no Red Hat, dnf no Fedora, etc.
sudo apt upgrade
```
* Instalação do Ansible:
```
sudo apt install ansible  # ou use o gerenciador de pacotes correspondente à sua distribuição
```
* Verificação da instalação:
```
ansible --version
```

## Configuração inicial:
* O primeiro passo é, caso você não tenha, gerar uma chave SSH, pois é através dela que iremos nos conectar com os servidores:
```
ssh-keygen -t rsa -b 2048
```
* Depois basta copiar essa chave, da maneira que achar conviniente, para o servidor:
```
ssh-copy-id seu_usuario@seu_servidor
```




