# LiterAlura
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
import requests

# URL da API Gutendex
url = "https://gutendex.com/books/"

# Fazer uma requisição GET à API
response = requests.get(url)
data = response.json()

# Verificar os dados recebidos
print(data)
import pandas as pd

# Transformar os dados em um DataFrame do Pandas
books_df = pd.DataFrame(data['results'])

# Mostrar as primeiras linhas do DataFrame
print(books_df.head())
# Verificar colunas disponíveis
print(books_df.columns)

# Exemplo: Filtrar livros em inglês
english_books = books_df[books_df['languages'].apply(lambda x: 'en' in x)]

# Mostrar os livros em inglês
print(english_books.head())
# Salvar DataFrame em um arquivo CSV
english_books.to_csv('english_books.csv', index=False)
git add .
git commit -m "Initial commit with API data fetching and processing"
git push origin main
import requests
import pandas as pd

# URL da API Gutendex
url = "https://gutendex.com/books/"

# Fazer uma requisição GET à API
response = requests.get(url)
data = response.json()

# Transformar os dados em um DataFrame do Pandas
books_df = pd.DataFrame(data['results'])

# Filtrar livros em inglês
english_books = books_df[books_df['languages'].apply(lambda x: 'en' in x)]

# Salvar DataFrame em um arquivo CSV
english_books.to_csv('english_books.csv', index=False)

print("Dados salvos em 'english_books.csv'")
