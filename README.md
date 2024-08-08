import speech_recognition as sr 
import webbrowser

recognizer = sr.Recognizer()
def search_google():
    with sr.Mircrophone() as source:
        print("Говорите что-нибудь...")
        audio = recognizer.listen(source)

        try:

            print("Распознание...")
            query = recognizer.recognize_google(audio, language='ru-RU')
            print(f'Вы сказали: {query}')
            search_url = f"https://www.google.com/search?q={query}"
            webbrowser.open(search_url)
        except sr.UnknowValueError:
            print("Извините, не удалось распознать речь")

search_google()
