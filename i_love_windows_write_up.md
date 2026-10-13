
Получаем файлик : **5d696d521de238c3.customDestinations-ms**
В тынтырнетах гуглим че это за расширение:

**Заголовок `customDestinations-ms`**: это стандартное расширение скрытых системных файлов Windows, которые хранят историю закрепленных и недавно открытых файлов для приложений на панели задач.

ИИ гугла так же подсказывает как прочитать содержимое файла в адекватном виде:

```bash
# Флаг -e l заставит strings искать строки в формате 16-bit-little-endian т.к. винда часто хранит строки в таких файлах именно в такой кодировке
strings -e l 5d696d521de238c3.customDestinations-ms
```

Посмотрим на вывод:

В выводе находим следующую строку:

```text
cGVybWN0ZntlcmljX3ppbW1lcm1hbm5fdG9vbHNfdXNlcn0=
```

Это base64 строка, пользуемся CyberChef либо еще проще сразу декодируем через терминал:

```bash
echo "cGVybWN0ZntlcmljX3ppbW1lcm1hbm5fdG9vbHNfdXNlcn0=" | base64 -d
```

Получаем флаг:
```css
permctf{eric_zimmermann_tools_user}
```
