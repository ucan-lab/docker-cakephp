up:
	docker-compose up -d
build:
	docker-compose build --no-cache --force-rm
create-project:
	mkdir -p ./docker/php/bash
	touch ./docker/php/bash/.bash_history
	@make build
	@make up
	docker-compose exec app composer create-project --prefer-dist cakephp/app:4.* .
	docker-compose exec app sed -i '0,/localhost/ s/localhost/db/' config/app_local.php
install-recommend-packages:
	docker-compose exec app composer require --dev roave/security-advisories:dev-master
init:
	touch ./docker/php/bash/.bash_history
	docker-compose up -d --build
	docker-compose exec app cp config/.env.example config/.env
	docker-compose exec app cp config/app_local.example.php config/app_local.php
	docker-compose exec app composer install
down:
	docker-compose down
destroy:
	docker-compose down --rmi all --volumes
remake:
	@make destroy
	@make init
stop:
	docker-compose stop
start:
	docker-compose start
restart:
	@make down
	@make up
destroy-volumes:
	docker-compose down --volumes
ps:
	docker-compose ps
logs:
	docker-compose logs
logs-watch:
	docker-compose logs --follow
web:
	docker-compose exec web ash
app:
	docker-compose exec app bash
migrate:
	docker-compose exec app bin/cake migrations migrate
test:
	docker-compose exec app composer test
yarn:
	docker-compose exec web yarn
yarn-dev:
	docker-compose exec web yarn run dev
yarn-watch:
	docker-compose exec web yarn run watch
yarn-watch-poll:
	docker-compose exec web yarn run watch-poll
yarn-hot:
	docker-compose exec web yarn run hot
db:
	docker-compose exec db bash
sql:
	docker-compose exec db bash -c 'mysql -u $$MYSQL_USER -p$$MYSQL_PASSWORD $$MYSQL_DATABASE'
salt-generate:
	docker-compose exec app bash -c "curl -s https://gist.githubusercontent.com/ucan-lab/cba0f7677355e07284fe1e2d5a90cd63/raw/3771e7c11963316eef389fc36a79144d6848a5db/cakephp-security-salt-generator.php | php"
