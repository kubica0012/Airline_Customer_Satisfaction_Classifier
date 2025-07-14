# Klasyfikator predykcji zadowolenia klientów linii lotniczych ✈️
Projekt skupia się na przewidywaniu satysfakcji klientów linii lotniczych przy użyciu nadzorowanych algorytmów uczenia maszynowego. Zbiór danych zawiera różne cechy dotyczące usług na pokładzie i poza nim, a celem jest klasyfikacja, czy pasażer jest zadowolony, czy neutralny/niezadowolony.
## Jak uruchomić
1. Prześlij pliki `train.csv` i `test.csv` do swojego środowiska (projekt powstał w Google Colab)  
2. Uruchom wszystkie komórki w notatniku  
3. Modyfikuj lub rozbudowuj klasyfikatory i wizualizacje według potrzeb

## Zbiór danych  
Airline Passenger Satisfaction z Kaggle: https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction  
Zbiór danych składa się z dwóch plików: `train.csv` oraz `test.csv`. 

### Kluczowe cechy:  
- Usługa Wi-Fi na pokładzie  
- Odprawa online  
- Komfort siedzenia  
- Przestrzeń na nogi  
- Obsługa bagażu  
- Rozrywka pokładowa  
- Czystość  
- Jedzenie i napoje  
- Lokalizacja bramki

Kolumna docelowa to:  
- `satisfaction`: z wartościami `satisfied` lub `neutral or dissatisfied`.

## Przetwarzanie wstępne  
- Połączono pliki `train.csv` i `test.csv` w jeden plik `CombinedLab.csv`  
- Usunięto brakujące dane  
- Usunięto niepotrzebne kolumny takie jak `id` oraz `Unnamed: 0`  
- Stworzono dwie nowe cechy:  
  - `avg_rating`: średnia ocen wszystkich usług  
  - `avg_rating_services_on_board`: średnia ocen usług na pokładzie  

## Kodowanie i skalowanie  
- Cechy kategoryczne zakodowano za pomocą **OneHotEncoder** z pakietu `category_encoders`  
- Dane zostały znormalizowane przy pomocy **StandardScaler** oraz **RobustScaler**  
- Zredukowano wymiarowość danych za pomocą **PCA** do celów wizualizacji  

## Modele  

### 1. Naive Bayes (GaussianNB)  
- Trenowany na skalowanych cechach  
- Dokładność (zbiór testowy): ~56,3%  
- ROC AUC: ~0,6352  
- Walidacja krzyżowa ROC AUC (5-krotna): ~0,6407  
- Metryki ewaluacyjne: dokładność, precyzja, recall, macierz pomyłek, krzywa ROC  

### 2. Drzewo decyzyjne  
- Trenowane na pełnym zbiorze cech oraz na zbiorze cech ograniczonym do usług na pokładzie  
- Strojenie parametrów: `max_depth`, `min_samples_leaf`, `min_samples_split`  
- Wizualizacja za pomocą `Graphviz`  

## Metryki oceny  
- Dokładność  
- Dokładność bazowa (Null Accuracy)  
- Macierz pomyłek  
- Raport klasyfikacji  
- Krzywa ROC  
- Wskaźnik ROC AUC  
- Walidacja krzyżowa (10-krotna)  
- Histogram prawdopodobieństw predykcji  

## Narzędzia i biblioteki  
- Python (Google Colab)  
- Pandas, NumPy, Matplotlib, Seaborn  
- scikit-learn (PCA, Naiwny Bayes, Drzewo Decyzyjne, metryki)  
- category_encoders  
- graphviz  

Projekt został opracowany w ramach kursu na studiach.
