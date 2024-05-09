# O básico
## Não se esqueça de configurar

caso o username e email não estejam configurandos:

```
git config --local user.email 49589600+Carto1a@users.noreply.github.com
git config --local user.name "Carto1a"
```

caso for usar ssh:
**TODO**
## Repositório

#### URLS
- **HTTPS**: https://github.com/username/reponame.git
- **SSH**: git@github.com:username/reponame.git

### Repositório vazio

```
echo "# INITIAL" >> README.md
git init
git add README.md
git commit -m "initial"
git branch -M main
git remote add origin [url]
git push -u origin main
```

### Repositório existente

```
git clone [url]
```

# Comandos

## init

## clone

## add

## commit

### Em qual momento fazer o commit:

- **Após concluir uma funcionalidade ou uma parte significativa do trabalho:** Quando você finalizar uma funcionalidade, uma correção de bug ou uma parte importante do seu projeto, faça um commit para registrar essas mudanças e marcar um ponto de referência no histórico do projeto.

- **Antes de iniciar uma nova tarefa ou experimento:** Antes de começar a trabalhar em uma nova tarefa ou fazer alterações significativas, faça um commit das alterações atuais para garantir que você tenha um ponto de restauração se precisar voltar atrás.

- **Quando atingir um marco significativo no projeto:** Se você alcançar um marco significativo no desenvolvimento do projeto, como o lançamento de uma versão importante ou a conclusão de uma etapa importante, faça um commit para marcar esse ponto no histórico.

- **Depois de revisar e confirmar suas alterações:** Após revisar suas alterações e confirmar que estão prontas para serem incluídas no repositório, faça um commit para enviá-las.

- **Regularmente e de forma incremental:** Faça commits regularmente e de forma incremental à medida que você avança no desenvolvimento do seu projeto. Isso ajuda a manter um histórico claro e organizado das alterações feitas ao longo do tempo.

### Como escrever uma boa mensagem no commit

[[Commit Message]]

## branch

## remote

## push

## config

## revert




