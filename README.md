# Desafio Git e GitHub DIO
Em participação do programa **Potência Tech iFood - Desenvolvimento de Jogos**, na plataforma [DIO](https://www.dio.me/ "Plataforma DIO"), este é um desafio de projeto proposto pelo programa, onde devo colocar minhas anotações das aulas de Git e GitHub neste repositório, as anotações se encontrarão neste arquivo.

## Configurando o Git

Primeiramente, digita-se `git config` e então vê -se todas as opções, dentre elas, existem três principais, global, system e local.

Na `global`, as alterações variam de usuário para usuário.

Na `system`, as alterações mudam em todos os usuários.

Na `local`, as alterações variam de repositório para repositório.

E então, chegamos aos comandos:

`git config —global user.name “seunome”`

`git config —global user.email seuemail@exemplo.br`

Sendo assim para alterar, mas para visualizar é só digitar:

`git config --global user.name`

`git config --global user.email`

Para alterar o nome padrão dos branchs é só digitar:

`git config --global init.defaultBranch nomedobranch`

> [!IMPORTANT]
> Para clonar repositórios ou empurrar novos dados para um, precisamos de credenciais, mas desde 2021, não se usa mais senha, restando agora o método pelo token, que é o mais fácil e prático, e o método com uma chave ssh.

**Método Token**

Se cria uma chave token classic na plataforma web do [GitHub](https://github.com/ "Plataforma GitHub"), e então quando se for clonar ou enviar dados, se usa essa credencial, esse token, gerado somente uma vez, e que após a saída da pagina onde ele fica, por motivos de segurança, ele some, pois é para ser usado somente em quanto foi criado, mas entretanto todavia, para não ficar criando infinitos tokens, utilizando essa linha de código:

`git config —global credential.helper store`

Na próxima vez que o token for utilizado ele será salvo e não será necessário a repetição, mas se você divide o computador com alguém e tudo mais, pode colocar esse token em cache, trocando a palavra `store` por `cache`, fazendo com que as credenciais sumam em cinco minutos.

## Criando Repositórios Locais

Para criar repositórios locais, primeiramente criamos uma pasta, e dentro dela, no git bash digitamos:
```
git init
git branch -M main
git remote add origin URL
```

não sendo necessário modificar o config do git, já que ele já foi configurado.

## Clonando Repositórios

Para clonar repositórios, que é a maneira mais fácil, utiliza-se:

`git clone URL NomeDaPasta`

Sendo o nome da pasta uma parte opcional, pois a pasta vem nomeada com o nome do repositório.

Dessa forma, já vai vir com o origin setado, não necessitando criar a localização do repositório remoto, no caso o repositório do GitHub.

## Enviando arquivos

Para se mandar arquivos, primeiro se usa:

`git add NomeDoArquivo` para arquivos específicos e `git add .` para todos os novos arquivos, usando como base o commit anterior.

Arquivos novos serão aqueles que não estavam no repositório remeto até o commit anterior, também entram arquivos alterados.

Para se dar commits, que são descrições das atualizações, se usa:

`git commit -m “”`

Para mostrar o histórico de commits se usa:

`git log`

Ou para um mais detalhado:

`git reflog`

Mas e se caso eu escrever errado o commit?

`git commit —amend -m “”`

Mas e se eu acabar já tendo enviado um arquivo, mas acabar excluindo seu conteúdo?

`git restore NomeDoArquivo`

Fazendo com que o arquivo volte ao estado do ultimo commit.

Mas e se eu tiver enviado um commit errado, atualizando arquivos incompletos ou errados, como faço?

`git reset —soft CódigoHash` ou `git reset —mixed CódigoHash` ou `git reset —hard CódigoHash`

O `soft` traz de volta os arquivos do commit anterior mas já adicionados pelo git add.

O `mixed` traz de volta os arquivos do commit anterior mas sem adicionados pelo git add. OBS: é o padrão, git reset leva a esse comando.

O `hard` retorna ao primeiro commit só que com os novos arquivos apagados.

O git reset também serve para arquivos específicos.

Agora, chegou a hora de mandar, para isso, utiliza-se:

`git push origin main`

## Sobre Branchs

Branchs são ramificações separadas, em um jogo, esse versionamento seria por exemplo, uma mecânica não finalizada e que não pode ser adicionada ao projeto original.

Ou seja, as alterações de uma ramificação não alteram na branch principal a não ser que seja mesclada.

Para criar branchs e trocar na mesma hora se utiliza:

`git checkout -b NomeDaBranch`

Para trocar branchs se usa:

`git checkout NomeDaBranch`

Para trocar branchs se usa:

`git checkout NomeDaBranch`

Para listar branchs existentes:

`git branch`

Para listar o ultimo commit de cada branch:

`git branch -v`

Para mesclar branchs ao principal:

`git merge NomeDoBranch`

Para remover um branch sem uso, um abandonado ou já mesclado:

`git branch -d NomeDoBranch`

Muito cuidado com os conflitos que podem acontecer pelo trabalho em equipe, por exemplo seu amigo enviar um arquivo para o repositório remoto que ainda não está no seu local, se você tentar dar um push no seu local para remoto, irá dar conflito pois existem arquivos no remoto que não existem no local, sendo necessário o:

`git pull`

Só que agora, se os arquivos repetidos tiverem mesmo nome, ele vai pedir para você decidir qual alteração manter, a sua ou a do seu amigo, ficando explicito no conteúdo do arquivo as duas versões para você escolher uma.

> [!NOTE]
> O git pull chama os arquivos existentes no remoto que não estão no local.

## Resumo

Essas foram as minhas anotações de Git e GitHub.

Para outras configurações, acessar a [Documentação](https://git-scm.com/docs/git/pt_BR "A documentação de Git").
