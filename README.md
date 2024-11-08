# Лабораторна робота №5 - Розробка додатку для візуалізації вимірювань GPS

У процесі виконання лабораторної роботи я зосередився на розробці веб-додатку для візуалізації даних GPS. Мета полягала в створенні інтерфейсу, який би зчитував дані з емулятора GPS через WebSocket та відображав положення супутників і об'єкта на графіку. Спочатку я налаштував середовище, запустивши сервер, який надсилав дані у реальному часі.
Наступним етапом я створив HTML-документ, в якому визначив структуру сторінки. Я використав бібліотеку Plotly для візуалізації графіків, що дозволило мені створити інтерактивний графік, який реагує на нові дані, що надходять через WebSocket (ws://localhost:4001).

![image](https://github.com/user-attachments/assets/1093f1f4-7bdd-4c1b-ab39-d532c02a085c)


На сторінці є форма для зміни параметрів GPS, що дозволяє користувачу налаштовувати його відповідно до потреб:
1.Швидкість супутника (км/год). Цей параметр визначає, з якою швидкістю супутник рухається. Висока швидкість супутника може впливати на точність визначення положення об'єкта.
2.Швидкість об'єкта (км/год). Вказує, з якою швидкістю рухається об'єкт, координати якого ми намагаємося визначити. Ця інформація допомагає в коректному розрахунку положення об'єкта на графіку.
3.Кнопка "Оновити налаштування". Після зміни налаштувань, користувач може натиснути цю кнопку, щоб відправити нові параметри на сервер. Це забезпечує оновлення конфігурацій GPS у реальному часі.

Графік на сторінці показує положення супутників (червоні маркери) та об'єкта (синій маркер) у декартових координатах. Я використав трилатерацію для обчислення координат об'єкта на основі даних від щонайменше трьох супутників. Це дозволило мені точно відобразити положення об'єкта на графіку, який динамічно оновлюється при отриманні нових даних.

![image](https://github.com/user-attachments/assets/233dc712-0de0-4d89-8a2a-e4f8a4e9fabf)


