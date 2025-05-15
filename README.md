
# Laboratory of Evolutionary Genomics

Repositório criado com o objetivo de atualizar os dados já existentes no site.




## 📁 Como clonar este projeto


No terminal, execute:

```
git clone git@github.com:SEU-USUARIO/data-labgenomics.git
```
Substitua seu-usuario pelo seu nome de usuário no GitHub.

Depois de clonar, acesse a pasta do projeto:
```
cd data-labgenomics
```

## 📌 Comandos úteis do Git
Adicionar alterações ao stage
```
git add .
```
Criar um commit com mensagem
```
git commit -m "sua mensagem de commit aqui"
```
Enviar as alterações para o repositório remoto
```
git push
```
Puxar alterações do repositório remoto. Sempre antes de iniciar a alteração execute o pull para garantir que os dados estão atualizados na última versão. 
```
git pull
```


## 🛠 Como editar os dados no JSON
Nesse exemplo, o arquivo JSON contém informações sobre pessoas vinculadas ao time, com campos como description, image, name, email e site.
```
{
  "principal": {
    "description": "...",
    "image": "...",
    "name": "...",
    "email": "...",
    "site": "..."
  },
  "posdoc_fellow": [
    {
      "description": "...",
      "image": "...",
      "name": "...",
      "email": "...",
      "site": "..."
    }
  ]
}
```

### ➕ Como adicionar uma nova pessoa (ex: outro posdoc_fellow)
1. Localize a chave "posdoc_fellow", que é uma lista (array de objetos).

2. Adicione um novo objeto no mesmo formato, separado por vírgula.
Exemplo:
```
{
  "principal": {
    "description": "...",
    "image": "...",
    "name": "...",
    "email": "...",
    "site": "..."
  },
  "posdoc_fellow": [
    {
    "description": "Texto da primeira pessoa...",
    "image": "URL da imagem",
    "name": "Nome",
    "email": "Email",
    "site": "Link do Lattes ou outro site"
    },
    {
    "description": "Texto da segunda pessoa...",
    "image": "URL da imagem",
    "name": "Novo Nome",
    "email": "novo@email.com",
    "site": "http://link.com"
    }
  ]
}
```

### ➖ Como remover uma pessoa
1. Encontre o bloco do objeto referente à pessoa que deseja remover dentro da lista posdoc_fellow.

2. Apague todo o bloco (incluindo chaves {} e a vírgula final se houver outro item após ele).
Exemplo: Antes:
```
{
  "principal": {
    "description": "...",
    "image": "...",
    "name": "...",
    "email": "...",
    "site": "..."
  },
  "posdoc_fellow": [
        {
            "name": "Pessoa A",
            ...
        },
        {
            "name": "Pessoa B",
            ...
        }
    ]
}
```
Removendo "Pessoa A":
```
{
  "principal": {
    "description": "...",
    "image": "...",
    "name": "...",
    "email": "...",
    "site": "..."
  },
  "posdoc_fellow": [
        {
            "name": "Pessoa B",
            ...
        }
    ]
}
```
⚠️ Certifique-se de manter a sintaxe JSON correta (vírgulas, colchetes, aspas etc.). Se tiver dúvidas, use um validador de JSON online. (https://jsonlint.com/)

## 🖼 Como usar imagens do Google Drive
Para exibir uma imagem hospedada no Google Drive, você precisa extrair o ID da imagem e montá-la da seguinte forma:
```
"image": "https://drive.google.com/uc?id=SEU_ID_AQUI"
```
### 🔍 Como pegar o ID da imagem no Google Drive
1. Vá até o Google Drive e clique com o botão direito na imagem desejada.

2. Clique em "Obter link".

3. Certifique-se de que o acesso está definido como "Qualquer pessoa com o link pode visualizar".

4. O link gerado será parecido com:
```
https://drive.google.com/file/d/1eeRi6BbwlAVqmsuV8z0EkxAq_2g5zSAV/view?usp=sharing

```
5. O trecho entre /d/ e /view é o ID da imagem.
Exemplo:
Neste link, o ID é:
```
1eeRi6BbwlAVqmsuV8z0EkxAq_2g5zSAV

```
### 🧩 Como montar a URL correta
Pegue o ID copiado e substitua em:
```
https://drive.google.com/uc?id=SEU_ID_AQUI

```
Exemplo final no JSON:
```
"image": "https://drive.google.com/uc?id=1eeRi6BbwlAVqmsuV8z0EkxAq_2g5zSAV"

```
