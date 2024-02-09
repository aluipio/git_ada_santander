

# **GIT code annotations**

#############################################
##### Primeiro Projeto - passo a passo
#############################################

1. Crie uma repositório no GitHub

2. Usando terminal, entre no projeto existente em seu ambiente virtual e execute o comando abaixo para inicia o projeto: 
~~~
git init
~~~

3.1. Em seguida, adicione os arquivos de configuração para preparar o commit (. > insere todos os arquivos):
~~~
git add .
~~~

3.2. Inserir arquivo único. 
>Opcional: Adicione um arquivo readme caso não tenha iniciado o repositório com ele:
~~~
git add README.md
~~~

4. Crie um novo commit para os arquivos que irá subir para o repositório:
~~~
git commit -m "Minha Atualização"
~~~

5. Identifique o repositório em questão, utilizando a URL gerada no passo 1 com o seguinte comando:
~~~
git remote add origin URL-GERADA-PELO-PASSO-1
~~~

6. Suba os arquivos para o repositório, com o comando:
>OBS.: Autorize o upload com seu login e senha;
>OBS.: A branch <main> será o ambiente principal do projeto;
~~~
git push -u origin BRANCH
~~~

7. Pronto. Seu primeiro projeto foi armazenado no repositório virtual.

---
#############################################
##### Carregando Projeto existente.
#############################################

1. Localize a link https do projeto interessado.

2. Executo o comando a seguir para clona o projeto.
~~~
git clone URL-GERADA-PELO-PASSO-2-AQUI
~~~

---
#############################################
##### Operando BRANCHS
#############################################

1. Visualiza as branchs existentes
~~~
git branch
~~~

2. Cria uma nova branch (um dos dois comandos):
~~~
git branch BRANCH_SECUNDARIA
git checkout -b BRANCH_SECUNDARIA
~~~

3. Habilita a branch para alterações:
~~~
git checkout BRANCH_SECUNDARIA
~~~

4. Use os comandos de manuseio dentro da branch:
>Lembre de especificar a branch que deseja alterar;
~~~
git add .
git commit -m "Atualização"
git push -u origin BRANCH_SECUNDARIA
~~~

5. Retorna para a BRANCH principal (main):
~~~
git checkout main
~~~

6. Mesclar a BRANCH principal (main) com a derivada:
~~~
git merge BRANCH_SECUNDARIA
~~~

7. Faz upload das alterações:
~~~
git commit -m "Salves Atualização"
git push -u origin main
~~~

7.1. Visuzaliar o conflito do merge:
~~~
git diff <nome_branch_origem> <nome_branch_alvo>
~~~

8. Deletar branch do Git Local (um dos dois comandos):
~~~
git branch -D BRANCH_SECUNDARIA
git checkout -d BRANCH_SECUNDARIA
~~~

8. Deletar branch do GitHub:
~~~
git push origin --delete BRANCH-SECUNDARIA
~~~

9. Sobe todas as alterações:
~~~
git push
~~~

10. Reverter as alterações feitas em qualquer arquivo:
~~~
git checkout -- NOME_DO_ARQUIVO
~~~

---
#############################################
##### Outras Operações
#############################################

* Verifica verão do git
~~~
git -v
git --version
~~~

* Visualizar o status da BRANCH atual:
~~~
git status
~~~

* Para atualizar todas as informações: 
~~~
git remote update
git fetch
~~~

* Copia todas as alterações contidas do repositório REMOTO > LOCAL:
~~~
git pull
~~~

* Configura o Git no projeto:
~~~
git config user.name my-name
git config user.email my-email
~~~

* Configura o Git Global
~~~
git config --global user.name "João Silva"
git config --global user.email "exemplo@seuemail.com.br"
~~~

* Eliminar todas as alterações/commits locais e o master branch local for necessário para apontar para o histórico mais recente do servidor:
~~~
git fetch origin
git reset --hard origin/master
~~~

---
#############################################
##### Problemas no versionamento
#############################################

Desde o Release 2.9.0 12, o Git parou de permitir o merge automático de projetos que possuem históricos Git diferentes.

O erro fatal: refusing to merge unrelated histories geralmente acontece quando você tenta fazer o git pull de um repositório remoto, mas o seu repositório local possuí um histórico de commits, branches, etc, diferente do que está no repositório remoto.

Para permitir que o Git faça o merge de dois projetos com históricos diferentes, é só passar o parâmetro --allow-unrelated-histories quando for fazer o pull, assim:
~~~
git pull origin master --allow-unrelated-histories
~~~

---
###########################################################
##### Controle de link remoto
###########################################################

# Remove origin da lista remota através do comando remove: 
git remote remove origin
    
# Atualiza origin pointing URL com set-url:
git remote set-url origin [new-url]

# Renomear o manipulador origin handler para outro nome através do comando rename: 
git remote rename origin [new-name]

# Se um repositório existente ainda não tiver sido clonado e pretende estabelecer uma ligação entre o seu repositório e um servidor remoto:
git remote add origin [new-url]

---
### **Auters**:

- [Anderson Miranda](https://github.com/aluipio)

---
### **Links Úteis** {#custom-id}:

- [Atlassian](https://www.atlassian.com/br/git/tutorials/saving-changes/git-stash)
