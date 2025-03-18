# Use Rust nightly image
FROM rustlang/rust:nightly as builder

# Set the working directory
WORKDIR /usr/src/app

# Install cargo-watch for live reloading
RUN cargo install cargo-watch

# Copy source code
COPY . .

# Run the app with live reloading
CMD ["cargo", "watch", "-x", "run"]
