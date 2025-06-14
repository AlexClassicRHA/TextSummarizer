# Automatic Text Summarizer — Автоматический суммаризатор текста

Веб-приложение для автоматического суммирования текста с расширенными функциями.

## Основные возможности

- **Суммаризация текста** на английском и непальском языках
- **Гибкие источники**:
  - Прямой ввод текста
  - Обработка контента по URL-ссылке
  - Суммаризация PDF-файлов с сохранением в текстовый формат
- **Алгоритмы суммаризации** (на выбор):
  - Frequency Algorithm (Частотный анализ)
  - Sentence Matching (Сопоставление предложений)
- **Дополнительные функции**:
  - Сохранение результатов суммаризации
  - Топ-5 популярных новостей из источников:
    - BBC
    - CNN
    - Nagarik News

## Технологический стек

- **Backend**: Django
- **Зависимости**:
  - `nltk` (обработка естественного языка)
  - `beautifulsoup4` (парсинг веб-страниц)
  - `django` (веб-фреймворк)

---

## Установка и запуск

### 1. Клонирование репозитория
```bash
git clone https://github.com/xanjay/Automatic-Text-Summarizer.git
cd Automatic-Text-Summarizer
```

### 2. Установка зависимостей
```bash
pip install -r requirements.txt
```

### 3. Настройка SECRET_KEY
1. Сгенерируйте секретный ключ на [Django Secret Key Generator](https://www.miniwebtool.com/django-secret-key-generator/)
2. В файле `settings.py` замените строку:
```python
SECRET_KEY = os.environ.get('SECRET_KEY', '-1')
```
3. **Рекомендуемый способ**: Добавьте ключ в переменные окружения:
```bash
export SECRET_KEY='ваш_сгенерированный_ключ'
```

### 4. Настройка базы данных
1. Установите MySQL и создайте базу данных:
```sql
CREATE DATABASE text_summarizer;
```
2. Обновите настройки в `settings.py`:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'text_summarizer',    # Имя БД
        'USER': 'ваш_пользователь',   # Пользователь MySQL
        'PASSWORD': 'ваш_пароль',     # Пароль пользователя
        'HOST': 'localhost',          # Хост (оставьте пустым для localhost)
        'PORT': '3306',               # Порт (по умолчанию 3306)
    }
}
```

### 5. Инициализация базы данных
```bash
python manage.py migrate
```

### 6. Создание администратора
```bash
python manage.py createsuperuser
```
Следуйте инструкциям для создания учетной записи администратора.

### 7. Запуск сервера
```bash
python manage.py runserver
```
Приложение будет доступно по адресу: http://127.0.0.1:8000

---
