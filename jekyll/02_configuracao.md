# Configuração

Jekyll permite que você invente seus sites de diversas maneiras, e é graças às opções de configuração poderosas e flexíveis que isso é possível. Essas opções podem ser especificadas em um arquivo `_config.yml`, colocado no diretório raiz do seu site, ou pode ser especificado como ~~sinalizadores~~ para serem executadas no terminal com `jekyll`.

## Definições de Configuração

### Configuração Global

A tabela abaixo lista as definições disponíveis no Jekyll, e os diversos `options` (espcificado no arquivo de configuração) e `flags` (especificado no comando de linha) que o controlam.

| Definicão | Descrição | `Options` e `Flags` |
| Origem do Site | Modifique o diretório onde o Jekyll fará a leitura dos arquivos | `source: DIR` `-s --source DIR` |
| Destino do site | Modifique o diretório onde o Jekyll fará a escrita dos arquivos | `destination: DIR` `-d --destination DIR` |
| Protegido | Desabilitar plugins customizáveis. | `safe: BOOL --safe` |
| Exclusão | Remove diretórios e/ou arquivos da conversão | `exclude: [DIR, FILE, …]` |
| Inclusão | Força a inclusão de diretórios e/ou arquivos na conversão. `htaccess` é um bom exemplo, já que as *dotfiles* são excluídas por padrão. | `include: [DIR, FILE, …]` |
| Fuso horário | Defina o fuso horário para a geração de site. Isso define a variável de ambiente `TZ`, que Ruby usa para lidar com o tempo e data de criação e manipulação. Qualquer entrada da [IANA Time Zone Database](http://en.wikipedia.org/wiki/Tz_database) é válida, por exemplo, `America/New_York`. O valor padrão é o definido no seu sistema. | `timezone: TIMEZONE` |

### Opções de comandos para construção

**Atualização automática** | Ativa a atualização automática do site quando os arquivos forem modificados. | `-w --watch` |
**Configuração** | Especifíca um arquivo de configuração. Sobrescreve definições em em `_config.yml`. | `--config FILE` |
**Rascunhos** | Coloca o post em modo rascunho. | `--drafts` |
**Post Agendado** | Publica um post em uma data futura/agendada. | `future: BOOL` `--future` | 
**Posts Relacionados** | Produz um índice de posts relacionados | `lsi: BOOL` `--lsi` |
**Posts Limitados** | Limita o número de posts a serem publicados. | `limit_posts: NUM` `--limit_posts NUM` |

### Opções de comandos do servidor

Além das opções abaixo, sub-comando `serve` aceita qualquer das opções para os sub-comandos `build`, que são então aplicados para a compilação local, que ocorre logo antes de seu site ~~ser servido~~.

| Porta do servidor local | direciona para uma porta definida | 
| Hostname do servidor local | direciona para o hostname definido | 
| URL Base | Executa o website a partir da URL base definida | 


