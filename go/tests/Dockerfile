FROM docker.01-edu.org/golang:1.16.0-alpine3.13

ENV GIT_TERMINAL_PROMPT=0
RUN apk add --no-cache git

RUN go get golang.org/x/tools/cmd/goimports

RUN mkdir -p /jail/student
RUN touch /jail/student/go.mod

WORKDIR /public/go/tests
COPY go.* ./
RUN go mod download
COPY base base
COPY func func
COPY lib lib
COPY prog prog
COPY rc rc
RUN go install ./rc ./prog/...

COPY entrypoint.sh /usr/local/bin
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
