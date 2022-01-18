include env
export

DATE = $(shell date +%Y-%m-%d-%H-%M)

start: # Start PostgreSQL
	@docker-compose up -d postgresql

stop: # Stop PostgreSQL
	@docker-compose stop postgresql

shell: # Open PostgreSQL shell
	@docker-compose exec -e POSTGRES_PASSWORD=$(POSTGRES_PASSWORD) postgresql \
		psql -h $(POSTGRES_HOSTNAME) -U $(POSTGRES_USER) $(POSTGRES_DB)

backup: # Backup PostgreSQL database
	$(title)
	@docker-compose exec -e PGPASSWORD=$(POSTGRES_PASSWORD) postgresql \
		pg_dump -h $(POSTGRES_HOSTNAME) -p $(POSTGRES_PORT) -d $(POSTGRES_DB) -U $(POSTGRES_USER) \
		-w -F tar -f /backup/$(POSTGRES_DB)-$(DATE).tar

restore: # Restore PostgreSQL database
	$(title)
	echo "Backup files:"
	@cd $(POSTGRES_BACKUP_DIR); ls $(POSTGRES_DB)-*.tar
	@echo "File to restore:"
	@read file; \
	docker-compose exec -e PGPASSWORD=$(POSTGRES_PASSWORD) postgresql \
		pg_restore -h $(POSTGRES_HOSTNAME) -p $(POSTGRES_PORT) -d $(POSTGRES_DB) -U $(POSTGRES_USER) \
		-w -c /backup/$$file
