# 📚 Web Scraping de Livros com Python

## 📖 Descrição

Este projeto foi desenvolvido em Python com o objetivo de aplicar conceitos de Web Scraping para coletar informações de livros disponíveis no site **Books to Scrape**.

O sistema realiza uma requisição HTTP, interpreta o código HTML da página e extrai automaticamente informações como o nome e o preço dos livros.

---

## 🚀 Funcionalidades

- Conexão com um site utilizando Requests.
- Leitura e interpretação do HTML com BeautifulSoup.
- Coleta automática dos livros da página.
- Extração do nome de cada livro.
- Extração do preço de cada livro.
- Exibição das informações no console.

---

## 🛠 Tecnologias Utilizadas

- Python 3
- Requests
- BeautifulSoup4
- Google Colab

---

## 📂 Estrutura do Projeto

```
WebScraping.ipynb
README.md
```

---

## ▶️ Como Executar

1. Instale as bibliotecas necessárias:

```bash
pip install requests
pip install beautifulsoup4
```

2. Abra o arquivo `WebScraping.ipynb` no Google Colab ou Jupyter Notebook.

3. Execute todas as células.

---

## 💻 Trecho do Código

```python
import requests
from bs4 import BeautifulSoup

url = "https://books.toscrape.com"

resposta = requests.get(url)

site = BeautifulSoup(resposta.text, "html.parser")

informacoes = site.find_all("article", class_="product_pod")

for livro in informacoes:
    nome = livro.h3.a["title"]
    preco = livro.find("p", class_="price_color").text.strip()

    print(nome)
    print(preco)
```

---

## 📊 Resultado Esperado

Ao executar o projeto, o programa exibe no terminal uma lista contendo:

- Nome do livro
- Preço

Exemplo:

```
A Light in the Attic
£51.77

Tipping the Velvet
£53.74

Soumission
£50.10
```

---

## 👨‍💻 Integrantes

- Arthur Felipe Rodrigues


---

## 📚 Disciplina

Desenvolvimento Rápido de Aplicações em Python
