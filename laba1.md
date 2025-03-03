# Лабораторна робота 1. Ентропія джерела інформації

## 1. Технічне завдання
Розрахувати ентропію символів для заданих текстових даних, порівняти ентропію для різних мов та зробити висновки.

## 2. Інструменти
- Python (collections.Counter, math.log2)
- Тексти з відкритих джерел (Wikipedia, Project Gutenberg)

## 3. Покроковий план виконання

### КРОК 1. Ознайомлення з поняттям ентропії
- Вивчити(згадати): що таке ентропія Шеннона.
- Формула:  
    $$H(X) = - \sum_{i=1}^{n} p_i \log_2 p_i$$
- Ресурси: [Shannon's Theory Explained](https://www.youtube.com/watch?v=2s3aJfRr9gE)

### КРОК 2. Підготовка середовища
- Встановити Python 3.10+
- Завантажити тексти українською, англійською та китайською мовами.
- Зберегти файли як `ukrainian.txt`, `english.txt`, `chinese.txt`.

### КРОК 3. Реалізація функції обчислення ентропії
```python
import collections
import math

def calculate_entropy(text):
    TODO
```

### КРОК 4. Завантаження та очищення тексту
```python
def load_and_clean_text(filepath):
    TODO
```

### КРОК 5. Обчислення ентропії
```python
ukr_text = load_and_clean_text('ukrainian.txt')
eng_text = load_and_clean_text('english.txt')
chi_text = load_and_clean_text('chinese.txt')

print(f'Ентропія українського тексту: {calculate_entropy(ukr_text):.4f}')
print(f'Ентропія англійського тексту: {calculate_entropy(eng_text):.4f}')
print(f'Ентропія китайського тексту: {calculate_entropy(chi_text):.4f}')
```

### КРОК 6. Аналіз результатів
| Мова      | Ентропія (біт/символ) |
|-----------|--------------------|
| Українська | 4.85 |
| Англійська | 4.12 |
| Китайська  | 6.24 |

### КРОК 7. Оформлення звіту
**Шаблон:**  
- Мета роботи  
- Код програми  
- Вихідні дані  
- Результати (таблиця ентропій)  
- Висновки

### КРОК 8. Завантаження звіту в Google Classroom
- Формат файлу: PDF
- Назва файлу: `ЛР1_Прізвище_Група.pdf`

## Додатково: Побудова графіка ентропії залежно від розміру тексту
```python
import matplotlib.pyplot as plt

```

---

