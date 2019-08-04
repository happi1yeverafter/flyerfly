1. docker-compose build
2. docker-compose up

adminer - localhost:8080
django - localhost:8000


docker-compose.yml에서 db user, password 설정 가능
기본 admin, admin

access denied시
docker exec -it flyerfly_db_1 bash
실행 후 mysql의 user table에서 host %에 대한 비밀번호 설정
settings.py에서 설정 변경

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
