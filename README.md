# reconocimientoplacas

Detector de Placas Vehiculares desde Video
Este script en Python utiliza OpenCV, NumPy y Pytesseract para detectar y extraer el texto de las placas vehiculares en un video previamente grabado. El sistema identifica la zona de interés (la placa), procesa la imagen, la convierte a escala de grises, binariza y finalmente extrae el texto utilizando OCR.

📦 Requisitos
Asegurece de tener los siguientes paquetes instalados:

pip install opencv-python numpy pillow pytesseract
Configuración Adicional
Debe tener instalado Tesseract OCR en su sistema, y configurar su ruta correctamente:

pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"

📹 Video de Entrada
El script usa un archivo de video llamado video14.mp4. Puede reemplazarlo con cualquier video de su elección, solo asegúrece de cambiar la línea:

cap = cv2.VideoCapture('video14.mp4')

📊 Flujo de Procesamiento
Lectura de Fotogramas: Se extraen los frames uno a uno.
Definición de Zona de Interés: El script dibuja un rectángulo en la región central, donde se espera encontrar la placa.

Procesamiento de la Imagen:
Conversión a matrices de canales de color (BGR).
Diferencia entre canales (detectar posibles áreas con texto).
Binarización (umbral).
Detección de contornos.
Extracción de la Placa: Se recorta la placa detectada.
OCR: Se procesa la imagen de la placa y se extrae el texto usando Tesseract.
Visualización: El texto detectado se muestra sobre el video en tiempo real.

⚙️ Configuración de Tesseract
Si tiene Tesseract instalado en otra ruta, debe ajustar esta línea:

pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"

▶️ Ejecución
Para ejecutar el script, use:

python Placas.py
