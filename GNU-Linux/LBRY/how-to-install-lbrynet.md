# Как установить lbrynet на свой сервер

1. Переходим в нужную директорию и скачиваем zip-файл 

###### [Проверьте новые версии](https://github.com/lbryio/lbry-sdk/releases)

```
cd /var/www
sudo wget https://github.com/lbryio/lbry-sdk/releases/download/v0.96.0/lbrynet-linux.zip
```

2. Распаковываем и удаляем zip-файл

```
sudo apt install unzip | sudo unzip lbrynet-linux.zip | sudo rm lbrynet-linux.zip | ls
```

###### Появился файл lbrynet

3. Создаем псевдоним для /var/www/lbrynet

* Открываем файл с псевдонимами

```
nano ~/.bashrc
```

* Стрелочками перемещаемся в самый низ и вставляем *(Shift+Ctrl+V)* следующую строку:

```
alias lbn='/var/www/lbrynet'
alias lbrynet='/var/www/lbrynet'
```

###### Теперь вы можете писать как lbn, так и lbrynet. 
###### Чтоб сохранить и закрыть файл жмем Ctrl+S и Ctrl+X

4. Перезагружаем машину и переподключаемся к серверу
```
sudo reboot now
```

lbrynet установлен на ваш сервер.
###### Чтобы это проверить, введите lbn
