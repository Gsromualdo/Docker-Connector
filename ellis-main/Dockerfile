FROM python:3.13.5-alpine3.22

# Define o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copia o arquivo de requirements primeiro para aproveitar o cache do Docker
COPY ./requirements.txt /app/requirements.txt

# Instala as dependências
RUN pip install --no-cache-dir --upgrade -r /app/requirements.txt

# Copia o restante do código da aplicação
COPY . /app

# Comando para rodar a aplicação usando Uvicorn
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]
