signet aims to ease the process of signing
GPG keys, or rather their individual UIDs.

It behaves in a similar manner to eg. caff,
but has less requirements and fewer configuration
options.

Basically, signet is a shell wrapper around
numerous calls to gpg itself.

GOAL
----
Have an easy way to sign keys on online as
offline machines, by allowing import and
export by multiple methods (eg. files,
key servers)

BASIC OPERATION
---------------
signet first queries the PRIVATE_SIGNER_KEYRING
(defaults to ~/.gnupg/secring.gpg) for secret keys 
suitable for signing and lets the user choose the
key she wants to sign with.

In the next step, the keys to be signed are imported
into a temporary keyring via multiple possible imports
(keyserver, exported files, complete keyrings).

Thereafter, UIDs are individually brought before the
user to sign or reject to do so, and then exported
signature for signature into their own files
suitable for emailing to the respective UIDs.
