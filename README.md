# RabbitMQ
____
<br/> Для выполнения задания мы установили Docker </br>
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
sudo apt update
apt-cache policy docker-ce
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
```
![image](https://sun9-87.userapi.com/impg/dXb_ZVuA50yOYttGO9jhAVzmQx-kaj7VgGrPug/sWVWx2RPTTI.jpg?size=745x237&quality=96&sign=e6e6b76ea8b16b5f53c1ecf40e2c2214&type=album)

<br/> Выполним развертывание сервера RabbitMQ на основе официального Docker-образа — rabbitmq: RabbitMQ is an open source multi-protocol messaging broker. Создадим контейнер с RabbitMQ командой: </br>
```
docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq
```
<br/> Команда run с флагом -it подключает интерактивный tty в контейнер. Флаг --rm нужен, чтобы контейнер автоматически удалялся при завершении. Сервер RabbitMQ использует два TCP-порта: 5672 — для доступа клиентов, 15672 — для управления через web-интерфейс. </br>
![image](https://sun9-63.userapi.com/impg/C0u0wOKGHRgo9VDjBBDMxCD_cMbpc0PDQSVg3Q/h-nUvulPdRg.jpg?size=1523x402&quality=96&sign=56652d4c4bed0608f89d2fa45a6fa7c6&type=album)
<br/> Мы будем использовать Pika, который является клиентом Python, рекомендованным командой RabbitMQ. Установим его командой: </br>
```
pip3 install pika
```
![image](https://sun9-72.userapi.com/impg/hbFaAq8FZXmZtAJtD9bhvfx--0HYIK8eG974TQ/-Pwv5jCMTQs.jpg?size=519x100&quality=96&sign=ad7a34b050bfcf73ec1817a06356e068&type=album)
<br/> Для отправки сообщений использовали channel.basic_publish, для получения channel.basic_consume </br>
![image](https://sun9-83.userapi.com/impg/YKxrvnVVNhu2uxjhfU5xHAFsw-RcIKqvpm_itA/N2C8xrPPlj8.jpg?size=1904x347&quality=96&sign=13b9d4e2bf65775e455f9f168b627310&type=album)
