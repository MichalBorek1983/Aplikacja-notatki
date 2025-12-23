# 🎙️ Audio-Notatki – Twój Inteligentny Asystent

> **Aplikacja wykorzystująca AI do zamiany mowy na tekst i generowania podsumowań.**

![Status](https://img.shields.io/badge/Status-Development-yellow)
![Python](https://img.shields.io/badge/Python-3.9+-blue)
![OpenAI](https://img.shields.io/badge/AI-Whisper%20%26%20GPT-green)
![Streamlit](https://img.shields.io/badge/Frontend-Streamlit-red)

## 📄 O Projekcie
**Aplikacja-notatki** to narzędzie stworzone w celu automatyzacji procesu robienia notatek. Zamiast ręcznie zapisywać spotkania, pomysły czy wykłady, użytkownik może po prostu mówić, a sztuczna inteligencja zajmie się resztą.

Projekt demonstruje praktyczne zastosowanie modeli **OpenAI (Whisper)** do przetwarzania danych nieustrukturyzowanych (audio) oraz **LLM (GPT)** do analizy tekstu.

### 🔴 Problem
Notatki głosowe są szybkie do nagrania, ale trudne do przeszukiwania. Odsłuchiwanie godzin nagrań, aby znaleźć jeden fragment, jest nieefektywne.

### 🟢 Rozwiązanie
Aplikacja rozwiązuje ten problem w trzech krokach:
1.  **Transkrypcja:** Zamienia nagranie audio na tekst z wysoką dokładnością (nawet w języku polskim).
2.  **Synteza:** Model językowy analizuje treść i tworzy zwięzłe podsumowanie (Summary).
3.  **Akcja:** Wyciąga z nagrania listę zadań do wykonania (Action Items).

---

## ⚙️ Kluczowe Funkcjonalności
* **Upload plików Audio:** Obsługa formatów `.mp3`, `.wav`, `.m4a`.
* **Transkrypcja AI:** Wykorzystanie modelu Whisper (przez API OpenAI) dla najlepszej jakości rozpoznawania mowy.
* **Inteligentne Podsumowania:** Automatyczne generowanie notatki ze spotkania przy użyciu GPT-3.5/GPT-4.
* **Eksport:** Możliwość pobrania gotowej notatki jako plik tekstowy.

---

## 🛠️ Stack Technologiczny

### AI & Backend
* **Python:** Logika aplikacji.
* **OpenAI API (Whisper):** Silnik Speech-to-Text.
* **OpenAI API (ChatCompletion):** Silnik NLP do streszczania tekstu.

### Frontend
* **Streamlit:** Interfejs użytkownika pozwalający na szybką interakcję z modelami AI.

---

## 🖥️ Jak uruchomić lokalnie?

1.  **Sklonuj repozytorium:**
    ```bash
    git clone [https://github.com/MichalBorek1983/Aplikacja-notatki.git](https://github.com/MichalBorek1983/Aplikacja-notatki.git)
    cd Aplikacja-notatki
    ```

2.  **Zainstaluj zależności:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Skonfiguruj klucz API:**
    Utwórz plik `.streamlit/secrets.toml` lub `.env` i dodaj swój klucz OpenAI:
    ```toml
    OPENAI_API_KEY = "sk-twoj-klucz-tutaj"
    ```

4.  **Uruchom aplikację:**
    ```bash
    streamlit run app.py
    ```

---
*Autor: Michał Borek*