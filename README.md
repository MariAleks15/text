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
