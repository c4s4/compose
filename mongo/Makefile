include env
export

mongo-start: # Start MongoDB
	@docker-compose up -d mongo

mongo-stop: # Stop MongoDB
	@docker-compose stop mongo

mongo-shell: # Open MongoDB shell
	@docker exec -it mongo_mongo_1 mongo -u $(MONGO_INITDB_ROOT_USERNAME) -p $(MONGO_INITDB_ROOT_PASSWORD)
