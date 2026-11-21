# Nexora

Nexora is a SaaS application that allows businesses to create, manage and track QR codes. It supports both static and dynamic QR codes, giving users the flexibility to generate simple QR codes or manage codes whose linked websites can be changed without generating new ones.

The application is designed for businesses that use QR codes for digital menus, marketing campaigns, product information and other purposes. Organisations can manage their QR codes, invite team members and access features based on their subscription plans.

The project is currently under development.

## Features

Nexora is being developed around two main areas.

### QR Code Management

- Generate static and dynamic QR codes.
- Download QR codes for use on websites or printed materials.
- Update websites linked to dynamic QR codes without generating new ones.
- Regenerate static QR codes when a website needs to be corrected.
- Enable or disable dynamic QR codes.
- Track scans and view analytics for dynamic QR codes.
- Organise and manage QR codes within an organisation.

### Subscription Management

- User registration and authentication.
- Organisation and team member management.
- Role-based access control.
- Subscription plans with different features and usage limits.
- QR code usage tracking and quota enforcement.
- Subscription upgrades, downgrades and cancellations.
- Billing and payment integration.

These features will be introduced gradually as development progresses.

## Architecture

Nexora uses a modular monolith architecture, with separate modules for QR code management and subscription management.

Both modules share a single ASP.NET Core API and database infrastructure, while keeping their business logic separate.

The solution is organised into three main areas:

- **SubscriptionManagement** handles organisations, memberships, permissions, subscription plans, billing and feature access.
- **QRManager** handles QR code generation, website updates, redirects and scan analytics.
- **Shared** contains the API and database infrastructure used by both modules.

### Project Structure

```
Nexora/
├── src/
│   ├── SubscriptionManagement/
│   │   ├── SubscriptionManagement.Application/
│   │   ├── SubscriptionManagement.Interface/
│   │   └── SubscriptionManagement.Models/
│   │
│   ├── QRManager/
│   │   ├── QRManager.Application/
│   │   ├── QRManager.Interface/
│   │   └── QRManager.Models/
│   │
│   └── Shared/
│       ├── Nexora.Api/
│       └── Nexora.Data/
│
├── tests/
│   ├── SubscriptionManagement/
│   │   ├── SubscriptionManagement.UnitTests/
│   │   └── SubscriptionManagement.IntegrationTests/
│   │
│   ├── QRManager/
│   │   ├── QRManager.UnitTests/
│   │   └── QRManager.IntegrationTests/
│   │
│   └── Shared/
│       └── Nexora.IntegrationTests/
│
├── docs/
│   ├── subscriptionManagement/
│   ├── qrManager/
│   └── shared/
│
└── Nexora.slnx
```

## Tech Stack

The project uses or is planned to use the following technologies:

- **Backend:** C#, .NET 10, ASP.NET Core
- **Database:** SQL Server, Entity Framework Core
- **Architecture:** Modular Monolith, Repository Pattern, Unit of Work, Dependency Injection
- **Testing:** xUnit, Testcontainers
- **Containerisation:** Docker
- **CI/CD:** GitHub Actions
- **Observability:** OpenTelemetry

Additional technologies will be introduced as needed.

## Development

Nexora is being built incrementally, starting with the core application structure and QR code functionality.

The development process focuses on keeping the code maintainable, separating responsibilities, writing automated tests and documenting important design decisions.

The project will gradually expand to include organisation management, subscription plans, usage limits, scan analytics and payment integration.

## License

This project is licensed under the [MIT License](LICENSE.txt).
