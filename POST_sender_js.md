# Код, отправляющий POST-запрос на локальный сервер 💻
```
fetch('http://localhost:8000/add_user', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        username: 'john_doe',
        user_info: 'любит петь'
    })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```
***
### Запуск
1. Переходим в папку с js кодом
2. В терминале пишем `node <имя_файла>.js`
3. ✅