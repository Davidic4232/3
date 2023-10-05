import requests
from bs4 import BeautifulSoup
import datetime


url = "https://example.com/your-weather-page"


response = requests.get(url)


if response.status_code == 200:
    # Розпарсювання вмісту сторінки з використанням BeautifulSoup
    soup = BeautifulSoup(response.text, 'html.parser')

    # Отримання температурних даних (припустимо, що температура знаходиться в елементі з ідентифікатором "temperature")
    temperature_element = soup.find(id="temperature")
    температура = float(temperature_element.text.strip().split()[0])  # Парсимо температуру і конвертуємо її в число

    # Отримання поточної дати і часу
    дата_і_час = datetime.datetime.now()

    
    дата

    conn = sqlite3.connect("погода.db")
    cursor = conn.cursor()
    cursor.execute("INSERT INTO погода (дата_і_час, температура) VALUES (?, ?)", (дата_і_час, температура))
    conn.commit()
    conn.close()

    
   
print(f"Дані про температуру збережено до бази даних: Дата і час: {дата_і_час}, Температура: {температура}°C")
else:
    
   
print("Помилка при запиті до веб-сайту з погодою")
