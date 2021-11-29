import pandas as pd
from urllib.request import urlopen
from bs4 import BeautifulSoup

url = 'https://alura-site-scraping.herokuapp.com/index.php'

response = urlopen(url)
html = response.read()

soup = BeautifulSoup(html, 'html.parser')

anuncio = soup.find('div', {'class': 'well card'})

infos = anuncio.find('div', {'class': 'body-card'}).findAll('p')
for info in infos:
  card[info.get('class')[0].split('-')[-1]] = info.get_text()

items = anuncio.find('div', {'class': 'body-card'}).ul.findAll('li')
items.pop()
acessorios = []
for item in items:
  acessorios.append(item.get_text().replace('► ', ''))

card['acessorios'] = acessorios

dataset = pd.DataFrame.from_dict(card, orient='index').T
dataset
