# Use the Rust official image as the base
FROM rust:latest

# Set the working directory
WORKDIR /app

# Install cargo-watch
RUN cargo install cargo-watch

# Copy the Cargo manifest and dependencies first to cache dependencies
COPY Cargo.toml Cargo.lock ./
RUN mkdir src && echo "fn main() {}" > src/main.rs 
RUN cargo build

# Copy the rest of the application
COPY . .

# Expose the application port (if applicable)
EXPOSE 8080

# Run cargo-watch to automatically restart on file changes
CMD ["cargo", "watch", "-x", "run"]
