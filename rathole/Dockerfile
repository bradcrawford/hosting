FROM alpine:3.16 AS downloader
ARG VERSION=v0.4.8
RUN base_url=https://github.com/rapiz1/rathole/releases/download/${VERSION}/ \
    && file=$(case "$(uname -m)" in "x86_64") echo "rathole-x86_64-unknown-linux-musl.zip";; "aarch64") echo "rathole-aarch64-unknown-linux-musl.zip";; "armv7l") echo "rathole-armv7-unknown-linux-musleabihf.zip";; "arm") echo "rathole-arm-unknown-linux-musleabihf.zip";; *);; esac) \
    && wget -O rathole.zip ${base_url}${file} \
    && unzip rathole.zip

FROM alpine:3.16
COPY --from=downloader /rathole .

USER 1000:1000
ENTRYPOINT ["./rathole"]
