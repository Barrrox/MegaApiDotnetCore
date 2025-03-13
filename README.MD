<h1 align="center">
  
  <br>
  <img
  src=".\_docs\assets\icon.png"
  width = "450"
  >
  </br>
  <a href="#">
    Megaman API
  </a>
</h1>

<p align="center">
  <strong>Fornecendo informações sobre os bosses do Megaman via API REST.</strong>
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License" />
  </a>
  <a href="#dependencias">
    <img src="https://img.shields.io/badge/.NET_Core-3.1-blue" alt=".NET Core 3.1" />
  </a>
  <a href="#contribuir">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="Contribuições bem-vindas!" />
  </a>
</p>



## 🚀 Visão Geral

A **Megaman API** foi desenvolvida em **.NET Core 3.1** para fornecer informações sobre os bosses do Megaman em formato JSON. Cada entidade `Robot` contém os seguintes atributos:

- **Id**: Identificador único
- **Code**: Código do robô
- **Name**: Nome do boss
- **HP**: Pontos de vida
- **Picture**: URL da imagem

## 📦 Dependências

Esta API utiliza as seguintes dependências:

| Dependência | Versão |
|-------------|--------|
| [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore) | 3.1.8 |
| [Microsoft.EntityFrameworkCore.Design](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design) | 3.1.8 |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer) | 3.1.8 |
| [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json) | 12.0.2 |

## 📂 Estrutura do Projeto

```
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
```

### 🏗️ Descrição dos Diretórios
- **Controllers/** - Contém os controladores responsáveis pelos endpoints da API.
- **Database/** - Contém a configuração do Entity Framework e migrações.
- **middlewares/** - Implementação de middlewares para tratamento de requisições.
- **Models/** - Representação das entidades do domínio.
- **Services/** - Camada de serviços responsável pela lógica de negócios.
- **Program.cs** - Ponto de entrada da aplicação.
- **Startup.cs** - Configuração dos serviços e pipeline de requisições.

## 🛠️ Técnicas e Boas Práticas

- **.NET Core 3.1** - Plataforma moderna, escalável e multiplataforma.
- **Entity Framework Core** - ORM para acesso ao banco de dados SQL Server.
- **Newtonsoft.Json** - Serialização e desserialização JSON.
- **Arquitetura em Camadas** - Separação de responsabilidades em Controllers, Services e Models.
- **Configuração Centralizada** - Uso de `appsettings.json` para gerenciamento de configurações.
- **Middlewares Customizados** - Implementação para autenticação, logging e tratamento de erros.

## 🤝 Como Contribuir

Quer contribuir para o projeto? Veja as orientações abaixo:

1. Faça um fork do repositório.
2. Crie um branch com sua feature (`git checkout -b minha-feature`).
3. Faça commit das mudanças (`git commit -m 'Adiciona nova feature'`).
4. Faça push para o branch (`git push origin minha-feature`).
5. Abra um Pull Request.

## 📄 Licença

Este projeto é licenciado sob a [Licença MIT](https://opensource.org/licenses/MIT).

