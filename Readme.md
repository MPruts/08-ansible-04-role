Файл requirements.yml содержит описание ролей, которые необходимо скачать для работы playbook.

Перед запуском playbook необходимо в командной строке перейти в калаог где расположен файл site.yml и выполнить команду скачивания ролей:

    ansible-galaxy install -r requirements.yml -p roles

Перед запуском playbook нужно указать в файле inventory/prod/hosts.yml адреса серверов на которых будут установлены роли elasticsearch, kibana, filebeat.

Для запуска playbook выполнить команду:

    ansible-playbook -i inventory/prod/ site.yml

В процессе работы выполнения playbook site.yml происходит установка ролей:
- elastic на хост el-instance
- kibana на хост k-instance - ссылка на роль [kibana-role](https://github.com/MPruts/kibana-role)
- filebeat на хост f-instance - ссылка на роль [filebeat-role](https://github.com/MPruts/filebeat-role)

