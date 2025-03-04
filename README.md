# linux-alias-tutorials
Um repositório com tutoriais simples e práticos para criar aliases que otimizam o uso do terminal no Linux.
---
# 1) Criando um Alias para Listar Diretórios do PATH Linha por Linha no Linux:

**Introdução:**

O PATH é uma variável de ambiente que armazena os diretórios onde o shell busca executáveis. Às vezes, pode ser útil visualizar os diretórios contidos no PATH organizados linha por linha. Este tutorial ensina como criar um alias para isso utilizando o comando `tr`.

**Pré-requisitos:**

- Um sistema operacional baseado em Linux.
- Familiaridade básica com o terminal.
- Um editor de texto como nano, vim, ou qualquer outro editor de sua preferência.

Passo 1: Verifique o PATH Atual digitando o comando abaixo no terminal do Linux</br>
```sh
echo $PATH
```

A saída será uma lista de diretórios separados por ":". Nosso objetivo é transformar esses diretórios em uma lista exibida linha por linha.

**Passo 2: Teste o Comando no Terminal**</br>
O comando que utilizaremos para formatar o PATH é:</br>
```sh
echo $PATH | tr ':' '\n'
```

- echo $PATH: Imprime o conteúdo da variável PATH.
- |: O operador pipe passa a saída do comando anterior como entrada para o próximo comando.
- tr ':' '\n': Substitui os caracteres : por quebras de linha (\n).

Execute o comando acima no terminal para confirmar que ele funciona como esperado.</br>

**Passo 3: Criando o Alias**

Para evitar digitar o comando completo toda vez, você pode criar um alias.
1) Abra o arquivo de configuração do shell:

   Para usuários do Bash, o arquivo geralmente é o `~/.bashrc ou ~/.zshrc`. Abra-o com seu editor preferido:
   ```sh
   nano ~/.bashrc
   nano ~/.zshrc
   ```

2) Adicione o alias ao final do arquivo:
   No editor, adicione a seguinte linha:
   ```sh
   alias mypath='echo $PATH | tr ":" "\n"'
   ```

3) Salve e feche o arquivo:
   No nano, pressione `Ctrl+O` para salvar e `Ctrl+X` para sair.

4) Recarregue o arquivo de configuração:
   Para aplicar as alterações sem reiniciar o terminal, execute:
   ```
   source ~/.bashrc ou
   source ~/.zshrc

   ```
**Passo 4: Use o Alias**
Agora, você pode usar o alias `mypath` para listar os diretórios do PATH linha por linha:</br>
```sh
mypath
```

A saída será semelhante a esta:

```
/usr/local/bin
/usr/bin
/bin
/usr/local/sbin
/usr/sbin
/sbin
```


   




