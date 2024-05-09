# O básico
## Não se esqueça de configurar

caso o username e email não estejam configurandos:

```
git config --local user.email 49589600+Carto1a@users.noreply.github.com
git config --local user.name "Carto1a"
git config --global init.defaultbranch main
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

