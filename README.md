# Kibexinhos_Docker

Projeto para "deploy" do projeto Kibexinhos utilizando Docker.

## Passos Para Rodar o Projeto

### Download do projeto e atualização de submodulos

#### Clone o projeto no servidor que o projeto será executado

Acesse o servidor e faça o clone do projeto no servidor.

```bash
git clone https://github.com/Evertonmag/Kibexinhos_Docker.git
```

#### Atualização dos submodulos

Ainda no servidor ssh, execute os comandos:

```bash
# Indo para o diretório do projeto
cd Kibexinhos_Docker

# Atualizando git modules
git submodule update --init --recursive --remote
```

### Configurando Environment

#### Formato do arquivo .env

```bash
SendGridApiKey=<SUA_API_KEY_AQUI>
DBUser=<USUÁRIO_DO_BANCO>
DBPassword=<SENHA_DO_BANCO>

```

#### Opção 1: Copiando um arquivo .env da máquina local para o servidor

Gere o arquivo `.env` localmente e execute o comando scp para copiar para o servidor.

```bash
scp .env <USUARIO>@<IP_DO_SERVIDOR>:~/Kibexinhos_Docker
```

#### Opção 2: Criando um arquivo .env no servidor

Navegue até o diretório do projeto e gere o arquivo `.env` com um editor como `nano` ou `vim`.

### Rodando o Projeto no Servidor

Acesse o servidor por ssh e execute os comandos:

```bash
# Indo para o diretório do projeto
cd Kibexinhos_Docker

# Compilando e executando o projeto
docker-compose up --detach --build
```
