# Library System

Este repositório implementa um sistema de livraria utilizando um design baseado em DDD (Domain-Driven Design) e as seguintes tecnologias:

- **Node.js**: Back-end do sistema, gerenciando a lógica de negócios e os endpoints da API.
- **Neo4j**: Banco de dados orientado a grafos para modelar relações complexas entre entidades como livros, autores e usuários.
- **Next.js**: Front-end do sistema, proporcionando uma interface amigável e responsiva para os usuários.
- **Jest**: Framework de testes para garantir a qualidade do código e a integridade do sistema.

## Features

- **Gestão de Livros**: Cadastro, edição e remoção de livros no sistema.
- **Pesquisa Avançada**: Busca de livros por título, autor ou gênero.
- **Sistema de Recomendação**: Sugestões personalizadas baseadas em histórico de leitura e preferências.
- **Relacionamentos**: Exploração de relações entre livros e autores usando grafos no Neo4j.
- **Autenticação e Autorização**: Gerenciamento seguro de usuários com diferentes papéis (administradores, clientes, etc.).

## Estrutura do Projeto (DDD)

O sistema está dividido em camadas baseadas em DDD para separar responsabilidades e organizar o código:

### 1. **Camada de Domínio**
Contém as regras de negócio principais e as entidades centrais do sistema.

- **Entidades**: Modelos principais, como `Book`, `Author`, `User`.
- **Agregados**: Conjuntos de objetos associados, tratados como uma unidade (ex.: um autor com seus livros).
- **Serviços de Domínio**: Lógicas que não se encaixam em uma única entidade ou agregado.
- **Repositórios**: Interfaces para acesso aos dados.

### 2. **Camada de Aplicação**
Orquestra o fluxo de informação entre o domínio e o mundo externo.

- **Serviços de Aplicação**: Coordenam casos de uso específicos, como "cadastrar um livro" ou "recomendar livros".
- **DTOs**: Objetos de transferência de dados entre as camadas.

### 3. **Camada de Infraestrutura**
Fornece implementações para os repositórios e conexões com tecnologias externas.

- **Banco de Dados**: Configurações e interações com o Neo4j.
- **Serviços Externos**: Integrações com APIs de terceiros, se necessário.

### 4. **Camada de Interface do Usuário**
Responsável pela interação com o usuário final.

- **Front-End**: Desenvolvido com Next.js para renderização SSR (Server-Side Rendering) e uma experiência fluida.

## Configuração do Ambiente

### Dependências

Certifique-se de ter instalados os seguintes softwares:

- Node.js (versão 18 ou superior)
- Neo4j (Community ou Enterprise Edition)

### Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/library-system.git
   cd library-system
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```

3. Configure o arquivo `.env` com as variáveis de ambiente necessárias:
   ```env
   NEO4J_URI=bolt://localhost:7687
   NEO4J_USERNAME=seu-usuario
   NEO4J_PASSWORD=sua-senha
   JWT_SECRET=sua-chave-secreta
   ```

4. Inicie o Neo4j e certifique-se de que está funcionando corretamente.

5. Execute o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```

6. Abra o navegador em [http://localhost:3000](http://localhost:3000).

## Testes

- Para rodar os testes:
  ```bash
  npm run test
  ```

- Para acompanhar a cobertura de testes:
  ```bash
  npm run test:coverage
  ```

## Contribuição

1. Faça um fork do projeto.
2. Crie um branch para sua feature/bugfix:
   ```bash
   git checkout -b minha-feature
   ```
3. Faça os commits e envie suas alterações:
   ```bash
   git push origin minha-feature
   ```
4. Abra um pull request no repositório principal.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.

