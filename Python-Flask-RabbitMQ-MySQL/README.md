**Python: Flask + RabbitMQ + MySQL:**

- Dockerise this repository
- Write docker-compose file. The Docker compose should deploy rabbitmq, mysql, dockerised version of this repo 
- Pass relevent environement varialbles
- Create table on MySQL from python while dockerizing this repo console using commands: `from app import db` & `db.create_all();`
- If everything is fine, you'll be running RabbitMQ on http://localhost:15672/ and python app on http://localhost:5000/
- Create a simple Queue called "operations" on RabbitMQ: http://localhost:15672/#/queues (user: _guest_, pwd: _guest_);
- Start consuming with http://localhost:5000/consume
- Send messages with http://localhost:5000/publish (Json message example: `{ "method": "sum", "list": [8, 4] }` 

Don't forget to use _Content-Type: application/json_ on Headers

Publish method accepts a mathematical operation (sum, subtract, divide, multiply) and a list on numbers, then send this data to RabbitMQ);
Consume method listen to new messages at RabbitMQ and receive them, does the mathematical operation with the informed number list, and them save everything on a MySQL table called message(id, date_received, method, body, result);


