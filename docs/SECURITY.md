# Public Showcase Security Notes

This repository is intentionally documentation-first and does not mirror the production source tree.

## Disclosure Policy

The following categories are excluded from this repository:

- `.env` files and environment values
- API keys and access tokens
- Database credentials
- Privileged backend/service credentials
- Authentication secrets
- Webhook secrets
- Private administrative URLs
- Customer or client information
- Production database exports
- Internal authorization policies
- Proprietary workflow implementation
- Business-sensitive configuration

## Public Code Samples

Any future code samples added to this showcase should meet all of the following conditions before publication:

1. The sample is useful for technical evaluation.
2. It does not expose production credentials or identifiers.
3. It does not reproduce proprietary business logic.
4. It does not reveal privileged authorization or infrastructure details.
5. It can be understood independently of the production repository.
6. Example data is synthetic.

## Production Source

The complete application is maintained separately from this showcase. Access to production source should only be granted deliberately and on a case-by-case basis when deeper technical review is appropriate.

## Reporting

This repository is a portfolio case study and should not be treated as a production deployment repository. Security concerns relating to the public showcase can be reported privately to the repository owner rather than posted with sensitive details in a public issue.
