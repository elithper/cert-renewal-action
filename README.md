# cert-renewal-action

This is a small GitHub Action to renew the Let's Encrypt certificate for my personal blog's object storage bucket.

It uses David Coles' [acme-linode-objectstorage](https://github.com/dcoles/acme-linode-objectstorage) to request a new certificate and handle the resulting ACME challenge.

## Prerequisites

For the action to run, `BUCKET_NAME` must be set to the custom domain used for the bucket, e.g. `assets.michaelhoward.kiwi`.

Additionally, two secrets need to be added to the repository:

- `ACCOUNT_KEY`: a Let's Encrypt account key generated with `openssl genrsa 4096`.
- `LINODE_TOKEN`: a Linode API key with the object storage read/write permissions.

## Usage

The action can be triggered manually, but has been scheduled to run on the first day of every month.
