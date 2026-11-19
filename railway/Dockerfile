# Railway deployment image for listmonk.
# Uses the official prebuilt image (the repo's root Dockerfile expects a locally built binary).
FROM listmonk/listmonk:latest

ENV LISTMONK_app__address=0.0.0.0:9000
EXPOSE 9000

# --install --idempotent: sets up the DB only on first boot
# --upgrade: runs migrations when a newer image is deployed
# --config '': read all config from LISTMONK_* env vars
CMD ["sh", "-c", "./listmonk --install --idempotent --yes --config '' && ./listmonk --upgrade --yes --config '' && ./listmonk --config ''"]
