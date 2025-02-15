[![progress-banner](https://backend.codecrafters.io/progress/dns-server/8e0333c2-bc0f-4843-976c-2ff59cfa0213)](https://app.codecrafters.io/users/codecrafters-bot?r=2qF)

This is a starting point for Rust solutions to the
["Build Your Own DNS server" Challenge](https://app.codecrafters.io/courses/dns-server/overview).

In this challenge, you'll build a DNS server that's capable of parsing and
creating DNS packets, responding to DNS queries, handling various record types
and doing recursive resolve. Along the way we'll learn about the DNS protocol,
DNS packet format, root servers, authoritative servers, forwarding servers,
various record types (A, AAAA, CNAME, etc) and more.

**Note**: If you're viewing this repo on GitHub, head over to
[codecrafters.io](https://codecrafters.io) to try the challenge.

# Passing the first stage

The entry point for your `your_program.sh` implementation is in `src/main.rs`.
Study and uncomment the relevant code, and push your changes to pass the first
stage:

```sh
git commit -am "pass 1st stage" # any msg
git push origin master
```

Time to move on to the next stage!

# Stage 2 & beyond

Note: This section is for stages 2 and beyond.

1. Ensure you have `cargo (1.82)` installed locally
2. Run `./your_program.sh` to run your program, which is implemented in
   `src/main.rs`. This command compiles your Rust project, so it might be slow
   the first time you run it. Subsequent runs will be fast.
3. Commit your changes and run `git push origin master` to submit your solution
   to CodeCrafters. Test output will be streamed to your terminal.

# Running the Program

- If you would like to enable the added logging functionality, first set the `RUST_LOG` environment variable.
    - `export RUST_LOG=[trace | debug | info | warn]`
- Run `./your_program.sh` in one terminal session, and `dig @127.0.0.1 -p 2053 +noedns codecrafters.io`
  or some other network tool in another, where `codecrafters.io` is an example that we want to resolve.
    - The program returns a fixed arbitrary address as a solution.
- Run as `./your_program.sh --resolver <address>` to work in the forwarding DNS server mode.
    - `<address>` should be of the form `<ip>:<port>`.
    - A forwarding DNS server, also known as a DNS forwarder, is a DNS server that is configured to pass DNS queries it
      receives from clients to another DNS server for resolution, instead of directly resolving DNS queries by looking
      up the information in its own local cache or authoritative records.

# Running the Tests

```sh
cargo test conn
```
