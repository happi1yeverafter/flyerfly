1. docker-compose build
2. docker-compose up

adminer - localhost:8080
django - localhost:8000


docker-compose.yml���� db user, password ���� ����
�⺻ admin, admin

access denied��
docker exec -it flyerfly_db_1 bash
���� �� mysql�� user table���� host %�� ���� ��й�ȣ ����
settings.py���� ���� ����

use mysql;
set password 'id'@'%' = 'password';

settings.py

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'flyerfly',
        'USER': 'id',
        'PASSWORD': 'password',
        'HOST': 'db',
        'PORT': '3306',
        'OPTION': {
            'init_command': 'SET sql_mode="STRICT_TRANS_TABLES"'
        }
    }
}
