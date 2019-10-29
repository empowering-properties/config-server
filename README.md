Start vault:
---
```bash
docker run -d -p 8200:8200 --name vault -e 'VAULT_DEV_ROOT_TOKEN_ID=vault-secret' -e 'VAULT_DEV_LISTEN_ADDRESS=0.0.0.0:8200' -e "VAULT_ADDR=http://localhost:8200" vault
```

Add Vault Secret
---
```bash
vault kv put secret/empowering-properties spring.datasource.password=docker
``` 

Start Spring Cloud Config Application
---
```bash
mvn spring-boot:run
```

Check configuration:
---
```bash
curl http://localhost:8888/empowering-properties/default | jq
```
