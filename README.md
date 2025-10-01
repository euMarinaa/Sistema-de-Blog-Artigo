📝 Estrutura do Banco de Dados do Blog

Este projeto contém um sistema simples de blog com autores, artigos e comentários. Abaixo está a explicação de cada tabela e seus relacionamentos.


👩‍💻 Tabela Autores

Armazena informações sobre os autores do blog.

Coluna	Tipo	Descrição
AutorID	INT	Identificador único do autor (chave primária)
Nome	VARCHAR(100)	Nome completo do autor
Email	VARCHAR(100)	Email do autor (único)
DataCadastro	DATETIME	Data de cadastro do autor (padrão: data atual)

✨ Observações:

Um autor pode escrever muitos artigos.

Cada autor é único pelo Email.

📰 Tabela Artigos

Armazena os artigos escritos pelos autores.

Coluna	Tipo	Descrição
ArtigoID	INT	Identificador único do artigo (chave primária)
AutorID	INT	Referência ao autor do artigo (chave estrangeira 🔗)
Titulo	VARCHAR(200)	Título do artigo
Conteudo	VARCHAR(MAX)	Conteúdo completo do artigo
DataPublicacao	DATETIME	Data de publicação (padrão: data atual)
Relatorio	VARCHAR(20)	Status do artigo (Rascunho ou Publicado)

✨ Observações:

Relacionamento Autores (1) → Artigos (N)

Cada artigo pertence a um único autor, mas um autor pode ter vários artigos.

💬 Tabela Comentarios

Armazena os comentários feitos em cada artigo.

Coluna	Tipo	Descrição
ComentarioID	INT	Identificador único do comentário (chave primária)
ArtigoID	INT	Referência ao artigo comentado (chave estrangeira 🔗)
Nome	VARCHAR(100)	Nome de quem comentou
Email	VARCHAR(100)	Email do comentarista
Texto	VARCHAR(MAX)	Texto do comentário
DataComentario	DATETIME	Data do comentário (padrão: data atual)

✨ Observações:

Relacionamento Artigos (1) → Comentarios (N)

Cada comentário pertence a um único artigo, mas um artigo pode ter vários comentários.


** Um autor pode ter muitos artigos.
** Um artigo pode ter muitos comentários.
** Cada artigo pertence a apenas um autor.
** Cada comentário pertence a apenas um artigo.

