# github-connect

Example project on how to connect your nostr and github accounts together.
[NIP-05](https://github.com/nostr-protocol/nips/blob/master/05.md) is a way to verify connection between domain names and nostr accounts. Because github pages requires ownership over github repositories, we can leverage this fact to prove a github user owns a nostr account.

# Steps to produce [nostr-name]@[github-name].github.io/[repo]

* fork https://github.com/nostrize/github-connect
* edit _site/.well-known/nostr.json (change with your nostr username you want to use and pubkey accordingly)
* Go to Settings -> Pages -> Set Source: Github actions
* Go to Actions -> Enable workflows if necessary
* Go to Workflows -> Deploy static site to Pages -> Run workflow
* Check 
  * Evaluated environment url: https://[github-name].github.io/github-connect/
* Check NIP-05 URL on browser: https://[github-name].github.io/github-connect/.well-known/nostr.json
* Edit your profile in [metadata nostr](https://metadata.nostr.com/) using alby extension or nos2x
  * check NIP-05 is valid for [nostr-name]@[github-name].github.io/github-connect

# Steps to produce [nostr-name]@[github-name].github.io

* Same steps, this time you need to rename your forked repo to `[github-name].github.io`, then your NIP-05 address will be in the short form. Nostrize supports both short and long forms.

# Extension

* You can specify extra data in nostr.json for your nostrize account that will be used in github: an icon (as a URL), emoji or the type of the account (user or organization)
