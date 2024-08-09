▪ EXERCÍCIO – Básico sobre staging / commit:

a) No working dir, executar o comando:
echo 01 > arquivo.txt

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ echo 01 > arquivo.txt

b) Adicionar o arquivo no staging e conferir o status

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git add arquivo.txt
    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git status

    On branch main
    Your branch is up to date with 'origin/main'.

    Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
            new file:   arquivo.txt

c) Commitar o arquivo do staging com a descrição "git add example - arquivo.txt“

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git commit -m "git add example - arquivo.txt"

    [main e6752ad] git add example - arquivo.txt
    1 file changed, 1 insertion(+)
    create mode 100644 arquivo.txt    

d) Sobrescrever o conteúdo do arquivo.txt:

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ echo 02 > arquivo.txt

e) Verificar o diffing no arquivo

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git diff 

   diff --git a/arquivo.txt b/arquivo.txt
	index 9e22bcb..75016ea 100644
	--- a/arquivo.txt
	+++ b/arquivo.txt
	@@ -1 +1 @@
	-01
	+02

f) Adicionar novamente o arquivo no staging e conferir o status

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git add arquivo.txt
    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git status
    On branch main
    Your branch is up to date with 'origin/main'.

    Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
            modified:   arquivo.txt
 

g) Verificar o diffing no arquivo

	@JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git diff 
	diff --git a/arquivo.txt b/arquivo.txt
	index 9e22bcb..75016ea 100644
	--- a/arquivo.txt
	+++ b/arquivo.txt
	@@ -1 +1 @@
	-01
	+02

h) Sobrescrever o conteúdo do arquivo.txt:

	@JamesAlanRib ➜ /workspaces/exercicio01 (main) $ echo 03 > arquivo.txt

i) Verificar o diffing no arquivo

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git diff 
    diff --git a/arquivo.txt b/arquivo.txt
    index 9e22bcb..75016ea 100644
    --- a/arquivo.txt
    +++ b/arquivo.txt
    @@ -1 +1 @@
    -02
    +03

j) Fazer o restore do arquivo da área de staging e verificar o status

	@JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git restore --stage arquivo.txt
    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git status
    On branch main
    Your branch is up to date with 'origin/main'.

    nothing to commit, working tree clean

k) Realizar o commit do arquivo e verificar o log

	@JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git commit --m "commit do arquivo restaurado"
    [main 8517a53] commit do arquivo restaurado
    1 file changed, 1 insertion(+), 1 deletion(-)

l) Adicionar um arquivo gitignore com o seguinte conteúdo:
*.txt

	@JamesAlanRib ➜ /workspaces/exercicio01 (main) $ echo *.txt > gitignore
    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ ls
    README.md  arquivo.txt  gitignore
    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ cat gitignore 
    *.txt

    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git add *
    @JamesAlanRib ➜ /workspaces/exercicio01 (main) $ git commit -m "Salva todos" 
    [main c9106aa] Salva todos
    2 files changed, 2 insertions(+)
    create mode 100644 gitignore
    create mode 100644 novo.txt
