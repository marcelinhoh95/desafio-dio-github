# Git e GitHub: Anotações

## Link para Download do Git

- **Windows:** [Git - Install for Windows](https://git-scm.com/install/windows)
- **macOS:** [Git - Install for macOS](https://git-scm.com/install/mac)
- **Linux:** [Git - Install for Linux](https://git-scm.com/install/linux)

## Link para criação de cadastro no GitHub

[Sign Up GitHub](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home)

## Anotações

### O que é o Git

Git é um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas que pode registrar o histórico de edições de qualquer tipo de arquivo.

> **Sistema distribuído:** aquele que reúne vários dispositivos (computadores, servidores) que cooperam para executar tarefas e fornecer serviços como se fossem uma única máquina.

**Exemplo:** alguns livros digitais são disponibilizados no GitHub e escritos aos poucos, de forma pública.

### Características

- Criado por **Linus Torvalds**
- Projeto **Open Source**
- Sistema distribuído **seguro**

### Autenticação segura: chaves SSH ou token

O Git usa um par de chaves: **pública** e **privada**.

#### No GitHub: ativação do SSH

1. Acesse **Profile** → **Settings**
2. No menu, clique em **SSH and GPG Keys**
3. Clique em **New SSH Key**

#### No Git Bash: gerando o par de chaves

1. Gere o par de chaves:

   ```bash
   ssh-keygen -t ed25519 -C "seu_email@example.com"
   ```

   Caso seu sistema não suporte `ed25519`, use:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "seu_email@example.com"
   ```

2. Informe a senha (passphrase) para a chave quando solicitado.

3. Acesse o local da chave:

   ```bash
   cd <local da chave>
   ```

4. Liste os arquivos para verificar se a geração foi bem-sucedida:

   ```bash
   ls
   ```

5. Exiba o conteúdo da chave pública (arquivo com extensão `.pub`):

   ```bash
   cat <nome do arquivo da chave pública>.pub
   ```

6. Copie a chave pública e cole na configuração da nova chave SSH no GitHub.

7. Inicialize o SSH Agent:

   ```bash
   eval $(ssh-agent -s)
   ```

### Objetos no Git

1. **Blobs (Binary Large Objects):** armazenam o conteúdo dos arquivos (o código ou texto em si), sem metadados.
2. **Tree:** representa o diretório, mapeando os nomes dos arquivos para seus respectivos blobs e outras árvores (subdiretórios).
3. **Commit:** aponta para uma árvore raiz, registrando metadados do histórico (autor, mensagem, data) e referenciando o(s) commit(s) pai(s).
