<div align="center">

<img src="header.png" alt="FOMOTH, how much did you fumble" width="100%">

[![live](https://img.shields.io/badge/live-fomoth.com-00c805?style=flat-square&labelColor=0b0f0d)](https://fomoth.com)
[![engine](https://img.shields.io/badge/engine-fomoth-00c805?style=flat-square&logo=github&logoColor=white&labelColor=0b0f0d)](https://github.com/FomothFumble/fomoth)
[![x](https://img.shields.io/badge/x-@fomoth__fumble-00c805?style=flat-square&logo=x&logoColor=white&labelColor=0b0f0d)](https://x.com/fomoth_fumble)
[![chains](https://img.shields.io/badge/chains-robinhood%20%7C%20solana-00c805?style=flat-square&labelColor=0b0f0d)](https://fomoth.com)

</div>

### One number, measured properly

Every tracker on the market will show you profit and loss, because that is the easy half. The half
that decides a trading year is the token you sold at two times that ran forty times without you, and
almost nobody puts a dollar figure on it. That figure is what this account builds.

The rule is simple. Take every sell a wallet ever made, find the highest price the token reached
after that sell, and price the difference. Sum it, and you get the money that walked away. We call
it the fumble because that is what it feels like.

### How the measuring is done

Robinhood Chain gets read from nothing but a public RPC. No indexer exists for it, so transfers come
back raw from `eth_getLogs`, get regrouped into transactions, and launchpad curve words and Uniswap
v4 swaps get decoded out of the receipts. The top that followed an exit is read block exact off the
curve, not approximated from candles, which matters on a chain that mints ten blocks a second.

Solana takes the shorter path for trades and a longer one for trust. Any peak above fifteen times
gets re-checked against independent candles before it is allowed into a report, because a wrong all
time high is the fastest way to publish a fake number. One provider once reported a token at eleven
times its real top. That would have printed a 73 million dollar fumble. The check exists so it does
not happen twice.

### Live

**[fomoth.com](https://fomoth.com)** takes a public address and returns the verdict, the ghost curve
of what holding to the top would have been worth, every fumble ranked in dollars, and the exit rules
replayed over that wallet's own trades with the money each one would have added.

**[The engine](https://github.com/FomothFumble/fomoth)** is open. C++17 for the arithmetic with its
own tests, Python for the reading and the serving, CI that will not let the math change quietly.

### Ground rules

- **Read only.** A public address, never a key, never a signature, never a transaction.
- **A peak that cannot be reproduced does not ship.** A smaller honest number beats a big invented one.
- **Numbers carry their timestamp.** A replay is never presented as a live reading.
- **Nothing is sold as a signal.** This is measurement of what already happened, not a prediction of
  what comes next.

<div align="center">

`public rpc only` · `no private keys` · `every peak verified`

</div>
