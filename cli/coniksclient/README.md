# CONIKS Client implementation in Golang
__Do not use your real public key or private key with this test client.__

## Usage

##### Install the test client
```
⇒  go install github.com/huyuncong/coniks-go/cli/coniksclient
⇒  coniksclient -h
________  _______  __    _  ___  ___   _  _______
|       ||       ||  |  | ||   ||   | | ||       |
|       ||   _   ||   |_| ||   ||   |_| ||  _____|
|       ||  | |  ||       ||   ||      _|| |_____
|      _||  |_|  ||  _    ||   ||     |_ |_____  |
|     |_ |       || | |   ||   ||    _  | _____| |
|_______||_______||_|  |__||___||___| |_||_______|

Usage:
  coniksclient [command]

Available Commands:
  init        Create a configuration file for a CONIKS test client.
  run         Run a CONIKS test client instance.
  version     Print the version number of coniksclient.

Use "coniksclient [command] --help" for more information about a command.
```

### Configure the client

- Generate the configuration file:
```
⇒  mkdir coniks-client; cd coniks-client
⇒  coniksclient init
```
- Ensure the client has the server's *test* public signing key.
- Edit the configuration file as needed:
    - Replace the `sign_pubkey_path` with the location of the server's public signing key.
    - Replace the `registration_address` with the server's registration address.
    - Replace the `address` with the server's public CONIKS address (for lookups, monitoring etc).

### Run the client

```
⇒  coniksclient run  # this will open a REPL
```

##### Register a new name-to-public key mapping with the CONIKS server
```
> register [name] [key]
# The client should display something like this if the request is successful
[+] Succesfully registered name: alice
```

##### Look up a public key
```
> lookup [name]
# The client should display something like this if the request is successful
[+] Found! Key bound to name is: [alice_fake_public_key]
```

##### Other commands

Use `help` for more information.

Use `exit` to close the REPL and exit the client.

## Disclaimer
Please keep in mind that this CONIKS client is under active development.
The repository may contain experimental features that aren't fully tested.
We recommend using a [tagged release](https://github.com/huyuncong/coniks-go/releases).
