# Model definitions

## Participants

Define a **home institution** as either

* an academic or research institution that does
proofing of an identity and issues an identifier; or
* an institution that uses
a national credential.

Define a **virtual organization** as a R&E function that maintains some attributes about
and has access control requirements for  members of academia and optionally independent researchers.

Define a **bridge member** as a home institution or VO that allows a bridge to issue R&E credentials of various types on its behalf.

### Home institution privacy

Note the home institution is motivated to use a bridge issuer for the bridge credentials in order to partition the identity of the home institution from verifiers that are not related to the home institution.

## Credentials

Define **"R&E standard credentials"** to be verifiable credentials as defined by R&E,
signed with the home institution's identity, and including a correlatable identifier.

Define **"R&E blinded credentials"** to be verifiable credentials that indicate
R&E membership. For students, consider credentials attesting ISCED 2011 levels ("Is
primary student","Is tertiary student") See eduPersonAffiliation.

Define **"R&E access credentials"** to be verifiable credentials that include temporary
IDs and validation endpoint(s) which can be used to acquire an access token.

### R&E standard credentials

MUST have long-lived, non-reassignable, omni-directional identifier suitable for use as a globally-unique external key.

### Multiple blinded or access credentials

[ ] How to address having multiple home institutions or VOs that may grant access?

* Note that the name and description of the credential appear to be released to the verifier, so if the point is to prevent the verifier from knowing that the user is attempting access based on their relationship with institution X, the name of the credential shouldn't be "Insitution X Access."

[ ] Presumably users might want  combined access credentials? The bridge supports three of my home or virtual organizations -- i don't care about releasing all three affiliations if it means i can get access faster.

## APIs

### Bridge API for verifiers

Ideally, the temporary identifier meets criteria such that it can be used as the token resource id for a call such as: `GET /bridgeDocument/[temporaryID]`
