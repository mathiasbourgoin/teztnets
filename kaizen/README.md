Tezos changes protocol every few months. By contrast, Tezos testnets have been recreated at each protocol upgrade. Smart contract developers have been complaining that the pace of Testnet changes is too fast, and it is tedious to recreate contracts every few months.

**Kaizen** is a new kind of Tezos testnet that upgrades to closely follow Tezos mainnet protocol. We aim to run it for a long time.

Unlike mainnet, there is no democracy involved: Kaizen upgrades are user-activated. The upgrade schedule is centrally managed on the Teztnets.xyz platform.

Kaizen was previously known as *Granadanet*. Granadanet has been running since May 2021 and has seen significant developer activity. By using Granadanet as a starting point for Kaizen, we benefit from all this prior activity and make developer's lives easier.

Kaizen will hard-fork from Granadanet and upgrade to Hangzhou shortly before mainnet. We urge all Granadanet bakers to perform the configuration changes described below to participate in the hard fork. If you are running a Granadanet node, here is what you need to do to convert it into a Kaizen node:

1. update Tezos to the most recent release (currently v11.0)
1. update your node's configuration: `tezos-node config update --network https://teztnets.xyz/kaizen`
1. run the baker and endorser daemons for Hangzhou protocol: `tezos-baker-011-PtHangz2`, `tezos-endorser-011-PtHangz2` in addition to the Granada daemons

Your node is now configured to switch protocols to Kaizen at the end of cycle 185 (block 757,759) and subsequently bake using the Hangzhou protocol.

To verify that your configuration is correct, run `tezos-node config` or open your node config file with an editor. The configuration should mention a `user_activated_upgrade` at block `757759`.

We expect the transition to take place on December 3rd. If you do not change your node configuration by then, you will be on a different chain which remained on Granada protocol. Past that point, the only way to get back to Kaizen is to flush your storage and sync from scratch, or from a [snapshot](https://xtz-shots.io).