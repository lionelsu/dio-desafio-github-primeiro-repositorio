# Repositório do desafio de projeto da DIO sobre Git e Github

O conceito é aplicar em um repositório o progresso aprendido até aqui sobre Git e GitHub.

# Iniciando o git no computador: O que é Git?

Git é um sistema de versionamento de código distribuído, a curto modo, ele serve para registrar alterações em arquivos para que você possa lembrar das versões específicas mais tarde. 
Como o código é distribuído pode colaborar com diferentes grupos de pessoas de maneiras diferentes e ao mesmo tempo, dentro do mesmo projeto, ele pode estar em vários repositórios remotos e se, por qualquer motivo o servidor morrer, qualquer um dos repositórios de clientes podem ser restaurados de volta para outro servidor.

O Git pode ser baixado no site oficial do Git <a href="https://git-scm.com/" target="_blank">AQUI!</a>

# Criando uma Chave SSH para usar no GitHub
### Crie uma conta no GitHub antes de prosseguir

Se você for usuário de Windows, você pode clicar com o botão direito na area de trabalho e depois em *Git Bash* e digitar o comando no console:
```
ssh-keygen -t ed25519 -C email@cadastradono.github
```
Continue com *enter* para manter os locais do par de chaves como padrão e após solicitada a senha e a mesma for definida por você, navegue para a pasta em que as chaves foram salvas. Vamos usar a chave pública para associar ao GitHub. O caminho no terminal do Git deve ser assim:
```
cd /c/Users/*seunomedeuser/.ssh/
```
Após estar no diretório correto, insira:
```
cat id_ed25519.pub
```
Então o Git retornará a chave para ser usada no GitHub.
O caminho a ser seguido na página do GitHub para adicionar sua recém criada chave SSH é
**Settings > SSH and GPG keys > New SSH key > 
de um Titulo a sua Chave SSH e adicione a chave no campo KEY seguindo de > ADD SSH Key.
A chave deve ser adicionada desde o ssh-ed25519 AA54..... até o ... .com do e-mail**. 

como você ainda não saiu da do terminal e ainda está na pasta .ssh/ no Git, continue nesta pasta e digite:
```
eval $(ssh-agent -s)
```
e depois
```
ssh-add id_ed25519
```
Sim, você vai passar a chave privada para o "agente.
Isto cria uma avaliação para que o agente SSH continue rodando em plano de fundo.

# Alguns comandos básicos de interação entre o Git e o GitHub

1. Após criar um repositório no GitHub, ele já sugere que você o adicione no repositório local, ou seja, usando o Git. Esta URL fica logo a baixo em *...push an existing repository...* e o comando no Git:
```
git remote add origin https://github.com/seu/repositorio.git.io
```

2. Clonar um repositório existente no GitHub:
```
git clone git@caminho.do.ssh.github.io
```
precisa copiar caminho SSH em "<Code>" no repositório do GitHub

3. **Empurrar** commits para o GitHub:
```
git push origin master (ou main)
```

4. **Puxar** commits do GitHub:
```
git pull origin master (ou main)
```

Sempre que algo for alterado no projeto (via sua máquina local) você vai rodar os seguintes comandos:
```
git add . (ou *)
git commit -m "sua mensagem"
git push origin main
```

links úteis:
mais comandos úteis do Git: https://github.com/rvieirasilva529/dio-desafio-github

<code>Mestres da DIO, por favor avaliem se eu entendi bem o desafio compartilhando o meu progresso de aprendizado com este repositório. Caso não, me informem que eu darei meu melhor para realizar as correções necessárias.</code>
