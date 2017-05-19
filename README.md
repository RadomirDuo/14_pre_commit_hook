# Решение и проверка квадратного уравния

####Данный репозиторий содержит следующие файлы:
1. `quadratic_equation.py` - скрипт, который решает квадратное уравнение
и возвращает корни уравнения.
2. `tests.py` - скрипт, который тестирует выполнение `quadratic_equation.py`
3. `pre-commit` - `shell` файл, который является автотестом. 

####Работа автотеста.
Перед тем как сделать коммит, автоматически выполнится `pre-commit`, который запустит скрипт `tests.py`.
Произойдёт проверка скрипта `quadratic_equation.py` и вернётся 0 или 1.
0 - коммит выполнится
1 - выскочит ошибка

####Для того, чтобы автотест работал, необходимо:
- Под Unix системой
1. На локальной машине в репозитории `14_pre_commit_hook` скопировать в дирректорию
 `.git/hooks` файл `pre-commit`.
2. Дать права на исполнение, находясь в корне репозитория, командой `chmod +x .git/hooks/pre-commit`.
3. Сделать коммит.

####Примеры коммитов:

Ошибка

```
git commit -m "test pre-commit"
.E..
======================================================================
ERROR: test_returns_none_for_complex_solution (__main__.QuadraticEquationTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests.py", line 22, in test_returns_none_for_complex_solution
    root1, root2 = get_roots(1, 2, 3)
  File "/home/kento/devman/14_pre_commit_hook/quadratic_equation.py", line 8, in get_roots
    root1 = (-b - sqrt(discriminant)) / (2 * a)
ValueError: math domain error

----------------------------------------------------------------------
Ran 4 tests in 0.001s

FAILED (errors=1)

```

Выполнение коммита
```
git commit -m "initial status"
....
----------------------------------------------------------------------
Ran 4 tests in 0.001s

OK
[master 60e99ce] initial status
 1 file changed, 1 insertion(+), 1 deletion(-)

```

# Цели проекта

Код написан в образовательных целях. Тренировочный курс для веб-разработчиков. - [DEVMAN.org](https://devman.org)
