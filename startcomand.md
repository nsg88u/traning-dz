#запустить контейнер postresql и подключить том /home/vasa/data/:/data/pg
docker run --name postgresql -v /home/vasa/data/:/data/pg -d postgres:latest

#убить контейнер, не трогая подключенный том /home/vasa/data
docker rm -f postgresql

#посмотреть содержимое каталога /home/vasa/data
ls /home/vasa/data

#перенести каталог /home/vasa/data в любую другую директорию и снова запустить postresql с новым путём /home/{{newpath}}/data
cp -r /home/vasa/data /home/vasa2/data

docker run --name postgresql -v /home/vasa2/data/:/data/pg -d postgres:latest