Sometimes you just have to have raw HTTP to see things clearly.

I (nickatsegment) took two approaches to help do such a thing, neither of which entail littering the code with debug statements.

# Man-in-the-middle
https://github.com/segmentio/aws-okta/pull/134 shows a docker-compose set up that uses mitm-proxy to MITM your aws-okta container's traffic and decrypt it with a generated root CA.

Pros:
- no modifications of aws-okta necessary

Cons:
- requires running aws-okta in a container (impossible to debug a MacOS client)

# TLS key log

https://github.com/segmentio/aws-okta/pull/133 modifies our `http.Client`s to log TLS session keys to a file, which can then be combined in e.g. Wireshark to decrypt a package capture.

Pros:
- no Docker

Cons:
- needs a special binary (I don't think we'd ever want to have TLS key logging enabled in a release build)