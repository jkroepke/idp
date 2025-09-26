FROM alpine:3.22.1

LABEL org.opencontainers.image.source="https://github.com/jkroepke/idp"

RUN apk update && apk add --no-cache yq-go git bash base64 sed jq findutils curl kubectl
RUN mkdir -p /kratix/input; mkdir /kratix/output; mkdir /kratix/metadata; chown -R nobody /kratix
RUN mkdir /tmp/; chown -R nobody /tmp
ENV HOME=/tmp
USER nobody

ADD dependencies /dependencies
ADD execute-pipeline /execute-pipeline
ADD install-dependencies /install-dependencies

CMD [ "/execute-pipeline" ]
ENTRYPOINT []
