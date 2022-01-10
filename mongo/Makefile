include env
export

start: # Start MongoDB
	@docker-compose up -d mongo

stop: # Stop MongoDB
	@docker-compose stop mongo

shell: # Open MongoDB shell
	@docker exec -it mongo_mongo_1 mongo -u $(MONGO_INITDB_ROOT_USERNAME) -p $(MONGO_INITDB_ROOT_PASSWORD)
