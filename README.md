# GHF-lab-md-04
Repositório visa consolidar o conhecimento apresentado na aula.

Modulo 04 - Desenvolvimento moderno 

> Criar Reposiório

> Codespace: criar código da aplicação
- Crie uma aplicação dotnet core wepapp usando a lista de comandos abaixo: (executar os comandos no terminal)
```
//Criar o webapp:
  ```dotnet new webapp -n github4women```
//Baixar as dependências:
  ```dotnet restore **/*.csproj```
//Compilar o webapp:
  ```dotnet build **/*.csproj --no-restore```
//Rodar o wepapp:
  ```dotnet run --project **/*.csproj```
```
- Crie o arquivo de Workflow
```
    name: .NET

    on:
      push:
        branches: [ "main" ]
      pull_request:
        branches: [ "main" ]
    
    jobs:
      buildapp:
        runs-on: ubuntu-latest

        steps:
        - uses: actions/checkout@v4
        - name: Setup .NET
          uses: actions/setup-dotnet@v4
          with:
            dotnet-version: 8.0.x
        - name: Restore dependencies
          run: dotnet restore **/*.csproj
          working-directory: ${{ github.workspace }}
        - name: Build
          run: dotnet build **/*.csproj
```
- Executar o workflow
- Verificar Log do Workflow
  ![image](https://github.com/user-attachments/assets/f151d791-cb47-4a5e-9c31-180f4f395a84)


