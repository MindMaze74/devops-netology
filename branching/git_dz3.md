# Отчёт по заданию «Ветвление, merge и rebase»

## Выполненные шаги
1. Созданы файлы merge.sh и rebase.sh с начальным содержимым, коммит `prepare for merge and rebase`.
2. В ветке `git-merge` дважды изменён `merge.sh` (замена `$*` на `$@`, затем цикл `while`), коммиты отправлены.
3. В `main` изменён `rebase.sh` (добавлен вывод через `$@` и разделитель), коммит отправлен.
4. Создана ветка `git-rebase` от коммита `prepare for merge and rebase`, в ней два коммита с изменениями `rebase.sh`.
5. Выполнен `merge` ветки `git-merge` в `main` – без конфликтов.
6. Выполнен `git rebase -i main` для `git-rebase`, коммиты объединены через `fixup`, разрешены конфликты:
   - первый конфликт – оставлен вариант `echo "\$@ Parameter #$count = $param"`;
   - второй конфликт – оставлен вариант `echo "Next parameter: $param"`.
7. После успешного rebase сделан принудительный пуш `git push -f`.
8. Ветка `git-rebase` слита с `main` через fast-forward.

## Скриншоты
### Граф сети на GitHub
![График сети]()

### Локальный граф (команда git log)
<details>
  <summary>Нажмите, чтобы увидеть результаты  git log</summary>

```bash
user@ubuntu24:~/git/devops-netology$ git log --oneline --graph --all --decorate
* 808820e (HEAD -> main, origin/main, origin/git-rebase, git-rebase) git-rebase 1
*   cc14dfc Merge branch 'git-merge' конфликтов не будет
|\  
| * fcd6b8b (origin/git-merge, git-merge) merge: use shift
| * 6e58370 merge: @ instead *
* | b100e62 update rebase.sh in main
|/  
* 262c519 prepare for merge and rebase
* 64cc631 Prepare to delete and move
* b5f3c96 Prepare to delete and move
* ce99456 новые правки
* c901e43 (gitlab/main) Update README
* 84ccdbc Moved and deleted
* 5de71b5 Prepare to delete and move
* 95b546a Moved and deleted
* a73759e Moved and deleted
* 0f998c0 Prepare to delete and move
* b2f1860 завершение дз после правок
* 28a8639 завершение дз после правок
* 5300cb3 Moved and deleted
* 2a55553 (tag: v0.1, tag: v0.0) Update .gitignore
| * 3cc104c (origin/fix, gitlab/fix, fix) Update README in fix branch
|/  
* a23a577 Moved and deleted
* 56d4cf3 Added gitignore
* 096deca git add...
* 2323eee First commit
* cd254b4 Initial commit
 ^X
| * 6e58370 merge: @ instead *
* | b100e62 update rebase.sh in main
|/  
* 262c519 prepare for merge and rebase
* 64cc631 Prepare to delete and move
* b5f3c96 Prepare to delete and move
* ce99456 новые правки
* c901e43 (gitlab/main) Update README
* 84ccdbc Moved and deleted
* 5de71b5 Prepare to delete and move
* 95b546a Moved and deleted
* a73759e Moved and deleted
* 0f998c0 Prepare to delete and move
* b2f1860 завершение дз после правок
* 28a8639 завершение дз после правок
* 5300cb3 Moved and deleted
* 2a55553 (tag: v0.1, tag: v0.0) Update .gitignore
| * 3cc104c (origin/fix, gitlab/fix, fix) Update README in fix branch
|/  
* a23a577 Moved and deleted
* 56d4cf3 Added gitignore
* 096deca git add...
* 2323eee First commit
* cd254b4 Initial commit
```
</details>