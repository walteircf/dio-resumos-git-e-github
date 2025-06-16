
# DIO | Resumos Git e Github

Repositório para armazenar resumos do curos de versionamento de código com git e Github. [Digital Innovation One](https://www.dio.me/)

## 📚 Documentação
- [Documentação Git](https://git-scm.com/doc)
- [Documentação GitHub](https://docs.github.com/)

## Índice de Aulas

| Aulas | Resumos |
|-------|---------|
|Gravando alterações no Repositório Local|[Resumo](./resumos/aula%2001.md)

## 🖥️ Resumos das Aulas

Inicie o repositório local
```
$ git init
```
após criar o repositório no Github (sem inicializa-lo), utilizar o comando abaixo para vincular o repositório local ao repositório remoto do GitHub:
```
$ git remote add origin URL/SSH
```
e em seguida criar o branch principal
```
$ git branch -M main
```
Após esses passos, se por acaso for um repositório novo, adicionar um arquivo com os comandos
```
$ touch (para criar arquivos vazios. Ex: .gitignore)
```
ou 
```
$ echo "texto exemplo" > exemplo.md (para gravar texto dentro de um arquivo)
```
É possível verificar o rastreio do Git em relação aos arquivos do repositório através do comando
```
$ git status
```
Em seguida, utilizar o comando
```
$ git add .
```
Para adicionar os arquivos e modificações para a área de preparação. Para em seguida utilizar o comando para sincronizar os arquivos e pastas com o Git:
```
$ git commit -m "commit exemplo"
```
Após realizar o commit é possível utilizar o comando:
```
$ git push -u origin main
```
para subir o repositório local para o repositório remoto.

Para verificar os commits realizados e quem os fez, basta utilizar o comando:
```
$ git log (Para um registro completo com todas as informações)
```
ou
```
$ git log --oneline (Para um registro resumido apenas com o codigo do commit e o comentario)
```


## Remover repositório e desfazer alterações

Para remover um repositório criado em uma pasta, é possível utilizando o comando 
```
$ rm -rf (remove recursivamente e à força)
```
Para restaurar mudanças indesejadas:
```
$ git restore NOME-DO-arquivo
```
Para alterar o comentário do ultimo commit, é possivel utilizando o comando:
```
$ git commit --amend -m "Novo comentário"
```
Outra alternativa é utilizar:
```
$ git commit --amend
```
para entrar no VIM. Apertar o "i" para poder inserir e editar a mensagem.

Para sair, basta apertar "ESC", apertar o botão ":", seguido de "w" para escrever e "q" para sair.

Se por acaso quiser mudar o editor para outro mais "amigável", é só rodar o seguinte comando:
```
$ git config --global core.editor "notepad"("vim" para retornar)
```
Assim, alteramos o editor para o notepad do windows.

Se quiser desfazer o ultimo commit:
```
$ git reset --soft 'HASH do commit que deseja retornar' (pega os arquivos do commit "apagado" e coloca na área de preparação)
$ git reset --mixed HASH (pega os arquivos do commit "apagado" e coloca na árvore de trabalho "Untracked", para adicionar na área de preparação)
$ git reset --hard HASH (desfaz todos os arquivos do commit)
```
Para ter um histórico detalhado das alterações:
```
$ git reflog
```
Para remover arquivos da área de preparação, é possivel utilizar o comando "reset" passando o nome do arquivo, ou:
```
$ git restore --staged ARQUIVO A SER REMOVIDO
```

## Enviando e baixando alterações com o repositório remoto

Após criar o repositório vazio no Github, podemos usar os seguintes comandos, caso o repositório local não tenha sido iniciado e também esteja vazio: 
```
echo "# nome da pasta" >> README.md - para criar um arquivo 
git init - para iniciar o repositório
git add README.md - para adicionar o arquivo ao Stage
git commit -m "first commit" - para adicionar o primeiro comentario
git branch -M main - para forçar a troca da nomenclatura do branch de "master" para "main", caso não tenha alterado nas configurações do Git
git remote add origin git@github.com:walteircf/dio-resumos-git-e-github.git - para linkar os repositórios remoto e local
git push -u origin main - para enviar os arquivos para o github
```
Ou, caso já tenha arquivos no repositório local e já esteja iniciado:
```
git remote add origin git@github.com:walteircf/dio-resumos-git-e-github.git
git branch -M main
git push -u origin main
```
