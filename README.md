# Мікросервісна Архітектура

Цей репозиторій присвячений вивченню мікросервісної архітектури та її реалізації на Python, C++ та Go.

## Зміст
1. Вступ до мікросервісної архітектури
2. Дизайн мікросервісів
3. Комунікація між мікросервісами
4. Моніторинг та тестування
5. Приклади коду
6. Література

## Вступ до мікросервісної архітектури
Мікросервісна архітектура розбиває додатки на невеликі незалежні сервіси, кожен з яких виконує одну функцію.

## Дизайн мікросервісів
Основні принципи дизайну мікросервісів: незалежність, модульність, масштабованість.

## Комунікація між мікросервісами
Мікросервіси спілкуються через API, зазвичай використовуючи HTTP або повідомлення.

## Моніторинг та тестування
Моніторинг і тестування мікросервісів є важливими для забезпечення їхньої надійності та продуктивності.

## Приклади коду
### Python
```python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route('/service1')
def service1():
    return jsonify(message='Service 1 response')

if __name__ == '__main__':
    app.run(port=5001)
```

### C++
```cpp
#include <httplib.h>

int main() {
    httplib::Server svr;

    svr.Get("/service1", [](const httplib::Request&, httplib::Response& res) {
        res.set_content("{\"message\":\"Service 1 response\"}", "application/json");
    });

    svr.listen("localhost", 5001);
}
```

### Go
```go
package main

import (
    "encoding/json"
    "net/http"
)

type Response struct {
    Message string `json:"message"`
}

func service1(w http.ResponseWriter, r *http.Request) {
    response := Response{Message: "Service 1 response"}
    json.NewEncoder(w).Encode(response)
}

func main() {
    http.HandleFunc("/service1", service1)
    http.ListenAndServe(":5001", nil)
}
```

## Література
1. *Building Microservices: Designing Fine-Grained Systems* by Sam Newman
2. *Microservice Architecture: Aligning Principles, Practices, and Culture* by Irakli Nadareishvili, Ronnie Mitra, Matt McLarty, and Mike Amundsen

## Про мене
Привіт! Мене звати **Кошнарьов Данил**, я софтвер девелопер та розробник ПО. Моя мета - допомогти вам освоїти мікросервісну архітектуру та стати кращими програмістами.

## Зворотний зв'язок
Якщо у вас є питання чи пропозиції, не соромтеся зв'язатися зі мною.
