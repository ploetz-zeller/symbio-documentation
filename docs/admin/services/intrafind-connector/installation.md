# Installation

## Requirements

- Azure Cloud Subscription
- Windows-based Azure AppService Plan
- Windows-based Azure AppService running .NET 5.0
- Azure SQL Database

The connector is provided as a service.
Symbioworld will host and manage it for your Symbio installation.

Please contact us at `info@symbioworld.com` to discuss your use case or a potential proposal.

## Installation

The connector service is automatically provisioned and deployed during CI/CD builds.
A three-stage process ensures production readiness:
- DEV stage: integration tests ensure interoperability with current versions of Symbio and Intrafind's iFinder.
- TEST stage: in-house day-to-day usage ensures a general usability
- PROD stage: the production stage is split into a quality assurance/pre-production stage where your test environment is connected so you can ensure and approve updates, and the actual production stage where your organization actively works with Symbio
