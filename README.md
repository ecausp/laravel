# laravel.lndo.site

Arrquivos de configuração para dev com Lando e Laravel

## Uso

Certifique-se de ter instalados o lando e o docker

Clone o projeto Laravel como de costume

Baixe esses arquivos para a raiz do seu projeto

Note que o .gitignore vai substituir o do projeto. Isso é para que os arquivos do Lando não sejam versionados em seu projeto

## Configure o .env do projeto

Para as credenciais MySQL utilize:

```bash
DB_CONNECTION=mysql
DB_HOST=database
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=laravel
```

## Comandos

Se existe o container destrói e recompila
```bash
lando destroy -y && lando rebuild -y
```

Composer install no projeto
```bash
lando ssh -s appserver -c "composer install"
```

Gera a key do projeto
```bash
lando ssh -s appserver -c "php artisan key:generate"
```

Roda as migrations do projeto
```bash
lando ssh -s appserver -c "php artisan migrate"
```

Só para testar o override de configurações php no arquivo php.ini
```bash
lando ssh -s appserver -c "php -i | grep upload_max_filesize"
```
Endereço do projeto
https://laravel.lndo.site

Se usa senha única pode-se cadastrar um oauth consumidor respondendo no endereço 
https://laraval.lndo.site/callback 

Dessa forma seus projetos dev com senha única podem utilizar o mesmo oauth consumidor

