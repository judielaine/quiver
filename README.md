# quiver

Verifiable credentials offer some novel features and potential improvements for security and privacy for persons who need to present attributes about themselves attested by other parties.

Not all of the interactions referred to as federated authentication meet this description of transferring attributes; access control decisions have privacy and security concerns that affect all three parties.

That is, there are some use cases where the information that a principal needs to present to a verifier is not a good match to the general use case of verifiable credentials, because of privacy requirements on behalf of the issuer and very limited audiences of verifiers.

There is also a use case where simple credentials (such as "is a student") would release more information than desired due to the identity of the issuer.

WARNING:  the following terminology  should be changed so that they are not R&E specific -- because these are not necessarily R&E limited -- and bridge is OK for current discussion but not necessarily best fit.

This model posits a role for "bridge" issuers. The bridge issuers may

* derive credentials that blind the verifier from the original issuer,
* act as a privacy partition (RFC9614) mediating the originating-issuer - verifier relationship,
* act on behalf of other organizations,
* and act as an identity custodian for participation in R&E systems by independent researchers.

A trust network is needed to verify that a bridge is authorized to represent specific originating issuer, and to facilitate the back channel OAuth network.

## Table of contents

* [Definitions](./defintions.md)
* [Provisioning](./provisioning.md)

## Initial overview

Assume a principal has a some to-be-defined ["R&E standard credentials"](./defintions.md#credentials) by their [home institution](./defintions.md#participants) including a correlatable identifier comparable to the [general purpose subject identifier](https://docs.oasis-open.org/security/saml-subject-id-attr/v1.0/cs01/saml-subject-id-attr-v1.0-cs01.html#_Toc536097226). The principal has used that credential at a [bridge issuer](./defintions.md#participants) to establish ["R&E bridge credentials"](./defintions.md#credentials). [Note](./defintions.md#home-institution-privacy)

The bridge credentials are very simple, identifying the bridge and a short lived identifier for the principal.

When the principal attempts access at some resource that is constrained to provide access based on decisions of their home institution, the principal is prompted to present a bridge credential.

On receipt of the bridge credential, in concert with the OpenID federation metadata, the verifier should be able to identify the bridge issuer's `OAuth authorization server` and the `OAuth protected resource` for requesting the token associated with the principal's temporary identifier from the bridge. [Note]

When the bridge receives 

## Quiver?

In mathematics, especially representation theory, a quiver is another name for a multidigraph; that is, a directed graph where loops and multiple arrows between two vertices are allowed. [Wikipedia](https://en.wikipedia.org/wiki/Quiver_(mathematics))

A quiver also is a object that contains arrows for archers.

I don't assert that this model is a multigraph or made of quivers in any way. Nor should there be any implication that the wallet metaphor would better be served with a quiver metaphor.

It is a nice resonant word, though, with arrows and graphs, that provides for a useful code name.
