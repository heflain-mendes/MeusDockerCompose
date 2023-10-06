# README - Orientações de uso do Compose

Este guia fornece instruções sobre como usar o Docker Compose para configurar e executar ambientes de desenvolvimento para várias tecnologias, incluindo GCC, Prolog, MySQL e PostgreSQL. Você pode usar o Docker Compose para simplificar a criação e execução desses ambientes em contêineres Docker.

## Requisitos

Antes de começar, certifique-se de que você tenha o Docker e o Docker Compose instalados em seu sistema. Você pode instalá-los seguindo as instruções em [docker.com](https://www.docker.com/get-started).

## Configuração dos Ambientes

Antes de executar qualquer ambiente, você deve seguir as instruções de configuração apropriadas para garantir que os arquivos necessários sejam montados corretamente nos contêineres.

### Ambiente GCC

Para usar o ambiente GCC, siga estas etapas:

1. Execute o seguinte comando para iniciar o contêiner:

   ```bash
   docker-compose -f dc_gcc.yaml run gcc bash
   ```

2. Monte seu código-fonte dentro do contêiner copiando-o de `./src` para `/app`.

3. Compile seu código-fonte usando o GCC:

   ```bash
   gcc -o myapp main.c
   ```

### Ambiente Prolog

Para usar o ambiente Prolog, siga estas etapas:

1. Execute o seguinte comando para iniciar o contêiner:

   ```bash
   docker-compose -f dc_prolog.yaml run prolog bash
   ```

2. Monte seu código-fonte dentro do contêiner copiando-o de `./src` para `/app`.

3. Compile seu código-fonte usando o SWI-Prolog:

   ```bash
   swipl -f <nome_arquivo>.pl
   ```

### Ambiente MySQL

Para usar o ambiente MySQL, siga estas etapas:

1. Execute o seguinte comando para iniciar o contêiner:

   ```bash
   docker-compose -f dc_mysql.yaml up
   ```

2. Monte seus arquivos de dados dentro do contêiner copiando-os de `./db` para `/var/lib/mysql`.

### Ambiente PostgreSQL

Para usar o ambiente PostgreSQL, siga estas etapas:

1. Execute o seguinte comando para iniciar o contêiner:

   ```bash
   docker-compose -f dc_postgre.yaml up
   ```

2. Monte seus arquivos de dados dentro do contêiner copiando-os de `./db` para `/var/lib/postgresql/data`.

## Encerrando os Ambientes

Depois de concluir o uso de qualquer ambiente, você pode encerrá-lo executando o seguinte comando:

```bash
docker-compose -f <arquivo_compose>.yaml down
```

Substitua `<arquivo_compose>.yaml` pelo arquivo de composição específico que você deseja encerrar, como `dc_gcc.yaml`, `dc_prolog.yaml`, `dc_mysql.yaml` ou `dc_postgre.yaml`.

Lembre-se de que essas são apenas diretrizes básicas para começar a usar esses ambientes com o Docker Compose. Certifique-se de adaptar essas instruções às necessidades específicas do seu projeto e ambiente de desenvolvimento.
