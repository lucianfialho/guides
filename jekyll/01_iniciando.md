# Jekyll

## Introdução

Transforme o seu arquivo de texto em um site estático e blogs.

#### Simples
Sem banco de dados, moderação de comentários ou atualizações chatas para instalar - só o seu conteúdo.

#### Estático
Markdown(ou Textile), Liquid, HTML & CSS estão no jogo. Sites estáticos saem prontos para deploy.

#### Blog-consciente

Links permanentes, categorias, páginas, entradas e layouts customizados são todos cidadãos de primeira classe aqui.

#### Entendendo e executando em segundos

	```bash
	$ gem install jekyll
	$ jekyll new meu-site
	$ cd meu-site
	~/meu-site $ jekyll serve
	# => Agora, basta navegar em: http://localhost:4000
	```
	
## Bem vindo

Este site pretende ser um guia completo para *Jekyll*. Vamos abordar temas como obter o seu site instalado e funcionando, criar e gerenciar seu conteúdo, personalizar a forma como o seu site funciona e se apresenta, implantando em vários ambientes, e passando alguns conselhos sobre a participação no desenvolvimento futuro do próprio *Jekyll*.

## Mas, o que é o Jekyll exatamente?

Jekyll é um simples blog-consciente, gerador de site estático. Ele se baseia em um diretório-modelo contendo arquivos de texto no estado bruto em vários formatos, executados através de [Markdown](http://daringfireball.net/projects/markdown/) (ou [Textile](http://textile.sitemonks.com/)) e conversores [Liquid](http://wiki.shopify.com/Liquid), e lhe retorna um website estático completo e adequado pronto para ser publicado nos eu servidor web favorito.

Jekyll também passa a ser o motor por trás das [GitHub Pages](http://pages.github.com/), o que significa que você pode usar *Jekyll* para hospedar a página do seu projeto, blog, ou site nos servidores do GitHub **gratuitamente**.

===

### Dicas, Notas e Avisos

* <span style="color: orange">**Dicas:**</span> ajuda você a obter mais do *Jekyll*. Estas são as dicas e truques que ajudarão você a ser um assistente *Jekyll*!
* <span style="color:darkblue">**Notas:**</span> são pedaços úteis de informação. Estes são para àquela informação extra, às vezes necessária para entender o *Jekyll*.
* <span style="color: red">**Avisos:**</span> ajudam você a não se meter em encrenca. Fique longe dessas mensagens, caso queira evitar desastres.

Se você se deparar com qualquer coisa ao longo do caminho que nós não mencionamos, ou se você souber de uma dica que você acha que os outros achariam útil, por favor, [registre uma issue](https://github.com/mojombo/jekyll/issues/new) e vamos discutir sobre sua inclusão neste guia.

===

## Início rápido

Para os impacientes, aqui está a forma mais rápida para ter uma estrutura pré-definida do Jekyll funcionando e pronta para instalar.

	```bash
	$ gem install jekyll
	$ jekyll new meu-blog
	$ cd meu-blog
	~/meu-blog $ jekyll serve
	# => Agora, basta navegar em: http://localhost:4000
	```
	
Isso não é nada, no entanto. A verdadeira magia acontece quando você começar a criar posts, utilizando a matéria-bruta para controlar templates e layouts, e tirando partido de todas as opções de configuração impressionantes que o Jekyll torna disponível.

> <span style="color:darkblue">**Nota:**</span> Redcarpet é o motor padrão do Markdown para novos sites. No Jekyll 1.1, nós mudamos o motor padrão para sites gerados de `jekyll new` para redcarpet.

Se você estiver com problemas para executar, certifique-se de ter instalado todos os requisitos.

## Instalação

ter o Jekyll instalado "a ponto de bala" demora poucos minutos. Se, em algum momento se tornar um tédio, por favor [registre uma issue]() descrevendo o problema que você encontrou e como podemos tornar o processo mais fácil.

### Requisitos

Instalar o Jekyll é simples e objetivo, mas existem alguns requisitos que precisam ser verificados no seu sistema antes de iniciar.

* [Ruby](http://www.ruby-lang.org/en/downloads/)
* [RubyGems](http://rubygems.org/pages/download)
* Linux, Unix, or Mac OS X

> <span style="color:darkblue">**Nota:**</span> Utilizando o Jekyll no Windows. É possível instalar o [Jekyll no Windows](http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html), mas a documentação oficial não suporta a instalação em plataformas Windows.

### Instalando com o RubyGems

O melhor caminho para instalar o Jekyll é através do RubyGems. No terminal, execute o comando abaixo para instalar o Jekyll.

```bash
$ gem install jekyll
```

Todas as dependências do Jekyll serão instaladas automaticamente ao executar o comando acima, então não se preocupe com isto. Se tiver qualquer problema para instalar o Jekyll, consulte a página [solução de problemas]() ou [relate um problema]() para que a comunidade Jekyll possa melhorar a experiência para todos.

### Opções extras

Há uma série de recursos extras (opcionais) que o *Jekyll* suporta e que você pode querer instalar, dependendo de como você pretende usar *Jekyll*. Esses recursos extras incluem suporte LaTeX, e o uso de motores de renderização de conteúdo (*template engines*) alternativo. Confira [esta página](http://jekyllrb.com/docs/extras) para mais informações.

> <span style="color:orange">**Dica:**</span> Ativar destaque da sintaxe.
Se você é do tipo de pessoa que está usando *Jekyll*, então as chances para ativar o destaque de sintaxe é alta. É possível fazer isso usando *Pygments*. Você deve realmente verificar [como fazer isso](http://jekyllrb.com/docs/templates/#code_snippet_highlighting) antes de ir mais longe.

Agora que você já tem tuo instalado, vamos ao trabalho!

## Uso Básico

A gem do Jekyll, torna possível executar uma variável denominada como `jekyll` no seu terminal. É possível utilizar este comando de diversas maneiras:

	```bash
	$ jekyll build
	# => O diretório atual será gerado dentro da pasta ./_site
	
	$ jekyll build --destination <destino>
	# => O diretório atual será gerado dentro de <destino>
	
	$ jekyll build --source <fonte> --destination <destino>
	# => O diretório <fonte> será gerado dentro de <destino>
	
	$ jekyll build --watch
	# => O diretório atual será gerado dentro da pasta ./_site,
	#    sendo observado quando ocorrerem mudanças nos arquivos
	#    e atualizado automaticamente.
	```

Jekyll também vem com um servidor de desenvolvimento embutido, que permiti a visualização de como está ficando o site gerado no seu ambiente local.

	```bash
	$ jekyll serve
	# => Um servidor de desenvolvimento será executado em: http://localhost:4000/
	
	$ jekyll serve --watch
	# => Assim como mencionado acima, mas sendo observado quando 
	#    ocorrerem mudanças nos arquivos e atualizado automaticamente.	```

Estas, são algumas das opções de configurações disponíveis. Muitas das configurações podem ser especificadas com o uso de *flags* na linha de comando, ou alternativamente (e mais comum), estas podem ser especificadas no arquivo `_config.yml` no diretório raiz do seu projeto. O *Jekyll* usará automaticamente as opções deste arquivo quando executado.

Por exemplo, se você colocar as seguintes linhas no seu arquivo `_config.yml`:

	source:      _fonte
	destination: _destino
	
Os seguintes comando abaixo serão equivalentes:

	$ jekyll build
	$ jekyll build --source _fonte --destination _destino
	
Para saber mais sobre as opções de configuração disponíveis, consulte a página de [configuração](http://jekyllrb.com/docs/configuration).

## Estrutura do Diretório

Jekyll é, em sua essência, um mecanismo de transformação de texto. O conceito por trás do sistema é o seguinte: você dá a ele o texto escrito em sua linguagem de marcação favorita, seja Markdown, TexTile ou um HTML básico, e ele transforma isso em um layout ou numa série de arquivos de layout. Durante todo esse processo, você pode ajustar a aparência das URLs no seu site, quais serão os dados mostrados no layout, e muito mais. Isso tudo é feito através da edição de arquivos de texto, e o site estático será o produto final.

A estrutura báisca de um sit utilizando Jekyll, é a seguinte:

	.
	├── _config.yml
	├── _drafts
	|   ├── begin-with-the-crazy-ideas.textile
	|   └── on-simplicity-in-technology.markdown
	├── _includes
	|   ├── footer.html
	|   └── header.html
	├── _layouts
	|   ├── default.html
	|   └── post.html
	├── _posts
	|   ├── 2007-10-29-why-every-programmer-should-play-nethack.textile
	|   └── 2009-04-26-barcamp-boston-4-roundup.textile
	├── _site
	└── index.html


Uma visão geral sobre o que cada um significa:

| Arquivo / Diretório | Descrição |
|:-------------------:|:---------:|
| `_config.yml` | Armazena os dados de configuração. Muitas destas opções podem ser especificadas e executadas via linha de comando, mas é muito mais prático especificá-las neste arquivo. Até mesmo, para que seja de fácil memorização/visualização. |
| `_drafts` | Rascunhos (drafts) são entradas (posts) não publicadas. O formato destes arquivos é sem uma **data**: `titulo.MARKUP`. Saiba como [trabalhar com rascunhos](http://jekyllrb.com/docs/drafts). |
| `_includes` | Estes são os *partials* que podem ser misturados e combinados em seus layouts e publicados com o intuíto de facilitar a reutilização. A marcação líquida `{% include file.ext %}` pode ser usada para incluir um *partial* em `_includes/file.ext`.
| `_layouts` | Estes são os modelos que envolvem as suas entradas (posts). Os layouts são escolhidos com um esquema post-by-post, <span style="color:red;>"baseado na [prioridade YAML](http://jekyllrb.com/docs/frontmatter)</span>, a qual é descrita na próxima seção. A marcação líquida {{ content }} é utilizada para injetar conteúdo dentro de uma página.
| `_posts` | Seu conteúdo dinâmico, por assim dizer. O formato desses arquivos é importante, e deve seguir o formato: `ANO-MÊS-DIA-title.MARKUP`. Os [links permanentes](http://jekyllrb.com/docs/permalinks) podem ser personalizados em cada entrada (*post*), mas a data e linguagem de marcação são determinadas unicamente pelo nome do arquivo.
| `_site` | Este será o local onde o site gerado será colocado (por padrão), uma vez que o *Jekyll* o transforme. É uma boa ideia adicionar isto ao seu arquivo `.gitignore`.
| `index.html` e outros arquivos HTML, Markdown, Textile. | Desde que o arquivo tenha uma seção de prioridade YAML, este será transformado pelo *Jekyll*. O mesmo vai acontecer para qualquer arquivo `.html`, `.markdown`, `.md`, `.textile` no diretório ou diretórios não listados na raiz do seu site acima. 
| Outros arquivos/diretórios | Qualquer outro diretório e arquivo, com exceção dos listados acima - assim como diretórios `css`, `images`, arquivos `favicon.ico` e por aí em diante - serão copiados textualmente para o site gerado. Existem muitos sites que já utilizam o Jekyll, se você estver curioso para saber com se comportam, [clique aqui](http://jekyllrb.com/docs/sites). 