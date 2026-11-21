## Шаблон для третьего ДЗ по ИПР

Условие дз доступно по [ссылке](https://github.com/Nikfilk2030/missing_semester_hse_cs/blob/main/2026/amcs/year_1/hw_3/README.md)

## Запуск контейнера.

Сборка образа:
```bash
docker build -t counter-app .
```

Запуск нашего контейнера:
```bash
docker run -d --rm --name counter -p 8080:8000 -e GREETING="Привет из Docker" counter-app
```

## Отчет о проверках. 

Статус контейнера:
```bash
docker ps --filter name=counter
```
GET до инкремента:
```bash
curl -fsS http://127.0.0.1:8080/
 # Ожидается: "count": 0
```
Инкремент:
```bash
curl -fsS -X POST http://127.0.0.1:8080/increment
```
GET после инкремента:
```bash
curl -fsS http://127.0.0.1:8080/
 # Ожидается: "count": 1
```

С полным списком проверок уровня на 4 балла можно ознакомиться в файле `logs-4.txt`.
