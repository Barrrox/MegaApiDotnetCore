# Visão Geral do Projeto

Esta API foi desenvolvida em .NET Core 3.1 e tem como objetivo fornecer, via endpoints, informações sobre os bosses do Megaman em formato JSON. Cada entidade Robot é representada com os atributos: Id, Code, Name, HP e Picture.

# Dependências do Projeto

As principais dependências utilizadas foram organizadas na tabela abaixo, com links para as respectivas páginas oficiais:

| Dependência | Versão | Link Oficial
----------------------------------------
| Microsoft.EntityFrameworkCore |	3.1.8	| Microsoft.EntityFrameworkCore
| Microsoft.EntityFrameworkCore.Design |	3.1.8 |	Microsoft.EntityFrameworkCore.Design
| Microsoft.EntityFrameworkCore.SqlServer	| 3.1.8	| Microsoft.EntityFrameworkCore.SqlServer
| Newtonsoft.Json |	12.0.2 | Newtonsoft.Json

# Estrutura do Projeto

A estrutura do projeto segue a árvore de pastas abaixo:

pgsql
Copiar
Editar
.vs/
.vscode/
bin/
Controllers/
Database/
middlewares/
Models/
obj/
Properties/
Services/
appsettings.Development.json
appsettings.json
global.json
MegamanApi.csproj
MegamanApi.sln
Program.cs
Startup.cs

# Descrição dos Diretórios e Arquivos
- .vs/ e .vscode/: Contêm as configurações específicas do ambiente de desenvolvimento (Visual Studio e Visual Studio Code, respectivamente).
- bin/: Armazena os arquivos compilados da aplicação.
- Controllers/: Hospeda os controladores que gerenciam os endpoints da API (por exemplo, RobotsController).
- Database/: Provavelmente contém a configuração do contexto do Entity Framework e migrações relacionadas ao banco de dados.
- middlewares/: Pasta destinada aos middlewares, que são componentes responsáveis por interceptar e processar as requisições HTTP.
- Models/: Contém as classes de modelo que representam as entidades do domínio (como o Robot).
- obj/: Pasta gerada durante o processo de build com arquivos intermediários.
- Properties/: Contém arquivos de propriedades do projeto, como informações de assembly.
- Services/: Contém a camada de serviços onde reside a lógica de negócio e a comunicação com a camada de acesso a dados.
appsettings.Development.json e appsettings.json: Arquivos de configuração para os ambientes de desenvolvimento e produção.
global.json: Define a versão do SDK do .NET a ser utilizada pelo projeto.
- MegamanApi.csproj: Arquivo de projeto que especifica as dependências e configurações do build.
- MegamanApi.sln: Solução que agrupa os projetos da aplicação.
- Program.cs: Ponto de entrada da aplicação.
- Startup.cs: Responsável pela configuração dos serviços (DI, middlewares, etc.) e do pipeline de requisição.

# Técnicas e Boas Práticas Utilizadas
- .NET Core 3.1: Plataforma robusta e multiplataforma para o desenvolvimento de aplicações web de alto desempenho.
- Entity Framework Core (EF Core): Utilizado para o mapeamento objeto-relacional (ORM), facilitando o acesso e a manipulação de dados no banco de dados SQL Server. As dependências relacionadas foram:
  -  Microsoft.EntityFrameworkCore
  - Microsoft.EntityFrameworkCore.Design
  - Microsoft.EntityFrameworkCore.SqlServer
- Newtonsoft.Json: Biblioteca para serialização e desserialização de objetos JSON, garantindo uma troca de dados consistente e padronizada. Veja mais em Newtonsoft.Json.
- Arquitetura em Camadas: A separação em Controllers, Services e Models promove uma estrutura modular, facilitando a manutenção, testes e escalabilidade do sistema.
- Configuração Centralizada: Uso dos arquivos appsettings.json para gerenciar as configurações da aplicação, permitindo ajustes conforme o ambiente (desenvolvimento, homologação, produção).
- Middlewares Customizados: Implementação de middlewares para tratamento centralizado de requisições, autenticação, logging e tratamento de erros, melhorando a robustez e a segurança da API.