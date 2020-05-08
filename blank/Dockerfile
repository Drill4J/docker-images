FROM alpine:3 as builder
RUN apk add gcc musl-dev
RUN echo "int main(){}" | gcc -x c -s -Os --static -o/tmp/dummy - 

FROM scratch
COPY --from=builder /tmp/dummy .
ENTRYPOINT [ "/dummy" ]
