# Help Center

<h2 align="center">Help center for the Taraxa blockchain and network</h2>

<p align="center">Browse the topics below or use the GitBook assistant to ask anything you need help with.</p>

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Run your node</strong></td><td>Basic information to help running your node</td><td><a href="readme/run-your-node.md">run-your-node.md</a></td><td><a href="https://images.unsplash.com/photo-1560732488-6b0df240254a?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxzZXJ2ZXJ8ZW58MHx8fHwxNzc1MTE5ODY0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1560732488-6b0df240254a?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxzZXJ2ZXJ8ZW58MHx8fHwxNzc1MTE5ODY0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>RPC cluster</strong></td><td>Join the party (incoming)</td><td></td><td><a href="https://images.unsplash.com/photo-1580106815433-a5b1d1d53d85?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxzZXJ2ZXJ8ZW58MHx8fHwxNzc1MTE5ODY0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1580106815433-a5b1d1d53d85?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxzZXJ2ZXJ8ZW58MHx8fHwxNzc1MTE5ODY0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Other services</strong></td><td>Indexer, explorer, ... (incoming)</td><td></td><td><a href="https://images.unsplash.com/photo-1644088379091-d574269d422f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxuZXR3b3JrfGVufDB8fHx8MTc3NTEzMDY1M3ww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1644088379091-d574269d422f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxuZXR3b3JrfGVufDB8fHx8MTc3NTEzMDY1M3ww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

## End-users status

* You cannot withdraw or send tokens from/to the network or exchanges because the network does not accept new transactions.
* You can check their wallet balance, related nodes or active delegations through the wallet checker provided by the "Monitor" website here: [https://monitor.taraxa.ovh/](https://monitor.taraxa.ovh/)
* You can register on the webiste using your wallet even if you are not connected to the Taraxa network (it's just about signing a message with Metamast, no transaction involved, no gas, no fee, you're safe).
* You can configure Metamask by setting the network RPC URL to `https://mainnet.rpc.taraxa.ovh`. Use chain id `841` and token symbol `TARA` (leave the explorer field blank as it's not available yet). Then you should see your balance.

## Network status

* network is still stale/stuck as **we need a few more validators to come online**.
* the RPC loadbalancer is up and running with a few nodes behind, if you want to join the party, just  let us know.

#### Why?

* To create a block and accept transactions, validator nodes need to reach a consensus of 67% of the total votes.
* Validators have vote power based on the amount of delegated $TARA end-user have made.
* With the recent shutdown of the core team servers, the balance has changed and we don't have enough online validators to reach the 67% threshold.
* What (probably) happens. Let's say with hypothetical values:
  * Community validators had 80% of votes
  * Core team validators had 20% of votes
  * With the core team shutting down their nodes, we might think we still have enough votes to run the network. Problem is: a substantial amount of community validators were offline or don't have updated their nodes to the latest version, leading us to a state where we have something like 55% of the votes.

[**Terms and legal notice**](readme/terms-and-legal-notice.md)
