# Prompts

Contexto: Este é um projeto de uma API usando dotnet para listar os dados dos bosses de Megaman. O objetivo principal é ser um backed que fornece JSONs no formato abaixo:

```
Robot{ 
  Id =1,
  Code = "DLN/DRN-003",
  Name = "Cutman",
  HP = 150,
  Picture = "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```



Especificações do projeto:

```
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.8" />
    <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="3.1.8">
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
      <PrivateAssets>all</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="3.1.8" />
    <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
  </ItemGroup>

</Project>
```

ENDPOINTS:

```
using System.Collections.Generic;
using Megaman.Dtos;
using Megaman.Services;
using Microsoft.AspNetCore.Mvc;

namespace Megaman.Controllers
{
    //api/v1/robots
    [ApiController]
    [Route("api/v1/robots")]
    public class RobotsController : ControllerBase
    {
        private readonly IRobotServices _services;
        public RobotsController(IRobotServices services)
        {
           _services = services;
        }

        //GET api/robots
        [HttpGet] 
        public ActionResult<IEnumerable<RobotReadDTO>> GetAllRobots()
        {
            var robotItems = _services.SearchAll();
            return Ok(robotItems);
        }

        //GET api/v1/robots/{id}
        [HttpGet]
        [Route("{id:int}")]
        public object GetCommandById([FromRoute]int id)
        {   
            var robot = _services.SearchById(id);

            if(robot != null)
                return Ok(robot);
            
                return NotFound( 
                        new { message = "Nenhum robo encontrado" }
                );
        }

        //POST api/v1/robots
        [HttpPost]
        public ActionResult RobotSend(){
            return Ok();
        }


    }
}
```

REGRAS:

1. Sempre que citar uma dependecia do projeto, deixe um hiperlink para a pagina oficial daquela dependecia
2. Organize as dependecias em uma seção em formato de tabela
3. Crie uma estrutura do projeto com base na arvore de pastas abaixo e crie uma seção para explicar as tecnicas utilizadas:

.vs
.vscode
bin
Controllers
Database
middlewares
Models
obj
Properties
Services
appsettings.Development.json
appsettings.json
global.json
MegamanApi.csproj
MegamanApi.sln
Program.cs
Startup.cs