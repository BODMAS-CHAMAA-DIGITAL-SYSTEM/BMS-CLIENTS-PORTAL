# Bms Clients Portal — Architecture Notes

## Component boundary

A controlled portal for approved business, project and investment partners.

## Upstream and downstream dependencies

- Frontend components communicate with the BMS API over HTTPS.
- The API owns business rules, authorisation and trusted data operations.
- Database changes are managed through the BMS-DATABASE migration process.
- Payment-provider events are received by BMS-HOOK-SERVICE and handed to the API for validation and recording.

Only dependencies relevant to this component should be implemented here.

## Environment separation

Use separate development, staging and production configuration. Never reuse
production credentials in local development or test environments.

## Change control

Document breaking changes and coordinate them with dependent repositories
before deployment.
