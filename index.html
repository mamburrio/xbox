import time
import json
import re
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from webdriver_manager.chrome import ChromeDriverManager
from selenium.common.exceptions import NoSuchElementException

def obtener_juegos():
    # --- Configuración del Navegador Headless (Invisible) ---
    options = webdriver.ChromeOptions()
    options.add_argument('--headless') 
    options.add_argument('--no-sandbox')
    options.add_argument('--disable-dev-shm-usage')
    
    driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=options)
    
    # URL de Búsqueda: Xbox Keys, Precio < 20, Regiones (Global, AR, US, TR).
    url = "https://www.eneba.com/store/games?drm[]=xbox_one_and_series_x_s_key&page=1&price[]=0&price[]=20&regions[]=global&regions[]=argentina&regions[]=united_states&regions[]=turkey&types[]=game"
    
    driver.get(url)
    time.sleep(7) # Espera a que la página cargue completamente
    
    juegos_data = []
    
    # --- Extracción de Datos y Lógica ---
    items = driver.find_elements(By.CSS_SELECTOR, "div.pFaGHa") 
    
    for item in items:
        try:
            # Extracción básica
            titulo = item.find_element(By.CSS_SELECTOR, "span.YLosEL").text
            imagen = item.find_element(By.TAG_NAME, "img").get_attribute("src")
            link = item.find_element(By.TAG_NAME, "a").get_attribute("href")
            
            # 1. Extracción y Limpieza del Precio Original
            precio_texto = item.find_element(By.CSS_SELECTOR, "span.L5ErLT").text
            precio_float = float(re.sub(r'[^\d.]', '', precio_texto)) # Convierte el texto (ej: '$4.59') a número (4.59)
            
            # 2. Lógica de Precios: Sumar los $3.00 de comisión/ganancia
            PRECIO_COMISION = 3.00
            precio_final = round(precio_float + PRECIO_COMISION, 2)
            
            juegos_data.append({
                "titulo": titulo,
                "precio_original": precio_float,
                "precio_venta": precio_final,
                "imagen": imagen,
                "link_compra": link,
                "plataforma": "Xbox" 
            })
            
        except NoSuchElementException:
            continue
        except Exception as e:
            continue

    driver.quit()
    
    # --- Guardar Resultado en JSON ---
    with open('catalogo.json', 'w', encoding='utf-8') as f:
        json.dump(juegos_data, f, ensure_ascii=False, indent=4)
        print("Catálogo 'catalogo.json' actualizado exitosamente.")

if __name__ == "__main__":
    obtener_juegos()