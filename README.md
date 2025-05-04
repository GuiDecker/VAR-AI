# V.A.R (Vigilância-Ambiental-Resiliente) - Analise e Visão Computacional

Fundei o projeto VAR (Vigilância Aérea Resiliente), um projeto de visão computacional voltado para a prevenção de incêndios e localização de pessoas em grandes áreas como plantações, florestas ou regiões vulneráveis. A tecnologia emprega inteligência artificial e redes neurais treinadas para analisar imagens captadas por drones ou por câmeras fixas posicionadas estrategicamente. Ao identificar possíveis focos de incêndio, o sistema envia alertas automáticos via WhatsApp aos responsáveis, com instruções baseadas em protocolos definidos com as autoridades locais.

O VAR foi um dos 4 projetos selecionados para entrevista pelo canal Código Fonte TV, entre 24 grupos participantes. Em 2024, também integrou o NEXT 2024, o festival oficial de inovação e tecnologia da FIAP, uma das maiores instituições de ensino em tecnologia do Brasil.

**Vertente inativa do VAR.**
**Este repositório é uma versão pública mais simles projeto com YOLOv8 e um modelo treinado menor com yolo.**

Mudanças climaticas vem se tornando algo recorrente no mundo, e precisamos nos previnir.
O VAR é um projeto que foi idealizado para ajudar pessoas em areas de risco e previnir desastres naturais. O projeto constitui-se principalmente usar redes neurais em um dataset treinado aplicadas a visão computacional para fazer detecção do ambiente e chamar autoridades em riscos de desastres naturais

##  Sobre o projeto📚:
Esse projeto teve melhorias adaptadas para receber a analise de imagens e vídeos pela API de AI generativa do google, onde passará primeiramente por visões computacionais que trarão a detecção e previsão de pessoas em areas e a analise do gemini, trazendo detecção de pessoas ou animais perdidas e em areas de risco, além de trazer ações preventivas a serem tomadas para resgate

![Alt text](assets/person/person1.png) ![Alt text](assets/person/people-enchente.jpeg)

## Tecnologia/Biblioteca 💻
- **Python** utilizado no google colab
- **Ultralytcs YOLO** Versão YOLO v8
- **Gemini API**

## Suporte 👇
- Os arquivos **yolov8m.pt** e **yolov8n.pt** são os similares, a diferença é que o **v8m** é a versão intermediaria, sendo mais robusto, porém com mais tempo de execução e o **v8n** é uma versão mais leve de todas, sendo mais rápida, porém menos precisa
  
- Arquivos de imagens e vídeos estarão dentro da pasta assets caso queira adiciona-las no google colab

## Como Utilizar dentro do google colab🧩:

**Passo a passo**
### 1. Adicione o arquivo **YOLOv8m** ou **YOLOv8x** para rodar o modelo de detecção de pessoas
Lembre de passar o caminho do arquivo correto para onde adicionará esse arquivo
     
   ```bash
       model.predict(source="<CAMINHO_ARQUIVO_AQUI>", conf=0.7, save=True, show=True)
       model = YOLO("/content/yolov8n.pt")
     
       model.predict(source="<CAMINHO_ARQUIVO_AQUI>", conf=0.7, save=True, show=True)
       model.predict(source="/content/areas-de-risco.jpeg", conf=0.7, save=True, show=True)  
   ``` 
### 2. Coloque sua GOOGLE_API_KEY
  ```bash
 from google.colab import userdata
GOOGLE_API_KEY=userdata.get('GOOGLE_API_KEY')
genai.configure(api_key=GOOGLE_API_KEY)
  ``` 
### 3. Após fazer isso, o proximo codigo do google colab será o "Extração de frames do arquivo"
Na variavel video_file_name defina o caminho do arquivo que quer detectar e analisar com gemini, você pode escolher 
algum arquivo local ou hospetado, como:
**Vídeo Hospodade**
  ```bash
    video_file_name = "[.mp4](https://exemplo.com/images/teste.mp4)"
  ```
ou **Vídeo local da sua máquina**
```bash
    video_file_name = "/content/runs/detect/predict/RS_video.mp4"
  ```
