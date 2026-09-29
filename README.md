Main code of parser

import requests 
from bs4 import BeautifulSoup

A_3 = 'https://books.toscrape.com/catalogue/page-1.html'

for page in range(1, 50):

 A_5 = requests.get(A_3)

 url = BeautifulSoup(A_5.text, 'lxml')

 A_9 = url.find_all('article', {'class' : 'product_pod'})

 for A_15 in A_9:

   T_1 = A_15.h3.a['title']
   A_6 = A_15.find('p', {'class' : 'price_color'}).get_text()

   print(f'Name: {T_1}')
   print(f'Price: {A_6}')
