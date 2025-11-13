# -commands
# Основные команды Git

## 1. git pull

**Назначение:** Получить последние изменения из удалённого репозитория и объединить с локальной версией.

```bash
# Базовая команда (работает если ветка отслеживает удалённый репозиторий)
git pull

# Явное указание репозитория и ветки
git pull origin main

# С rebase вместо merge (сохраняет историю чище)
git pull --rebase origin main
Пример использования:

bash
# Перед началом работы всегда делайте pull
git pull origin main
2. git push
Назначение: Отправить локальные коммиты в удалённый репозиторий.

bash
# Первый push для новой ветки (с установкой отслеживания)
git push -u origin feature-branch

# Последующие push в ту же ветку
git push

# Push в конкретную ветку
git push origin main
Пример workflow:

bash
# Создаём новую ветку для фичи
git checkout -b new-feature

# Делаем изменения, коммитим
git add .
git commit -m "Add new feature"

# Пушим в первый раз
git push -u origin new-feature

# Далее можно просто использовать git push
3. git push --force и git push --force-with-lease
Назначение: Принудительная отправка изменений (перезаписывает историю).

⚠️ Осторожно! Используйте только когда понимаете последствия.

bash
# ОПАСНО: полная перезапись удалённой ветки
git push --force origin main

# Безопаснее: проверяет, не было ли новых коммитов с момента последнего pull
git push --force-with-lease origin main
Когда использовать:

После git rebase (изменили историю коммитов)

После git commit --amend (исправили последний коммит)

Когда нужно удалить чувствительные данные из истории

4. Другие полезные команды
git status
bash
# Показывает состояние рабочей директории
git status
git add
bash
# Добавить все изменения
git add .

# Добавить конкретный файл
git add filename.txt

# Добавить несколько файлов
git add file1.txt file2.js
git commit
bash
# Стандартный коммит
git commit -m "Your commit message"

# Изменить последний коммит (если ещё не запушили)
git commit --amend -m "New commit message"
git branch
bash
# Показать все ветки
git branch

# Создать новую ветку
git branch new-feature

# Удалить ветку
git branch -d old-feature
git checkout / git switch
bash
# Переключиться на ветку
git checkout main
git switch main

# Создать и переключиться на новую ветку
git checkout -b new-branch
git switch -c new-branch
Типичный рабочий процесс
bash
# 1. Начать с актуальной версии
git pull origin main

# 2. Создать ветку для задачи
git checkout -b my-feature

# 3. Работать над изменениями в VS Code
# ... вносим изменения в файлы ...

# 4. Добавить изменения в staging area
git add .

# 5. Создать коммит
git commit -m "Implement new feature"

# 6. Отправить изменения на GitHub
git push -u origin my-feature

# 7. Создать Pull Request через GitHub UI
Полезные советы для VS Code
Интеграция Git в VS Code:
Откройте панель Source Control (Ctrl+Shift+G)

Видите все изменённые файлы

Можете делать коммиты прямо из редактора

Терминал в VS Code:
Используйте встроенный терминал (Ctrl+`)

Все Git команды работают так же

Расширения:
GitLens - расширенная информация о коммитах

Git Graph - визуализация истории коммитов

text

