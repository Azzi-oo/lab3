I. Настройка глобального рабочего пространства
Задать имя пользователя в конфигурационном файле    git config --global user.name "Azzi"
  
Задать электронную почту в конфигурационном файле    git config --global user.email "yanberdin.az@yandex.ru"
  
Просмотреть сделанные настройки двумя способами Способ 1:    git config --list
   Способ 2:    git config --global --edit
   (Откроется конфигурационный файл в редакторе.)

II. Основные операции
Создать локальный репозиторий Создай папку для работы:    mkdir lab_git
cd lab_git
git init
  

Создать три текстовых файла (f1.txt, f2.txt, f3.txt) с несколькими содержательными строками    echo "Это файл 1" > f1.txt
echo "Это файл 2" > f2.txt
echo "Это файл 3" > f3.txt
  

Добавить файлы в отслеживаемые (git add)    git add f1.txt f2.txt f3.txt
  

Зафиксировать изменения с осмысленным сообщением    git commit -m "Добавлены три текстовых файла f1, f2, f3"
  main c959d6b] Добавдлены три текстовых файла f1, f2, f3

Удалить f3.txt:   rm f3.txt
  delete mode 100644 f3.txt

Зафиксировать изменения снова    git add .
git commit -m "Удалён файл f3.txt"
  

Посмотреть историю коммитов    git log
   или кратко:    git log --oneline
    commit 51cd7b149486d68fc35ab6ea3097d67883c4354a (HEAD -> main)
    Author: Азат Янбердин <azat@MacBook-Air.local>
    Date:   Tue Oct 21 17:42:28 2025 +0500

    Файл 3 удален

    commit c959d6b068cbebd8ed0c1c43a202b13403d22c93

Сделать ещё два коммита и поставить тег Пример:    echo "Добавлен новый текст" >> f1.txt
git add f1.txt
git commit -m "Дополнен файл f1.txt"
    [main 6f27302] Дополнен файл f1

echo "Изменён файл f2.txt" >> f2.txt
git add f2.txt
git commit -m "Изменён файл f2.txt"
    [main 6fdaef8] Изменен файл f2
   Поставить тег (например, “Лабораторная_3”):   git tag Лабораторная_3
   Посмотреть результат    git log --oneline --decorate
    6fdaef8 (HEAD -> main, tag: Лабораторная_3) Изменен файл f2
    6f27302 Дополнен файл f1
    51cd7b1 Файл 3 удален
    c959d6b Добавдлены три текстовых файла f1, f2, f3
    3bb6f7d (origin/main) first commit