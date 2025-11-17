# LuminaGuide

Sistema de Cálculo de Iluminação Residencial e Comercial
Disciplina: Engenharia de Software III – Etapa 02
Instituto Federal do Triângulo Mineiro — IFTM Campus Patrocínio

📖 Descrição Geral do Projeto

O PrjLuminaGuide é um sistema desenvolvido em Java, utilizando a arquitetura em camadas (Model – DAO – BO – View), com o objetivo de auxiliar vendedores e profissionais na análise e recomendação de iluminação adequada para ambientes, seguindo parâmetros técnicos de luminância (lux), área, pé-direito e fluxo luminoso de lâmpadas.

O sistema permite:

Cadastro e consulta de clientes

Gerenciamento de produtos (lâmpadas)

Gerenciamento de ambientes e valores de lux recomendados

Cálculo de iluminação necessária para um ambiente

Geração de histórico de cálculos

Relatórios textuais no terminal

Este projeto implementa boas práticas de modularização, uso de banco de dados MySQL, CRUD completo e organização em pacotes.

🛠 Tecnologias Utilizadas

Java 23

MySQL 8.x

JDBC

Apache Maven

NetBeans 25

Arquitetura MVC Simplificada (Model, DAO, BO, View)

📂 Estrutura do Projeto
src/
 └─ atividade/prjluminaguide/
      ├─ models/       → Classes de modelo (Cliente, Produto, Ambiente, etc.)
      ├─ dao/          → Acesso ao banco de dados
      ├─ bo/           → Regras de negócio
      ├─ view/         → Menus interativos (linha de comando)
      ├─ util/         → Classe de conexão (Conexao.java)
      └─ PrjLuminaGuide.java → Classe principal

🗄 Configuração do Banco de Dados

Crie o banco:

CREATE DATABASE luminaguide;
USE luminaguide;


Crie a tabela de clientes:

CREATE TABLE cliente (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    cpf VARCHAR(11),
    telefone VARCHAR(20),
    endereco VARCHAR(255)
);


Mesma lógica será usada para as tabelas:

produto

ambiente

vendedor

historicoCalculo

🔧 Requisitos do Ambiente

Antes de instalar, verifique se possui:

✔ Java JDK 23 instalado
✔ MySQL Server 8.x
✔ Variáveis de ambiente JAVA_HOME configuradas
✔ Maven instalado (ou integrado no NetBeans)

📥 Instalação e Execução
1. Clonar o repositório
git clone https://github.com/DouglasMiqueias/LuminaGuide.git
cd PrjLuminaGuide

2. Configurar a conexão com o banco

Edite o arquivo:

📌 src/.../util/Conexao.java

return DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/luminaguide",
    "root",
    "SUA_SENHA"
);

3. Compilar o projeto via Maven
mvn clean install

4. Executar o sistema
mvn exec:java -Dexec.mainClass="atividade.prjluminaguide.PrjLuminaGuide"


Ou simplesmente rodar pelo NetBeans (Run Project).

🎮 Como Usar o Sistema

Após executar o programa, será exibido o menu principal. Navegue pelas opções usando o teclado.

Fluxo básico sugerido:

Cadastrar um cliente

Cadastrar ambientes (ex.: banheiro, sala, escritório)

Cadastrar produtos (fluxo luminoso, potência, temp. de cor)

Acessar o menu de cálculo

Informar: área, pé-direito, pontos de luz, tipo de ambiente

Receber o cálculo + recomendação de produtos

O sistema salva o cálculo no histórico

✔ Boas Práticas Implementadas

Modularização em pacotes

Classes DAO com PreparedStatement

Camada BO com regras de negócio

Validação de entrada de dados

Separação completa entre view / lógica / acesso ao banco

Código comentado e padronizado

Uso correto de versionamento Git

Testes manuais funcionais

Organização orientada ao TCD

🧪 Testes

A etapa 2 inclui testes funcionais manuais, cobrindo:

CRUD de clientes

CRUD de produtos

Busca por ID

Conexão com banco

Cálculo de iluminação

Salvamento no histórico

(Na Etapa 03 você fará os testes formais — JUnit, integração, etc.)

👨‍💻 Autor

Douglas Miquéias de Alkimim Mota
Curso: Tecnologia em Análise e Desenvolvimento de Sistemas
Disciplina: Engenharia de Software 3 (TCD – Etapa 02)
IFTM – Campus Patrocínio

📝 Licença

Este projeto é acadêmico e faz parte das entregas obrigatórias do TCD da disciplina ESOF 3 no IFTM.
