You can find the folder containing the `docker-compose.yml` file here:
- [mern-3tier-application](https://github.com/shashankc20mca/CI-CD-GitOps-3-Tier-Microservices-Platform/tree/main/mern-3tier-application)

Build and start all services:

```bash
docker compose up -d --build
```
### Verify Running Containers

```bash
docker ps
```

### Check Logs

```bash
docker compose logs -f
```

To check logs for a specific service:

```bash
docker compose logs -f backend
docker compose logs -f frontend
docker compose logs -f mongodb
docker compose logs -f mongo-express
```
---

## Access the Application

Use the following URLs after the containers are up and running:

- Frontend: `http://<host-ip>:5050`
- Backend: `http://<host-ip>:8383`
- Mongo Express: `http://<host-ip>:8081`

---

## Stop the Application

Stop all running services:

```bash
docker compose down
```
