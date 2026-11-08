Banco de Dados – Rede Social (MySQL)

Projeto em equipe de modelagem e implementação de um banco de dados relacional em MySQL para uma rede social, onde usuários criam perfis, fazem publicações e interagem por meio de curtidas, comentários e compartilhamentos.

Objetivo

Estruturar os dados necessários para o funcionamento básico de uma rede social, garantindo integridade e consistência nas relações entre usuários e conteúdos.

Minha contribuição

Fui responsável pela criação da modelagem do banco de dados: definição das entidades, atributos, relacionamentos, chaves primárias e estrangeiras e restrições de integridade.

Tecnologias
MySQL
SQL (DDL e DML)
MySQL Workbench (modelagem e diagrama DER)
Estrutura do banco

O banco rede_social possui 7 tabelas:

Tabela	Descrição
usuario	Dados de cadastro (nome, e-mail único, senha, data de nascimento)
perfil	Perfil público do usuário (nome de usuário, biografia, pronome); relação 1:1 com usuario
publicacao	Postagens feitas pelos usuários (descrição, conteúdo, data)
comentarios	Comentários dos usuários nas publicações
curtida	Curtidas em publicações; cada usuário curte uma publicação apenas uma vez
compartilhamento	Compartilhamentos de publicações e o local onde foram compartilhadas
pesquisa	Histórico de pesquisas realizadas pelos usuários
Relacionamentos
Um usuário possui um perfil (1:1).
Um usuário pode ter várias publicações, pesquisas, comentários, curtidas e compartilhamentos (1:N).
Uma publicação pode ter vários comentários, curtidas e compartilhamentos (1:N).
Regras de integridade
Chaves primárias com AUTO_INCREMENT.
Chaves estrangeiras ligando as tabelas aos usuários e publicações.
UNIQUE em usuario.email e em perfil.id_usuario.
UNIQUE (id_usuario, id_publicacao) em curtida, evitando curtidas duplicadas.
NOT NULL nos campos essenciais.
Datas preenchidas automaticamente com CURRENT_TIMESTAMP.
Como executar
Tenha o MySQL (ou MySQL Workbench) instalado.
Clone o repositório:
bash
   git clone https://github.com/lu1szz/NOME-DO-REPOSITORIO.git
Execute o script no MySQL:
bash
   mysql -u seu_usuario -p < mysqlfinal.sql

Ou abra o arquivo mysqlfinal.sql no MySQL Workbench e execute-o. 4. Verifique a criação:

sql
   USE rede_social;
   SHOW TABLES;

O script recria as tabelas (DROP TABLE IF EXISTS) e insere dados de exemplo.

Diagrama (DER)
<!-- Adicione aqui a imagem do diagrama: ![DER](docs/der.png) -->
Equipe
Luis Oliveira – modelagem do banco de dados
<!-- adicione os demais integrantes e suas funções -->
Aprendizados
Modelagem de dados e normalização
Criação de tabelas, chaves e restrições em SQL
Trabalho colaborativo em equipe
