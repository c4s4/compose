include env
export

start: # Start ArangoDB
	@docker-compose up -d arango

stop: # Stop ArangoDB
	@docker-compose stop arango

root: # Open ArangoDB shell as root user
	@docker exec -ti arango_arango_1 arangosh

shell: # Open ArangoDB shell
	@docker exec -ti arango_arango_1 arangosh --server.username "$(ARANGO_USERNAME)@$(ARANGO_DATABASE)" --server.database $(ARANGO_PASSWORD)
