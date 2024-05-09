Lembrete de como criar e adicionar chaves ssh ao github e a outros serviços

# Lembrar

não se esqueça de checar se existe um ssh agent configurado

- ## Verificar se existe chaves no sistema

`ls -al ~/.ssh`

Ex:

```
total 16
drwxr-xr-x  2 carto1a carto1a 4096 set  6 14:45 .
drwxr-xr-x 23 carto1a carto1a 4096 set  6 14:45 ..
-rw-------  1 carto1a carto1a  176 set  6 14:45 id_rsa
-rw-r--r--  1 carto1a carto1a   41 set  6 14:45 id_rsa.pub
```

se a chave publica e privata ja existir, pule para -> 

- ## Gerar uma nova chave

Algortimo de criptografia: ed25519

`ssh-keygen -t [algortimo] -C "[nome da chave]"`

- ## Adicionar a chave ao ssh-agent

### Iniciar o ssh-agent
#### Windows
antes de adicionar a chave ao ssh-agent, é necessário iniciar o ssh-agent

`Get-Service -Name ssh-agent | Set-Service -StartupType 'Manual'`
`Start-Service ssh-agent`

#### Linux
dependendo do sistema, o ssh-agent pode ser iniciado automaticamente

### adicionar a chave ao ssh-agent

chave privada é a que não tem a extensão `.pub`
`ssh-add [caminho para a chave privada]`

- ## Adicionar a chave a um serviço

para adicionar a sua chave ssh a um serviço, é necessário copiar **TODO** o conteudo da chave publica, aquela que tem a extensão `.pub`, para o serviço desejado.

### Github

#### Segudo o github

1. No canto superior direito de qualquer página, clique na foto do seu perfil e em Configurações.

2. Na seção "Acesso" da barra lateral, clique em 🔑 Chaves SSH e GPG.

3. Clique em Nova chave SSH ou Adicionar chave SSH.

4. No campo "Title" (Título), adicione uma etiqueta descritiva para a nova chave. Por exemplo, se estiver usando um laptop pessoal, você poderá chamar essa chave de "Laptop pessoal".

5. Selecione o tipo de chave: autenticação ou assinatura. Para saber mais sobre a assinatura de commit, confira "Sobre a verificação de assinatura de commit".

6. No campo "Chave", cole sua chave pública.

7. Clique em Adicionar chave SSH.

8. Se solicitado, confirme acesso à sua conta em GitHub. Para obter mais informações, confira "Modo sudo".

#### Testando

`ssh -T git@github.com`

se o output for algo como:

```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
> Are you sure you want to continue connecting (yes/no)?
```

responda `yes`.
e se o resultado for algo como:

```
> Hi USERNAME! You've successfully authenticated, but GitHub does not
> provide shell access.
```

significa que a chave foi adicionada corretamente.


