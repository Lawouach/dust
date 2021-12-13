FROM chaostoolkit/chaostoolkit:latest

USER root
RUN apk add --no-cache --virtual build-deps gcc g++ git libffi-dev linux-headers \
        python3-dev musl-dev && \
    apk add libstdc++ && \
    pip install --no-cache-dir -q -U pip setuptools && \
    pip install --prefer-binary --no-cache-dir -q -U chaostoolkit \
    chaostoolkit-opentracing \
    jaeger-client \
    opentelemetry-exporter-jaeger-proto-grpc \
    opentelemetry-api \
    opentelemetry-sdk \
    opentelemetry-opentracing-shim && \
    apk del build-deps
USER 1001