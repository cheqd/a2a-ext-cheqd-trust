# cheqd Trust Extensions for A2A

> ## ⚠️ DRAFT — nothing is specified or implemented
>
> **This is not an A2A extension.** It has not been proposed to the A2A project, has no maintainer sponsorship, and is not official, experimental or recognised in any A2A process. See [A2A Extension and Protocol Binding Governance](https://a2a-protocol.org/latest/topics/extension-and-binding-governance/) for what those terms mean.
>
> **The specification is not written.** The extension URIs below are proposals, not allocations — one of them sits in a namespace cheqd does not own (see [Open questions](#open-questions)).
>
> **Do not implement against this.** Nothing here is agreed, reviewed or stable. This is an early exploration, not a cheqd product.

An exploration of how an A2A agent might prove, at the request boundary, that it is a known agent acting within granted authority — with trust state anchored on cheqd.

## Proposed shape

Two independently activatable extensions. Both URIs are provisional.

| Extension | Proposed URI | Would own |
|---|---|---|
| Request/response proof | `https://kya-os.org/a2a/ext/proof/v1` | Binding the `org.kya-os/proof.v1` holder-of-key profile to A2A's message envelope |
| cheqd trust resolution | `https://cheqd.io/a2a/ext/trust/v1` | `did:cheqd` resolution, reciprocal `alsoKnownAs` linkage, DID-Linked Resource policy, credential status |

They would compose, but neither would require the other.

## Open questions

1. **The proof URI namespace is not cheqd's.** `org.kya-os/proof.v1` is a [DIF TAAWG](https://identity.foundation/working-groups/trusted-agents.html) specification and `kya-os.org` is their namespace. Minting a binding URI there requires agreement with that working group. The alternative is a cheqd-owned URI, at the price of splitting the wire format and its identifier across two namespaces.
2. **Whether to propose this to the A2A project at all**, and if so, when relative to interoperability testing.

## Why this repository is separate

The implementation would live in [`cheqd/agent-trust`](https://github.com/cheqd/agent-trust) and ship to npm. This repository holds only a specification and a reference sample, so it could be contributed to the A2A project without carrying cheqd's AP2 work or build tooling — the same shape as [`experimental-ext-oid4vp-auth`](https://github.com/a2aproject/experimental-ext-oid4vp-auth), whose sample consumes its implementation from npm.

Licensed Apache 2.0 from the first commit, because official A2A extensions must be Apache 2.0 and relicensing later would need every contributor's agreement.

## Contents

- [`v1/`](./v1) — the specification. **Not yet written.**
- [`sample/`](./sample) — reference implementation. **Not yet written.**

## Contributing

This project uses a [Developer Certificate of Origin](./DCO). Sign off your commits with `git commit -s` — see [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

[Apache 2.0](./LICENSE)
