Hyperledger Sawtooth - Seth
-------------

This project is an Ethereum-compatible transaction family for the Hyperledger
Sawtooth platform.

The primary goal of the Sawtooth-Ethereum integration project, affectionately
dubbed "Seth", is to add support for running Ethereum Virtual Machine smart
contracts to the Hyperledger Sawtooth platform. In order to make this possible,
the Hyperledger Sawtooth project worked with the
[Hyperledger Burrow](https://github.com/hyperledger/burrow) project to integrate
their EVM implementation, the Burrow EVM, into with the Hyperledger Sawtooth
platform.

Documentation
-------------

Documentation for how to run and extend Sawtooth is available here:
https://sawtooth.hyperledger.org/docs/seth/releases/latest/introduction.html

Troubleshoot
------------

If you get errors like

```
More info: https://launchpad.net/~ethereum/+archive/ubuntu/ethereum
gpg: keyring `/tmp/tmpfibk1egw/secring.gpg' created
gpg: keyring `/tmp/tmpfibk1egw/pubring.gpg' created
gpg: requesting key 923F6CA9 from hkp server p80.pool.sks-keyservers.net
gpgkeys: key 2A518C819BE37D2C2031944D1C52189C923F6CA9 can't be retrieved
gpg: no valid OpenPGP data found.
gpg: Total number processed: 0
gpg: keyserver communications error: keyserver helper general error
gpg: keyserver communications error: unknown pubkey algorithm
gpg: keyserver receive failed: unknown pubkey algorithm

```
Then, I think it is better to test with the recent commit(a46e1a3505a80a874569884a3452a060965bd974).


It is possible that `sawtooth-seth-tp` transaction processor fails to build and in this case, you may get error like this:
`ERROR: Service 'seth-tp' failed to build:`. If that happens, then do not build `tp`. It is better to download the image from the directory itself. Do below in YAML file.

```
  seth-tp:
    tty: true
    stdin_open: true
    image: hyperledger/sawtooth-seth-tp
    container_name: seth-tp
    
 ```

License
-------

Hyperledger Sawtooth software is licensed under the [Apache License Version 2.0](LICENSE) software license.

Hyperledger Sawtooth documentation in the [docs](docs) subdirectory is licensed under
a Creative Commons Attribution 4.0 International License.  You may obtain a copy of the
license at: http://creativecommons.org/licenses/by/4.0/.
