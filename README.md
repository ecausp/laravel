# laravel.lndo.site

O objetivo é ter um ambiente de desenvolvimento (LAMP) para projetos em Laravel utilizando Docker + Lando. Com isso não será mais necessário ter Apache, MySql e PHP instalados no desktop de desenvolvimento.

## Uso

### 1) Certifique-se de ter instalados o lando e o docker:

Para isso acesse a documentação: 

Docker: https://docs.docker.com/engine/install/ubuntu/ 

Lando: https://docs.lando.dev/basics/installation.html#linux

### 2) Reinicie seu PC

### 3) Crie seu projeto

Utilize o projeto uspdev/starter: https://github.com/uspdev/starter ou clone seu projeto como de costume

### 4) Baixe os arquivos (.lando.yml, Dockerfile.custom, php.ini) deste repositório para a raiz do seu projeto

No arquivo .lando.yml configure o name do seu projeto

```bash
name: seuprojeto
```

Note que o .gitignore vai substituir o do projeto. Isso é para que os arquivos do Lando não sejam versionados em seu projeto. Você pode optar em incluir no .gitignore do seu projeto ou se preferir pode deixar que os arquivos sejam versionados.

Note que no arquivo .lando.yml você pode optar por exemplo pela versão do PHP, versão do Composer ou pelo servidor de Web utilizado, Apache ou Ngix

### 5) Configure o .env do projeto

Para as credenciais MySQL utilize:

```bash
DB_CONNECTION=mysql
DB_HOST=database
DB_PORT=3306
DB_DATABASE=seuprojeto
DB_USERNAME=seuprojeto
DB_PASSWORD=seuprojeto
```

### 6) Comandos

#### Recompila o projeto
```bash
lando rebuild -y
```

#### Composer install no projeto
```bash
lando composer install
```

#### Gera a key do projeto
```bash
lando php artisan key:generate
```

#### Roda as migrations do projeto
```bash
lando php artisan migrate
```

#### Só para testar o override de configurações php no arquivo php.ini
```bash
lando php -i | grep upload_max_filesize
```

#### Para iniciar o projeto
```bash
lando start
```

#### Informações do projeto
```bash
lando info
```

#### Se tem mais projetos iniciando com o mesmo exemplo de .lando.yml, certifique-se de os outros porjetos estão parados. Para isso vá na pasta do projeto que não vai utilizar no momento e execute
```bash
lando stop
```

## Sobre o Lando

O Lando também possui outros comandos de acordo com o recipiente utilizado, Ex. LAMP, https://docs.lando.dev/config/lamp.html#tooling

O Lando possui recipientes para outros Frameworks (Symfony) e CMS's (Drupal e Wordpress), https://docs.lando.dev/config/recipes.html#supported-recipes

## Endereço do projeto
https://laravel.lndo.site

## Se usa senha única pode-se cadastrar um oauth consumidor respondendo no endereço 
https://laravel.lndo.site/callback 

Dessa forma seus projetos dev com senha única podem utilizar o mesmo oauth consumidor

