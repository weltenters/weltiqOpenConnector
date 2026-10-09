# weltiq Open Connector

**One interface for broker and exchange orders and accounts.**

[한국어](README.ko.md) · [weltiq](https://weltiq.ai/) · [Questions and ideas](https://github.com/weltenters/weltiqOpenConnector/discussions)

> **Project introduction · source release in preparation.**
> This repository currently contains project and community documentation only. SDK source code, installable packages, and releases are not available yet. The scope below describes what we plan to publish, not a list of currently supported integrations. A release date has not been announced.

## Why we are building this

Broker and exchange APIs use different authentication flows, order formats, account models, and error responses. Developers repeatedly write and maintain the same integration code before they can work on their own tools.

weltiq Open Connector is a planned open-source SDK that brings selected official broker and exchange APIs behind a common order and account interface. Our aim is to make those integrations reusable and inspectable, while keeping each provider's supported features and limitations explicit.

You write the strategy or the tool. The connector handles the API integration. This project does not provide investment recommendations or promise trading results.

## What we plan to publish

- Common interfaces for orders, order status, cancellations, amendments, balances, and positions.
- Adapters for selected official broker and exchange APIs.
- A client for the weltiq paper trading service, so the first guided experience can use virtual funds.
- Provider capability information, error handling contracts, tests, and connection guides.
- Python examples and a command-line client for working with your own account.

Providers differ. An accepted order is not necessarily filled, a cancellation request is not a completed cancellation, and unsupported features must be identified explicitly. Supported providers, environments, and verified operations will be published with each release.

This repository will publish weltiq's integration code. It does not publish or grant access to a broker's trading server. Using a provider's API still requires the account, permissions, and terms that provider specifies.

## How it relates to weltiq

| | Open Connector SDK · planned | weltiq managed service |
|---|---|---|
| Where it runs | Your application and environment | weltiq's hosted service |
| Direct broker credentials | Configured and managed in your environment | Supported connections use the service's credential management |
| Operations and records | Your application integrates the SDK and manages its own operation and storage | Account views, execution records, and managed features follow the service's current availability and plan |
| Paper trading | A client connects to the weltiq paper service | The hosted service provides the paper environment |
| What is being opened | Selected connector code, interfaces, tests, and documentation | The hosted platform is a separate product |

The planned SDK does not include the hosted paper engine, a local simulation engine, strategy or backtesting engines, customer key storage, billing, or a multi-user service backend. Some managed connectors may remain outside the public SDK; the two support lists will be identified separately.

The guided first connection is planned around weltiq paper trading, which requires a weltiq account and follows its service limits. Direct connections to other supported providers are intended to work without requiring a weltiq account. Keys for those direct connections stay in your environment and are not automatically sent to weltiq.

For what you can use today, see [weltiq's API, MCP, and TradingView connections](https://weltiq.ai/integrations) and [service documentation](https://weltiq.ai/docs). Those service connections are separate from the unreleased Open Connector SDK.

## Why open source

We want developers to be able to inspect how requests are authenticated, how orders and errors are translated, and what each connector supports. Shared contracts, tests, documentation, and release history should make those boundaries easier to understand and maintain.

We plan to release the SDK under **Apache-2.0**, allowing commercial reuse under that license. The final license will accompany the source release after the publication scope is verified. No SDK source license is being applied to weltiq's private service code by this announcement. Provider API and market-data terms remain separate.

## Follow the project and suggest a connector

- Use [Discussions](https://github.com/weltenters/weltiqOpenConnector/discussions) for questions, use cases, and connector suggestions.
- Use [Issues](https://github.com/weltenters/weltiqOpenConnector/issues) for a concrete problem with the published documentation.
- For a connector suggestion, include the provider name, its official API documentation link, and the operations you need. Do not include account details or credentials.
- weltiq maintains the project. External pull requests are not accepted at this stage. See [CONTRIBUTING.md](CONTRIBUTING.md).
- Report security concerns privately as described in [SECURITY.md](SECURITY.md).

Source publication, verified connector coverage, installation instructions, and releases will be announced here as they become available. Suggestions inform prioritization; they do not commit us to a release date or provider integration.

Maintained by weltiq / Weltenters. [Visit weltiq](https://weltiq.ai/).
