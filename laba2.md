## Лабораторна робота 2. Моделювання джерела інформації

### 1. Технічне завдання
Створити модель стаціонарного джерела з пам’яттю 1-го порядку та згенерувати 1000 символів.

### 2. Інструменти
- Python (random.choices, numpy)

### 3. Покроковий план виконання

### КРОК 1. Ознайомлення з поняттям джерела інформації
- Вивчити, що таке джерело інформації та його моделі.
- Ознайомитися з поняттям стаціонарного джерела та джерела з пам’яттю.
- Ресурси: [Information Theory Basics](https://www.youtube.com/watch?v=XXZbg-7QpDI)

### КРОК 2. Визначення матриці ймовірностей переходів
- Обрати алфавіт (наприклад, {A, B, C, D}).
- Побудувати матрицю ймовірностей переходів між символами.

```python
import numpy as np

def generate_transition_matrix():
    matrix = np.array([[0.4, 0.3, 0.2, 0.1],
                       [0.1, 0.4, 0.3, 0.2],
                       [0.2, 0.1, 0.4, 0.3],
                       [0.3, 0.2, 0.1, 0.4]])
    return matrix
```

### КРОК 3. Генерація послідовності символів
- Використати матрицю ймовірностей для генерації 1000 символів.

```python
import random

def generate_sequence(matrix, length=1000, alphabet=['A', 'B', 'C', 'D']):
    sequence = [random.choice(alphabet)]
    for _ in range(length - 1):
        prev_index = alphabet.index(sequence[-1])
        next_symbol = random.choices(alphabet, weights=matrix[prev_index])[0]
        sequence.append(next_symbol)
    return ''.join(sequence)
```

### КРОК 4. Обчислення ентропії створеного джерела
- Використати функцію обчислення ентропії з ЛР1.

```python
from collections import Counter
import math

def calculate_entropy(text):
    frequencies = Counter(text)
    total = len(text)
    entropy = -sum((count/total) * math.log2(count/total) for count in frequencies.values())
    return entropy
```

### КРОК 5. Виконання аналізу та порівняння
- Обчислити ентропію для згенерованої послідовності.
- Порівняти її зі значенням ентропії для випадкового джерела без пам’яті.

```python
matrix = generate_transition_matrix()
sequence = generate_sequence(matrix)
entropy = calculate_entropy(sequence)
print(f'Ентропія згенерованого джерела: {entropy:.4f}')
```

### КРОК 6. Оформлення звіту
**Шаблон:**  
- Мета роботи  
- Код програми  
- Згенерована послідовність  
- Обчислена ентропія  
- Висновки

### КРОК 7. Завантаження звіту в Google Classroom
- Формат файлу: PDF  
- Назва файлу: `ЛР2_Прізвище_Група.pdf`

---

