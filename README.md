# 🎙️ Audio Notatki

Aplikacja Streamlit do nagrywania notatek głosowych, ich transkrypcji i wyszukiwania po znaczeniu (wyszukiwanie semantyczne).

![Status](https://img.shields.io/badge/Status-Prototype-yellow)
![Python](https://img.shields.io/badge/Python-3.9+-blue)
![Streamlit](https://img.shields.io/badge/Frontend-Streamlit-red)

## Jak to działa

1. Nagrywasz notatkę w przeglądarce (`streamlit-audiorecorder`).
2. Whisper (`whisper-1`) zamienia nagranie na tekst, który możesz poprawić przed zapisem.
3. Zapisana notatka dostaje embedding (`text-embedding-3-large`, 3072 wymiary) i trafia do kolekcji `notes` w bazie wektorowej Qdrant (podobieństwo kosinusowe).
4. Zakładka wyszukiwania zwraca 10 notatek najbliższych znaczeniowo do zapytania, razem z wynikiem podobieństwa. Bez zapytania pokazuje 10 notatek z bazy.

Dzięki temu nie trzeba pamiętać dokładnych słów: zapytanie "składniki na naleśniki" może znaleźć notatkę z listą zakupów.

## Konfiguracja

* `OPENAI_API_KEY`: z pliku `.env` albo wpisany w aplikacji.
* `QDRANT_URL` i `QDRANT_API_KEY`: z pliku `.env` albo ze `st.secrets` (Streamlit Community Cloud).
* Do przetwarzania audio potrzebny jest `ffmpeg` (lista pakietów systemowych w `packages.txt`).

## Uruchomienie

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Ograniczenia

* To prototyp: brak automatycznych podsumowań i wyciągania zadań (wcześniejszy opis tego repozytorium je zapowiadał, ale kod ich nie zawiera).
* Brak edycji i usuwania zapisanych notatek.

*Autor: Michał Borek*
