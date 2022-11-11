
# Laravel Template

### Passo a passo
Clone Repositório criado a partir do template, entre na pasta e execute os comandos abaixo:

Crie o Arquivo .env
```sh
cp .env.example .env
```


Atualize as variáveis de ambiente do arquivo .env
```dosini
APP_NAME=Laravel
APP_URL=http://localhost:8080

DB_PASSWORD=root
```


Suba os containers do projeto
```sh
docker compose up -d
```


Acessar o container
```sh
docker compose exec app bash
```


Instalar as dependências do projeto
```sh
composer install
```


Gerar a key do projeto Laravel
```sh
php artisan key:generate
```


Instalar pacote Composer do Laravel para login
```sh
composer require laravel/ui
```


Baixar pacote front end para o login
```sh
php artisan ui bootstrap --auth
```


Buscar a pasta "resources", dentro dela ir até a pasta "views", seguir até "layouts". 
Entre no arquivo "app.blade.php", vá até a seção "Scripts", apague a linha de codigo 
dentro dela (@vite(['resources/sass/app.scss', 'resources/js/app.js']), e em seu 
lugar insira as linhas de código abaixo:
```sh
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
```

Acesse o projeto
[http://localhost:8080](http://localhost:8080)

Acesse o phpmyadmin
[http://localhost:8081](http://localhost:8081)

API de categorias e filmes:
https://www.learn-laravel.cf/

Rotas:
- (get) /categories
- (get) /category/{id}
- (get) /movies
- (get) /movie/{id}

### Como realizar requisições HTTP get:
Adicionar no arquivo web.php e acesse a rota [http://localhost:8080/requisicao](http://localhost:8080/requisicao)
```php
Route::get('/requisicao', function () {
    $json = \Illuminate\Support\Facades\Http::get('https://learn-laravel.cf/movie/1')->body();
    dd($json);
});
```
Em caso de sucesso irá aparecer a mensagem (em linha única sem formatação):
```json
{
    "id": 1,
    "name": "Zack and Miri Make a Porno",
    "category_id": 6,
}
```

### Como criar tela de login no Laravel (ATENÇÃO LER DESCERIÇÃO DOS VIDEOS):

- Criação login sem node: [https://youtu.be/V2s2toQNMG0](https://youtu.be/V2s2toQNMG0)
- Criação login com node: [https://youtu.be/UhOYeYoK3Bc](https://youtu.be/UhOYeYoK3Bc)
