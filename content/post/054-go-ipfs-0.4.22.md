---
date: 2019-08-06
url: 93-go-ipfs-0.4.22
title: go-ipfs 0.4.22 released
author: Steven Allen
---

We're releasing a PATCH release of go-ipfs based on 0.4.21 containing some critical fixes.

The past several releases have been shaky and the network has scaled to the point where where small changes can have a wide-reaching impact on the entire network. To keep this situation from escalating, we've put a hold on releasing new features until we can improve our [release process](https://github.com/ipfs/go-ipfs/pull/6482) (which we will be trialing in this release) and [testing procedures](https://github.com/ipfs/go-ipfs/issues/6483).

This release includes fixes for the following regressions:

1. A major bitswap throughput regression introduced in 0.4.21 ([ipfs/go-ipfs#6442](https://github.com/ipfs/go-ipfs/issues/6442)).
2. High bitswap CPU usage when connected to many (e.g., 10,000) peers. See [ipfs/go-bitswap#154](https://github.com/ipfs/go-bitswap/issues/154).
2. The local network discovery service sometimes initializing before the networking module, causing it to announce the wrong addresses and sometimes complain about not being able to determine the IP address) ([ipfs/go-ipfs#6415](https://github.com/ipfs/go-ipfs/pull/6415)).

It also includes fixes for:

1. Pins not being persisted after `ipfs block add --pin` ([ipfs/go-ipfs#6441](https://github.com/ipfs/go-ipfs/pull/6441)).
2. Concurrent map access on GC due to the pinner ([ipfs/go-ipfs#6419](https://github.com/ipfs/go-ipfs/pull/6419)).
3. Potential pin-set corruption given a concurrent `ipfs repo gc` and `ipfs pin rm` ([ipfs/go-ipfs#6444](https://github.com/ipfs/go-ipfs/pull/6444)).
4. Build failure due to a deleted git tag in one of our dependencies ([ipfs/go-ds-badger#64](https://github.com/ipfs/go-ds-badger/pull/65)).


Thanks to:

* @hannahhoward for fixing both bitswap issues.
* @sanderpick for catching and fixing the local discovery bug.
* @campoy for fixing the build issue.

# ❤️ Contributors

Would you like to contribute to the IPFS project and don't know how? Well, there are a few places you can get started:

- Check the issues with the `help wanted` label in the [go-ipfs repo](https://github.com/ipfs/go-ipfs/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22)
- Join an IPFS All Hands, introduce yourself and let us know where you would like to contribute - https://github.com/ipfs/team-mgmt/#weekly-ipfs-all-hands
- Hack with IPFS and show us what you made! The All Hands call is also the perfect venue for demos, join in and show us what you built
- Join the discussion at [discuss.ipfs.io](https://discuss.ipfs.io/) and help users finding their answers.
- Join the [Go Core Dev Team Weekly Sync](https://github.com/ipfs/team-mgmt/issues/650) and be part of the Sprint action!

# ⁉️ Do you have questions?

The best place to ask your questions about IPFS, how it works and what you can do with it is at [discuss.ipfs.io](http://discuss.ipfs.io). We are also available at the `#ipfs` channel on Freenode, which is also [accessible through our Matrix bridge](https://riot.im/app/#/room/#freenode_#ipfs:matrix.org).