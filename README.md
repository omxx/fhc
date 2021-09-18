# HTTP checker tool

This tool tries to resolve https first, if this fails then fallback to http.

# Performance & speed

Solution is **very** resource friendly, you can use up to 1000 threads in an single core machine and this will work without any problem, the bottleneck for this tool is your network speed. By default, it is able to perform HTTP check for ~913 hosts per second in good network conditions. Depending on how much host have only http (not https) and/or are alive the number of host resolved in average can be low/higher as the tool have or not to perform a double check.

# Installation

1. You need to have the latest stable [Rust](https://www.rust-lang.org/) version installed in your system.
2. Clone the repo or download the source code, then run `cargo build --release`.
3. Execute the tool from `./target/release/fhc` or add it to your system PATH to use from anywhere.

# Usage

- Show all HTTP urls depite their response codes:

```
cat hosts.txt | fhc
```

- If you want to see only the HTTP host with 200-299 codes:

```
cat hosts.txt | fhc -2
```

You can tune the `--timeout`, `-t/--threads`, `-u/--user-agent` and other options according to your needs. See `fhc --help`
