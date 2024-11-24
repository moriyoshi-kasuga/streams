ARG RUST_VERSION=1.81
FROM rust:${RUST_VERSION}-bookworm

WORKDIR /backend

RUN curl -L --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/cargo-bins/cargo-binstall/main/install-from-binstall-release.sh | bash
RUN cargo binstall cargo-watch -y

COPY . .

EXPOSE 3000

CMD ["cargo", "watch", "-s", "cargo run"]
