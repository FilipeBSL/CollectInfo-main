## Requisitos

Para rodar o projeto em sua máquina, é necessário ter as seguintes instalações:

- **Maven** 3.6.3 ou posterior
- **Java** 17 ou posterior
- **Javac** 17 (deve estar alinhado com a versão do Maven)

**Observação:** Mesmo que você utilize uma versão posterior ao Java 17, o compilador Java (`javac`) precisa estar
apontando para a versão 17 para garantir compatibilidade com o Maven.

### 1. Clonando o Repositório

Para obter o código-fonte do projeto, execute:

```sh
git clone https://github.com/FilipeBSL/userService.git
cd traduzzo_api
```
Caso queira clonar uma branch específica, utilize:
```sh
git clone --branch <nome-da-branch> https://github.com/FilipeBSL/userService.git
cd traduzzo_api
```

### 2. Verificando e Instalando o Maven

Verifique se o Maven está instalado corretamente executando:

```sh
mvn -version
```

Se a versão for menor que a necessária, atualize ou instale o Maven:

**Ubuntu/Debian:**

```sh
sudo apt update && sudo apt install maven -y
```

**Fedora/RHEL:**

```sh
sudo dnf install maven -y
```

### 3. Verificando e Instalando o Java

Verifique se o Java está instalado corretamente executando:

```sh
java -version
```

Se a versão for menor que a necessária, atualize ou instale o Java conforme sua distribuição:

**Ubuntu/Debian:**

```sh
sudo apt update && sudo apt upgrade openjdk-* -y
sudo apt install openjdk-17-jdk -y
```

**Fedora/RHEL:**

```sh
sudo dnf update && sudo dnf install java-17-openjdk -y
```

### 4. Verificando e Configurando o `javac`

Após instalar o Java, é essencial garantir que o `javac` esteja alinhado com a versão utilizada pelo Maven.
Verifique a versão do `javac` executando:

```sh
javac -version
```

Se a versão do `javac` não corresponder ao Java configurado, atualize a alternativa do `javac` usando:

```sh
sudo update-alternatives --config javac
```

Escolha a opção que corresponda ao Java 17 (ou à versão utilizada pelo Maven).

Caso a opção do `javac` 17 não esteja disponível, adicione manualmente com o seguinte comando:

```sh
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/java-17-openjdk-amd64/bin/javac 100
```

Depois, execute novamente:

```sh
sudo update-alternatives --config javac
```

Selecione a opção correspondente ao Java 17.

E depois verifique a versão do javac novamente:
```sh
javac -version
```

## Execução da API

Para compilar e executar a API, utilize o Maven:

```sh
mvn clean install
mvn spring-boot:run
```

A API será executada na porta padrão **8080**. Se necessário, altere a porta no arquivo de propriedades:

```properties
server.port=8080
```
