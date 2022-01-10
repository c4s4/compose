include env
export

start: # Start PostgreSQL
	@docker-compose up -d postgresql

stop: # Stop PostgreSQL
	@docker-compose stop postgresql

shell: # Open PostgreSQL shell
	@docker-compose exec -e POSTGRES_PASSWORD=$(POSTGRES_PASSWORD) postgresql \
		psql -h $(POSTGRES_HOSTNAME) -U $(POSTGRES_USER) $(POSTGRES_DB)
