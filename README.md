# DNSChain

[![npm version](https://badge.fury.io/js/dnschain.svg)](https://npmjs.org/package/dnschain) [![Build Status](https://img.shields.io/travis/okTurtles/dnschain/master.svg?label=build%20(master))](https://travis-ci.org/okTurtles/dnschain) [![Build Status](https://img.shields.io/travis/okTurtles/dnschain/dev.svg?label=build%20(dev))](https://travis-ci.org/okTurtles/dnschain) [![Gitter](https://img.shields.io/badge/GITTER-JOIN%20CHAT%20%E2%86%92-brightgreen.svg)](https://gitter.im/okTurtles/dnschain)

There is a problem with how the Internet works today:

- HTTPS [is not secure](http://okturtles.com/#not-secure). Like most "secure" communications protocols,
  it is susceptible to undetectable public-key substitution MITM-attacks (example: [Apple iMessages](https://www.taoeffect.com/blog/2014/11/update-on-imessages-security/)).
- Netizens do not own their online identities. We either borrow them from
  companies like twitter, or rent then from organizations like ICANN.

These problems arise out of two core Internet protocols:
[DNS](https://en.wikipedia.org/wiki/Domain_Name_System) and [X.509](https://en.wikipedia.org/wiki/X.509).

DNSChain offers a free and secure decentralized alternative while remaining backwards compatible
with traditional DNS.

It compares favorably to [the alternatives](docs/Comparison.md), and provides the following features:
︎
<!-- This extra line is necessary for table to render properly. -->
|                                                                          | DNSChain           | X.509 PKI with [Certificate Transparency][ct] |
|:-------------------------------------------------------------------------|:-------------------|:----------------------------------------------|
| __MITM-proof'ed [Internet connections][mitm]__                           | :white_check_mark: | :x:                                           |
| __Secure and simple [GPG key distribution][gpg]__                        | :white_check_mark: | :x:                                           |
| __MITM-proof RESTful [API to blockchain][api]__                          | :white_check_mark: | :x:                                           |
| __Free and [actually-secure][free] SSL certificates__                    | :white_check_mark: | :x:                                           |
| __Stops many [denial-of-service attacks][dos]__                          | :white_check_mark: | :x:                                           |
| __Certificate revocation [that actually works][rev]__                    | :white_check_mark: | :x:                                           |
| __DNS-based [censorship circumvention][cens]__                           | :white_check_mark: | :x:                                           |
| __Prevents [domain theft][theft] ("seizures")__                          | :white_check_mark: | :x:                                           |
| __Access blockchain [domains like `.bit`, `.p2p`, `.nxt`, `.eth`][use]__ | :white_check_mark: | :x:                                           |
| __Certificate transparency (publicly auditable log of certs)__           | :white_check_mark: | :white_check_mark: ([maybe][ct])              |

[ct]: https://blog.okturtles.com/2015/03/certificate-transparency-on-blockchains/
[mitm]: docs/What-is-it.md#MITMProof
[gpg]: docs/What-is-it.md#GPG
[free]: docs/What-is-it.md#Free
[dos]: docs/What-is-it.md#DDoS
[rev]: docs/What-is-it.md#Revocation
[cens]: docs/What-is-it.md#Censorship
[theft]: https://www.techdirt.com/articles/20141006/02561228743/5000-domains-seized-based-sealed-court-filing-confused-domain-owners-have-no-idea-why.shtml
[use]: docs/How-do-I-use-it.md
[api]: docs/What-is-it.md#API

**:star: See Also: [Comparison](docs/Comparison.md) and [Security Model](docs/Security-Model.md)**

**:star: April 21, 2017: Comparison of [DPKI](https://github.com/okTurtles/dnschain/issues/180#issuecomment-255641398) to [CONIKS, Key Transparency, Certificate Transparency](https://blog.okturtles.com/2017/02/coniks-vs-key-transparency-vs-certificate-transparency-vs-blockchains/)**

## Documentation

### [:book: What is it?](docs/What-is-it.md)

- DNSChain replaces X.509 PKI with the blockchain
- MITM-proof authentication
- Simple and secure GPG key distribution
- Secure, MITM-proof RESTful API to blockchains
- Free SSL certificates become possible
- Prevents DDoS attacks
- Certificate revocation that actually works
- DNS-based censorship circumvention
- Other features: testing suite, rate-limiting, and caching

### [:book: Using DNSChain](docs/How-do-I-use-it.md)

- Free public DNSChain servers
- Access blockchain domains like `okturtles.bit`
- Registering blockchain domains and identities
- Encrypt communications end-to-end without relying on untrustworthy third-parties
- Unblock censored websites *(coming soon!)*
- And more!

### [:book: Running your own DNSChain server](docs/How-do-I-run-my-own.md)

- Requirements
- Getting Started
- Configuration
- Guide: Setting up a DNSChain server with Namecoin and PowerDNS
- *Coming Soon: securing HTTPS websites with DNSChain.*

### [:book: Developers](docs/Developers.md)

- Securing Your Apps With DNSChain
- Contributing to DNSChain development
- Adding support for your favorite blockchain
- Running Tests

## Community

- [Forums](https://forums.okturtles.com)
- [@DNSChain](https://twitter.com/dnschain) + [@okTurtles](https://twitter.com/okTurtles)
- [![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/okTurtles/dnschain)

## Other Resources

__:tv: Watch__

- [okTurtles + DNSChain Demo at SOUPS 2014 EFF CUP](https://www.youtube.com/watch?v=7QLaKW8ABy4)
- [Blockchain University lecture on DNSChain](https://www.youtube.com/watch?v=GJd5uECEkSs) (2h+, but you will [know kung-fu](https://www.youtube.com/watch?v=6vMO3XmNXe4) afterward!)
- [SF Bitcoin Meetup: Securing online communications with the blockchain](https://www.youtube.com/watch?v=Qy1x3Ud8LCI)
- [SF Bitcoin Developers Meetup: Deep Dive into Namecoin and DNSChain](https://www.youtube.com/watch?v=wUiMIy9urTA)

__:speaker: Listen__

- [P2P Connects Us Podcast on DNSChain](http://letstalkbitcoin.com/blog/post/p2p-connects-us-episode-four)
- [Frontier Podcast on DNSChain, DNSCrypt, MITM attacks, & more](http://reelsense.tv/frontier/101)
- [Beyond Bitcoin Hangouts with Bitshares crew on DNSChain](https://soundcloud.com/beyond-bitcoin-hangouts/beyond-bitcoin-hangout-greg-slepak-dnschain-2014-10-24)
- [Katherine Albrecht's privacy-focused radio show](http://www.katherinealbrecht.com/show-archives/2014/06/19/)

__:page_facing_up: Read__

- Engadget: [New web service prevents spies from easily intercepting your data](http://www.engadget.com/2014/09/29/okturtles/)
- Let's Talk Bitcoin: [Security in Decentralized Domain Name Systems](http://letstalkbitcoin.com/blog/post/security-in-decentralized-domain-name-systems)
- ProgrammableWeb: [Can the blockchain replace ~~SSL~~ X.509?](https://www.programmableweb.com/news/can-blockchain-replace-ssl/analysis/2015/03/17)
- [An intro to DNSChain: Low-trust access to definitive data sources](http://simondlr.com/post/94988956673/an-intro-to-dnschain-low-trust-access-to)
- [How to setup a blockchain DNS server with DNSChain](docs/setting-up-dnschain-namecoin-powerdns-server.md)
- [The Trouble with Certificate Transparency](https://blog.okturtles.com/2014/09/the-trouble-with-certificate-transparency/)
- [Introducing the dotDNS metaTLD](https://blog.okturtles.com/2014/02/introducing-the-dotdns-metatld/)
- [DNSChain versus...](docs/Comparison.md)

_Have a link? [Let us know](https://twitter.com/dnschain)!_

## Contributors

_Approximate chronological order._

- [Greg Slepak](https://twitter.com/taoeffect) (Original author and current maintainer)
- [Simon Grondin](https://github.com/SGrondin) (Unblock feature: DNS-based censorship circumvention)
- [Matthieu Rakotojaona](https://otokar.looc2011.eu/) (DANE/TLSA contributions and misc. fixes)
- [TJ Fontaine](https://github.com/tjfontaine) (For `native-dns`, `native-dns-packet` modules and related projects)
- [Za Wilgustus](https://twitter.com/ZancasDeArana) (For [pydnschain](https://github.com/okTurtles/pydnschain) contributions)
- [Cayman Nava](https://github.com/WeMeetAgain) (Ethereum support, api.icann.dns, and core developer)
- [Vignesh Anand](https://github.com/vegetableman) (Front-end + back-end for DNSChain admin interface)
- [Mike Ward](https://twitter.com/bocamike) (Documentation)
- [Dionysis Zindros](https://github.com/dionyziz) ([pydnschain](https://github.com/okTurtles/pydnschain) work)
- [Chara Podimata](https://www.linkedin.com/in/charapodimata) ([pydnschain](https://github.com/okTurtles/pydnschain) work)
- [Konstantinos Lolos](https://www.linkedin.com/in/kostislolos) ([pydnschain](https://github.com/okTurtles/pydnschain) work)
- [Anton Wilhelm](https://github.com/toenu23) (Support for [Nxt](http://nxt.org) cryptocurrency)
- [Tim Uy](https://github.com/tofutim) (Ubuntu tutorial)
- [Michael Bumann](https://twitter.com/bumi) (optional CORS support)
- *Your name & link of choice here!*

## Release History

__[Blog post for 0.5 release.](https://blog.okturtles.com/2015/03/dnschain-0-5-released-https-openname-resolver-api-more/)__

###### 0.5.3 - September 5, 2015

- __New Features:__
    + Optional CORS support from [Michael Bumann](https://twitter.com/bumi) (thanks!).
- __Improvements:__
    + Bumped `hiredis` to 0.4.1 for latest iojs compat.

###### 0.5.2 - March 11, 2015

- __Improvements:__
    + Includes tests for verifying NXT support
    + Added [`superagent`](https://github.com/visionmedia/superagent) for simpler HTTP requests
    + Moved `dnsHandler` into `blockchain.coffee` template class
    + Prevent `favicon.ico` requests from filling logs
    + Improved `Comparisons.md` documentation
    + Misc. code and logging improvements
- __Fixes:__
    + #138: Nxt resolver not working
    + #140: Prevent non-json values in Namecoin from returning "Not found"
    + #141: Allow arbitrary namecoin keys, but enforce ICANN domain rules for for `d/`
    + #142 + #120: Make it less likely Travis will fail

###### [:book: Older version notes](HISTORY.md)

Copyright (c) okTurtles Foundation. Licensed under [MPL-2.0 license](http://mozilla.org/MPL/2.0/).
