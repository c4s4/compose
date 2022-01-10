include env
export

psql-start: # Start PostgreSQL
	$(title)
	@docker-compose up -d postgresql

psql-stop: # Stop PostgreSQL
	$(title)
	@docker-compose stop postgresql

psql-shell: # Open PostgreSQL shell
	$(title)
	@docker-compose exec -e POSTGRES_PASSWORD=$(POSTGRES_PASSWORD) postgresql \
		psql -h $(POSTGRES_HOSTNAME) -U $(POSTGRES_USER) $(POSTGRES_DB)
