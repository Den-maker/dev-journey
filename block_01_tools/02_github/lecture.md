# Git и GitHub - Основные команды

## Первоначальная настройка

### Проверить настройки Git
```bash
git config --global user.name
git config --global user.email
```

### Установить имя и email (если не настроено)
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Инициализация репозитория

### Создать локальный Git репозиторий
```bash
git init
```

### Связать с удалённым репозиторием на GitHub
```bash
git remote add origin https://github.com/username/repo-name.git
```

### Проверить удалённые репозитории
```bash
git remote -v
```

## Работа с изменениями

### Посмотреть статус файлов
```bash
git status
```

### Добавить файлы в staging area
```bash
git add filename.txt           # добавить конкретный файл
git add .                      # добавить все изменения
git add *.md                   # добавить все .md файлы
```

### Создать коммит
```bash
git commit -m "Описание изменений"
```

**Стиль сообщений коммитов:**
- Используй настоящее время: `Add`, `Update`, `Fix`, `Remove`
- Будь конкретным: `Add lesson 01_bash` лучше чем `Add files`
- Первое слово с большой буквы

### Отправить изменения на GitHub
```bash
git push                       # обычный push
git push -u origin main        # первый push с установкой upstream
```

## Ветки

### Посмотреть текущую ветку
```bash
git branch
```

### Переименовать текущую ветку
```bash
git branch -M new-name
```

**Стандарт:** GitHub использует `main` как основную ветку. Старый стандарт был `master`.

## Типичный рабочий процесс
```bash
# 1. Внесли изменения в файлы
# 2. Проверяем что изменилось
git status

# 3. Добавляем в staging
git add .

# 4. Создаём коммит
git commit -m "Add new feature"

# 5. Отправляем на GitHub
git push
```

## Важные моменты

### .gitignore
Файл `.gitignore` указывает Git какие файлы **не нужно** отслеживать:
- Скомпилированные файлы (`.exe`, `.dll`)
- Конфиденциальные данные (`.env`, пароли, API ключи)
- Системные файлы (`Thumbs.db`, `.DS_Store`)
- Зависимости (`vendor/`, `node_modules/`)

### .gitkeep
Git не отслеживает пустые папки. Чтобы сохранить структуру папок в репозитории, создаём пустой файл `.gitkeep` внутри них.

## Полезные команды

### Посмотреть историю коммитов
```bash
git log                        # полная история
git log --oneline              # краткая история
```

### Отменить последний коммит (но сохранить изменения)
```bash
git reset --soft HEAD~1
```

### Посмотреть различия
```bash
git diff                       # изменения которые не в staging
git diff --staged              # изменения в staging
```