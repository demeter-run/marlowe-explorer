FROM nixos/nix:latest-amd64

WORKDIR /app

COPY . .
COPY /image/entrypoint.sh .

RUN nix-build --option filter-syscalls false shell.nix

RUN ["chmod", "+x", "entrypoint.sh"]

ENTRYPOINT ["sh", "-c", "./entrypoint.sh"]