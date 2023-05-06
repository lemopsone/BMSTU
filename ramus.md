# Установка Ramus Educational

## Требования (!):
- наличие homebrew

## 1. Установка Gradle

1) Устанавливаем Gradle версии 6 через Homebrew: 

`brew install gradle@6`

2) Заходим в .zshrc

`nano -w ~/.zshrc`

3) В конец файла вставляем три строки ниже (перемещаемся в файле стрелочкой вниз)

```
export JAVA_HOME="$(brew --prefix openjdk@11)/libexec/openjdk.jdk/Contents/Home/"
export PATH="$(brew --prefix gradle@6)/bin:$PATH"
export PATH="$(brew --prefix openjdk@11)/bin:$PATH"
```
Последовательно нажимаем **1)Ctrl+X 2)y 3)Enter** для сохранения изменений и выхода из файла

4) Применим изменения в окружении

`source ~/.zshrc`

## 2. Установка Ramus

1) Здесь установка на рабочий стол, но можете сами указать нужную папку

```
cd ~/Desktop/
mkdir RamusSoftware
cd RamusSoftware
```
2) Клонируем репозиторий

`git clone https://github.com/Vitaliy-Yakovchuk/ramus.git`

3) Собираем приложение:

`cd ramus && gradle runLocal`

Если всё было сделано по инструкции, то Ramus запустится.
Закрываем программу, ничего не сохраняя, и возвращаемся в терминал.

## 3. Настройка окружения

1) Заходим в .zshrc

`nano -w ~/.zshrc`

2) Вставляем в конец файла строку 

`alias ramus='cd ~/Desktop/RamusSoftware/ramus && gradle runLocal &'`

3) Сохраняем изменения комбинацией **1)Ctrl+X 2)y 3)Enter**

4) Применяем написанный алиас

`source ~/.zshrc`

### PROFIT!<br>Теперь для запуска Ramus Educational вам нужно просто написать `ramus` в окне терминала (текущая директория не имеет значения)