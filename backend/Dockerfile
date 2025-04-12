FROM python:3.12.10

# Устанавливаем рабочую директорию
WORKDIR /usr/src/app

# Обновляем pip
RUN pip install --upgrade pip

# Копируем файл зависимостей и устанавливаем их
COPY ./requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# copy entrypoint.sh
COPY ./entrypoint.sh .
RUN sed -i 's/\r$//g' /usr/src/app/entrypoint.sh
RUN chmod +x /usr/src/app/entrypoint.sh

# copy project
COPY . .

EXPOSE 8000

# run entrypoint.sh
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]