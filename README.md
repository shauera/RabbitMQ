# RabbitMQ
Getting started with RabbitMQ

Run a copy of RabbitMQ in docker
docker run -d --rm --hostname my-rabbit -p 4369:4369 -p 5671:5671 -p 5672:5672 -p 15671:15671 -p 15672:15672 -p 25672:25672 --name some-rabbit rabbitmq

Start RabbitMQ managment UI
docker exec some-rabbit rabbitmq-plugins enable rabbitmq_management

Access managment ui login user:guest password:guest
http://localhost:15672

Build fat jar
gradlew shadowjar

Run consumer
java -cp build\libs\RabbitMQ-all.jar helloWorld/Recv

Run producer
java -cp build\libs\RabbitMQ-all.jar helloWorld/Send
