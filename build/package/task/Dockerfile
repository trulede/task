FROM golang AS builder
RUN GOBIN=/go/bin go install cmd/task

FROM scratch
COPY --from=builder /go/bin/task /task
ENTRYPOINT ["/task"]
