Неофициальный пакетный менеджер для [[macOS]].

С его помощью можно установить консольные приложения и приложения с графическим интерфейсом (для этого нужно вызвать команду `brew install` с параметром `--cask`).

Homebrew устанавливает консольные приложения в директорию
`/opt/homebrew/bin/`, а приложения с [[Graphical User Interface (GUI)|GUI]] — в `/Applications`.

## formulas and casks
Homebrew называет файлы с описанием процесса установки
* formulae — для консольных программ
* cask — для программ с [[Graphical User Interface (GUI)]]

Эти файлы представляют из себя [[JavaScript Object Notation (JSON)|json]] с метаинформацией, такой как путь скачиванию приложения в интернете, файлы, которые она создаёт на компьютере пользователя, список зависимостей, для какой версии macOS приложение подходит, и т.п.
[Пример cask для Sublime Text](https://formulae.brew.sh/api/cask/sublime-text.json)
[Пример formulae для htop](https://formulae.brew.sh/api/formula/htop.json)

## taps
Third-Party Repositories для Homebrew называются **taps**.
* `brew taps` — посмотреть список подключенных репозиториев
* `brew taps <user/repo>` — makes a clone of the repository at https://github.com/user/homebrew-repo. After that, brew will be able to work on those formulae as if they were in Homebrew’s canonical repository.
* `brew untap <user/repo>` — удалить сторонний репозиторий.

## команды
* `brew install <название пакета>` — установить пакет по имени.
* `brew install --cask <название пакета>` — установить программу с графическим интерфейсом.
* `brew remove <название пакета>` — удалить пакет по имени.
* `brew upgrade` — обновить установленные пакеты.
* `brew upgrade --cask --greedy` — обновить установленные программы с GUI, даже если у них неизвестна версия или в cask стоит флаг `auto_updates true`, который означает что программа обновляется сама.
* `brew bundle dump` — создать файл с перечислением программ, которые установил пользователь, и которые не являются зависимостями для других программ. Это самый простой способ увидеть список зависимостей верхнего уровня.
* `brew cleanup` — удалить все устаревшие версии программ, хранящиеся в кеше.
* `brew autoremove` — удалить все зависимости, родители которых отсутствуют.
