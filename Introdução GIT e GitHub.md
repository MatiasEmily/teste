## GIT

**Windows**: shell  
**Unix**: bash (OSs Linux e Apple)  
**SHA1**: Secure Hash Algorithm
Encriptação alfanumérica de identificação única de 40 dígitos

### ESTRUTURA DO GIT

Arquivos rastreados pelo GIT (Tracked): Unmodified (pode ser removido), Modified, Staged (commita, retorna para unmodified)  
Arquivos não rastreados: Untracked

1. **Ambiente de desenvolvimento**  
Working directory: diretório de trabalho não modificado  
Staging area: cria snapshots de versões  
Local repository: composto por commits, que serão enviadas para repositório remoto

2. **Servidor**  
Remote repository

### Objetos Fundamentais

**Blob**: metadados, tipo, tamanho, \o, conteúdo do arquivo, sha1  
**Tree**: Armazenam blobs, metadados, \o, aponta para arquivos ou árvores, sha1  
**Commit**: Armazenam trees, parente, autor, mensagem, timestamp; o SHA1 desse commit é o hash de toda essa informação

**Exemplo no Git:**

1. `echo 'conteudo' | git hash-object --stdin`
2. `chaveSHA1de40digitos`
3. `echo -e 'blob 9\0conteudo' | openssl  sha1`
4. `chaveSHA1de40digitos`

## Graphic user interface (GUI)

## Command line interface (CLI)

### Comandos:

- Listar pastas (dir, ls, ls -a)
- Buscar diretório com change direct (cd, cd /)
- Retroceder pasta (cd ..)
- Limpar terminal (cls, clear ou ctrl+l)
- Autocompletar texto (tab)
- Criar pastas, make directory (mkdir)
- Criar arquivo (echo hello > hello.txt)
- Deletar arquivos (del nomedapasta)
- Mover arquivo (mv arquivo.ext ./pasta/)
- Acessar últimos comandos (seta para cima)
- Deletar pasta, remove directory (rmdir, rm)

**Flags**: complementos que acrescentam, modificam formato de comandos  
Windows: `rmdir /S /Q`  
Bash: `rm -rf` (recursive force, apaga tudo interno, e força confirmação)

#### Criação de chave SSH no GIT Bash

1. `ssh-keygen -t ed25519 -c emailpadrao@dogithub.com`
2. Escolha senha
3. Chaves encriptadas privada e pública geradas em local determinado

Visualizar conteúdo de arquivo:  
`$ cat chavepublica.pub`  
copiar código, para registrar chave pública SSH no GitHub

Gerar agent no CLI:  
`eval $(ssh-agent -s)`  
`ssh-add chaveprivada`

Clonar repositório:  
`git clone chaveSSHdodiretorionoGitHubclonavel`  
`yes`

### Token de acesso pessoal

Serve como senha em logins do GitHub usado em protocolos HTTPS. O token gerado não poderá ser visto novamente, é importante salvá-lo em lugar seguro.  
Site do GitHub > Developer settings > Personal access tokens > Generate new token

### Comandos no GIT

Inicialização do Git para repositório (git init):  
Registro de autor no Git  
`git config --global "seuemail@email.com"`  
`git config --global user.name Nome`

Adicionar commit inicial  
`git add *`  
`git commit -m "Commit inicial 1.0"`

Adicionar todas modificações do repositório local para Staged  
`git add .`

Criar commit  
`git commit -m "Mensagem explicando atualização"`

Monitorar status do diretório  
`git status`

Adicionar atualização para Staged  
`git add nomearq.ext pasta/`

Restaurar da área de Staged  
`git restore --staged nomearq.ext`

Adicionar origem para "empurrar" no repositório do GitHub (origin é o apelido usado para evitar repetição de digitação):  
`git remote add origin http://github.com/SeuGit/linkdorepositorio.git`

Lista repositórios cadastrados  
`git remote -v`

Empurrar de repositório local para remoto (branch master)  
`git push origin master`

Puxa conteúdo do repositório  
`git pull origin master`

Clonar um repositório alheio  
`git clone https://github.com/Repositorio/Pastadele.git`

### Tipos de conflitos comuns

**Merge conflicts**: Sincronização de alterações diferentes em mesma linha, escolhe qual/como a alteração ficará