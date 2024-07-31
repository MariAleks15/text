from collections import Counter
import re

def most_common_words(text, n=5):
    # Разбиваем текст на слова, игнорируя знаки пунктуации и пробелы
    words = re.findall(r'\w+', text.lower())
    # Используем Counter для подсчета количества вхождений каждого слова
    word_counts = Counter(words)
    # Получаем наиболее часто встречающиеся слова
    common_words = word_counts.most_common(n)
    return common_words

if __name__ == "__main__":
    text = input("Введите текст для анализа: ")
    n = int(input("Введите количество наиболее часто встречающихся слов, которые нужно вывести: "))
    common_words = most_common_words(text, n)
    print("Наиболее часто встречающиеся слова в тексте:")
    for word, count in common_words:
        print(f"{word}: {count} раз(а)")

        from collections import Counter
import re

def most_common_words(text, n=5, stop_words=None):
    """
    Возвращает n наиболее часто встречающихся слов в тексте.
    
    Параметры:
    text (str): Входной текст для анализа.
    n (int): Количество наиболее часто встречающихся слов для вывода (по умолчанию 5).
    stop_words (set): Набор стоп-слов для исключения из анализа (по умолчанию None).
    
    Возвращает:
    list: Список кортежей (слово, количество).
    """
    if stop_words is None:
        stop_words = set()

    # Разбиваем текст на слова, игнорируя знаки пунктуации и пробелы
    words = re.findall(r'\w+', text.lower())
    # Фильтруем стоп-слова
    filtered_words = [word for word in words if word not in stop_words]
    # Используем Counter для подсчета количества вхождений каждого слова
    word_counts = Counter(filtered_words)
    # Получаем наиболее часто встречающиеся слова
    common_words = word_counts.most_common(n)
    return common_words

if __name__ == "__main__":
    try:
        text = input("Введите текст для анализа: ")
        n = int(input("Введите количество наиболее часто встречающихся слов, которые нужно вывести: "))
        
        # Пример набора стоп-слов, можно дополнить по необходимости
        stop_words = {'и', 'в', 'на', 'с', 'по', 'как', 'что', 'это'}
        
        common_words = most_common_words(text, n, stop_words)
        
        print("Наиболее часто встречающиеся слова в тексте:")
        for word, count in common_words:
            print(f"{word}: {count} раз(а)")
    
    except ValueError:
        print("Ошибка: введите корректное число для количества слов.")

        from collections import Counter
import re

def most_common_words(text, n=5, stop_words=None):
    """
    Возвращает n наиболее часто встречающихся слов в тексте.
    
    Параметры:
    text (str): Входной текст для анализа.
    n (int): Количество наиболее часто встречающихся слов для вывода (по умолчанию 5).
    stop_words (set): Набор стоп-слов для исключения из анализа (по умолчанию None).
    
    Возвращает:
    list: Список кортежей (слово, количество).
    """
    if stop_words is None:
        stop_words = set()

    # Разбиваем текст на слова, игнорируя знаки пунктуации и пробелы
    words = re.findall(r'\w+', text.lower())
    # Фильтруем стоп-слова
    filtered_words = [word for word in words if word


