# Knock (knock-app)

Knock is notifications infrastructure as a service — a product and customer messaging platform you use to power transactional, lifecycle, broadcast, and in-product messaging across email, SMS, push, in-app, in-app guides, chat (Slack / Discord / Teams / WhatsApp), and outbound webhooks. Knock exposes two REST surfaces — a runtime API (api.knock.app) for triggering workflows and managing recipients/messages, and a Management API (control.knock.app) for resource CRUD — together with official SDKs in Node, Python, Ruby, Go, Elixir, Java, .NET, PHP and mobile (Swift, Kotlin, Flutter, React Native, Expo); a CLI; a remote MCP server; an agent toolkit for OpenAI / AI SDK / Langchain / Mastra; outbound webhooks; AI agent workflow steps; SlackKit and TeamsKit; and a git-style environment / branch / commit model for safe promotion of notification resources.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/knock-app/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/knock-app/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Notifications
- Messaging
- Infrastructure
- Workflows
- Cross-Channel
- Email
- SMS
- Push
- In-App
- Chat
- Slack
- Webhooks
- MCP
- AI Agents
- Developer Platform

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Knock Workflows API

Trigger and cancel notification workflows and inspect workflow recipient runs. Workflows are Knock's core programmable model — orchestrating channel steps (email, SMS, push, in-app, chat, webhook) and function steps (batch, delay, branch, throttle, fetch, AI agent, trigger-workflow) with conditions and preferences across recipients.

- **Human URL:** [https://docs.knock.app/api-reference/workflows](https://docs.knock.app/api-reference/workflows)

#### Tags

- Workflows
- Notifications
- Messaging
- Triggers

#### Properties

- [Documentation](https://docs.knock.app/api-reference/workflows)
- [Documentation](https://docs.knock.app/send-notifications/triggering-workflows/api)
- [OpenAPI](openapi/knock-workflows-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-workflows-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-workflows-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/knock-workflow-trigger-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Examples](examples/knock-trigger-workflow-example.json)

### Knock Users API

Identify, list, update, delete, and merge users plus manage their channel data, preferences, in-app feeds, guides, subscriptions, messages, and schedules. The primary recipient surface for Knock.

- **Human URL:** [https://docs.knock.app/api-reference/users](https://docs.knock.app/api-reference/users)

#### Tags

- Users
- Recipients
- Preferences
- In-App Feed
- Guides

#### Properties

- [Documentation](https://docs.knock.app/api-reference/users)
- [OpenAPI](openapi/knock-users-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-users-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-users-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Examples](examples/knock-identify-user-example.json)

### Knock Messages API

Read, list, and update Knock messages — the per-recipient delivery records produced by workflow runs. Includes activity, delivery log, and event timelines plus mark-as-seen/read/interacted/archived single and batch endpoints.

- **Human URL:** [https://docs.knock.app/api-reference/messages](https://docs.knock.app/api-reference/messages)

#### Tags

- Messages
- Engagement
- Delivery

#### Properties

- [Documentation](https://docs.knock.app/api-reference/messages)
- [OpenAPI](openapi/knock-messages-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-messages-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-messages-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/knock-message-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Knock Objects API

Create and manage non-user Objects in Knock and their channel data, preferences, subscriptions, and messages. Objects model accounts, projects, devices, or any non-human notification target.

- **Human URL:** [https://docs.knock.app/api-reference/objects](https://docs.knock.app/api-reference/objects)

#### Tags

- Objects
- Non-User Recipients

#### Properties

- [Documentation](https://docs.knock.app/api-reference/objects)
- [OpenAPI](openapi/knock-objects-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-objects-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-objects-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Tenants API

Manage Tenants — the top-level accounts or workspaces in your product. Tenants power tenant-scoped branding, preferences, and message-targeting.

- **Human URL:** [https://docs.knock.app/api-reference/tenants](https://docs.knock.app/api-reference/tenants)

#### Tags

- Tenants
- Multi-Tenancy
- Branding

#### Properties

- [Documentation](https://docs.knock.app/api-reference/tenants)
- [OpenAPI](openapi/knock-tenants-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-tenants-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-tenants-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Schedules API

Create, list, update, and delete workflow Schedules. Schedules fire workflows at one-off or recurring times for specific recipients with timezone and repeat-rule support.

- **Human URL:** [https://docs.knock.app/api-reference/schedules](https://docs.knock.app/api-reference/schedules)

#### Tags

- Schedules
- Recurring
- Cron

#### Properties

- [Documentation](https://docs.knock.app/api-reference/schedules)
- [Documentation](https://docs.knock.app/concepts/schedules)
- [OpenAPI](openapi/knock-schedules-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-schedules-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-schedules-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Examples](examples/knock-create-schedule-example.json)

### Knock Audiences API

Manage static Audiences and their members. Audiences power lifecycle messaging — when a user joins an audience, configured workflows fire automatically.

- **Human URL:** [https://docs.knock.app/api-reference/audiences](https://docs.knock.app/api-reference/audiences)

#### Tags

- Audiences
- Segments
- Lifecycle

#### Properties

- [Documentation](https://docs.knock.app/api-reference/audiences)
- [OpenAPI](openapi/knock-audiences-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-audiences-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-audiences-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Channels API

Inspect channels and run bulk message-status updates scoped to a channel. Channels represent configured provider integrations (Resend, SendGrid, Twilio, APNS, Slack, etc.).

- **Human URL:** [https://docs.knock.app/api-reference/channels](https://docs.knock.app/api-reference/channels)

#### Tags

- Channels
- Providers
- Bulk

#### Properties

- [Documentation](https://docs.knock.app/api-reference/channels)
- [OpenAPI](openapi/knock-channels-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-channels-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-channels-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Providers API

OAuth provider endpoints supporting SlackKit, MS Teams Kit, and other inbound provider integrations — authorize, revoke, and inspect connections to chat providers on behalf of users or tenants.

- **Human URL:** [https://docs.knock.app/api-reference/providers](https://docs.knock.app/api-reference/providers)

#### Tags

- Providers
- OAuth
- SlackKit
- TeamsKit

#### Properties

- [Documentation](https://docs.knock.app/api-reference/providers)
- [OpenAPI](openapi/knock-providers-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-providers-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-providers-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Integrations API

Inspect integrations configured for the current environment. Used by SlackKit and TeamsKit clients to discover the destinations available for a recipient.

- **Human URL:** [https://docs.knock.app/api-reference/integrations](https://docs.knock.app/api-reference/integrations)

#### Tags

- Integrations
- SlackKit
- TeamsKit

#### Properties

- [Documentation](https://docs.knock.app/api-reference/integrations)
- [OpenAPI](openapi/knock-integrations-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-integrations-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-integrations-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Bulk Operations API

Track and inspect long-running bulk operations. Many Knock endpoints (bulk identify users, bulk delete, bulk channel-status updates) return a bulk-operation handle; this surface exposes its lifecycle.

- **Human URL:** [https://docs.knock.app/api-reference/bulk_operations](https://docs.knock.app/api-reference/bulk_operations)

#### Tags

- Bulk
- Operations
- Async

#### Properties

- [Documentation](https://docs.knock.app/api-reference/bulk_operations)
- [OpenAPI](openapi/knock-bulk-operations-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-bulk-operations-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-bulk-operations-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Notify API

Internal notify endpoints used by the Knock event-driven trigger surface. Used to send notifications when workflows fire from source events, schedules, audiences, or programmatic triggers.

- **Human URL:** [https://docs.knock.app/api-reference/overview](https://docs.knock.app/api-reference/overview)

#### Tags

- Notify
- Events

#### Properties

- [OpenAPI](openapi/knock-notify-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-notify-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-notify-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Management API (mAPI)

Knock Management API (mAPI) — the resource-management surface at control.knock.app. Programmatic CRUD over Workflows, Channels, Email Layouts, Partials, Templates, Translations, Audiences, Broadcasts, Guides, Message Types, Variables, Members, Channel Groups, Environments, Branches, Commits, and API Keys. Powers the Knock CLI and MCP server.

- **Human URL:** [https://docs.knock.app/mapi](https://docs.knock.app/mapi)

#### Tags

- Management
- Resources
- CLI
- MCP
- DevOps

#### Properties

- [Documentation](https://docs.knock.app/mapi)
- [Documentation](https://docs.knock.app/developer-tools/management-api)
- [OpenAPI](openapi/knock-management-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/knock-management-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-management-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Knock Outbound Webhooks

Outbound webhooks fire message lifecycle (sent, delivered, seen, read, interacted, archived, link_clicked, bounced, undelivered) and environment-change (workflow / email_layout / translation / partial / source_event_action updates and commits) events as JSON POSTs to subscriber URLs configured in the Knock dashboard.

- **Human URL:** [https://docs.knock.app/developer-tools/outbound-webhooks/overview](https://docs.knock.app/developer-tools/outbound-webhooks/overview)

#### Tags

- Webhooks
- Events
- AsyncAPI

#### Properties

- [Documentation](https://docs.knock.app/developer-tools/outbound-webhooks/overview)
- [Documentation](https://docs.knock.app/developer-tools/outbound-webhooks/event-types)
- [AsyncAPI](asyncapi/knock-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/knock-audiences-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-audiences-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-bulk-operations-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-bulk-operations-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-channels-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-channels-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-integrations-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-integrations-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-management-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-management-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-messages-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-messages-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-notify-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-notify-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-objects-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-objects-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-providers-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-providers-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-schedules-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-schedules-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-tenants-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-tenants-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-users-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-users-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/knock-workflows-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/knock-workflows-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://knock.app)
- [Documentation](https://docs.knock.app/)
- [Documentation](https://docs.knock.app/api-reference/overview)
- [Documentation](https://docs.knock.app/mapi)
- [Getting Started](https://docs.knock.app/getting-started/what-is-knock)
- [Getting Started](https://docs.knock.app/getting-started/quick-start/general)
- [Sign Up](https://dashboard.knock.app/signup)
- [Authentication](https://docs.knock.app/api-reference/overview/authentication)
- [Rate Limits](https://docs.knock.app/api-reference/overview/rate-limits)
- [Rate Limits](https://docs.knock.app/api-reference/overview/batch-rate-limits)
- [Idempotency](https://docs.knock.app/api-reference/overview/idempotent-requests)
- [Pagination](https://docs.knock.app/api-reference/overview/pagination)
- [Errors](https://docs.knock.app/api-reference/overview/errors)
- [Errors](https://docs.knock.app/api-reference/overview/error-codes)
- [Status Page](https://status.knock.app)
- [Changelog](https://docs.knock.app/changelog)
- [Pricing](https://knock.app/pricing)
- [Terms of Service](https://knock.app/legal/terms)
- [Privacy Policy](https://knock.app/legal/privacy)
- [Trust Center](https://trust.knock.app)
- [Blog](https://knock.app/blog)
- [GitHub Organization](https://github.com/knocklabs)
- [SDK](https://github.com/knocklabs/knock-node)
- [SDK](https://github.com/knocklabs/knock-python)
- [SDK](https://github.com/knocklabs/knock-ruby)
- [SDK](https://github.com/knocklabs/knock-go)
- [SDK](https://github.com/knocklabs/knock-elixir)
- [SDK](https://github.com/knocklabs/knock-java)
- [SDK](https://github.com/knocklabs/knock-dotnet)
- [SDK](https://github.com/knocklabs/knock-php)
- [SDK](https://github.com/knocklabs/knock-swift)
- [SDK](https://github.com/knocklabs/knock-android)
- [SDK](https://github.com/knocklabs/knock-flutter)
- [SDK](https://github.com/knocklabs/javascript)
- [SDK](https://github.com/knocklabs/knock-mgmt-node)
- [SDK](https://github.com/knocklabs/knock-mgmt-python)
- [SDK](https://github.com/knocklabs/knock-mgmt-go)
- [Tool](https://github.com/knocklabs/knock-cli)
- [Tool](https://mcp.knock.app/mcp)
- [Tool](https://github.com/knocklabs/knock-mcp)
- [Tool](https://github.com/knocklabs/agent-toolkit)
- [Tool](https://github.com/knocklabs/telegraph)
- [Code Examples](https://github.com/knocklabs/in-app-notifications-example-nextjs)
- [Code Examples](https://github.com/knocklabs/slack-kit-example)
- [Code Examples](https://github.com/knocklabs/ios-example-app)
- [Code Examples](https://github.com/knocklabs/ai-agent-examples)
- [Code Examples](https://github.com/knocklabs/workflow-templates)
- [Code Examples](https://github.com/knocklabs/notion-feed-example)
- [Code Examples](https://github.com/knocklabs/marketplace-example)
- [Plugins](https://github.com/knocklabs/react-notification-feed)
- [Webhooks](https://docs.knock.app/developer-tools/outbound-webhooks/overview)
- [Webhooks](https://docs.knock.app/developer-tools/outbound-webhooks/event-types)
- [AsyncAPI](asyncapi/knock-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Plans](plans/knock-plans-pricing.yml)
- [Rate Limits](rate-limits/knock-rate-limits.yml)
- [Fin Ops](finops/knock-finops.yml)
- [JSON-LD](json-ld/knock-app-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/knock-app-vocabulary.yml)
- [Spectral Rules](rules/knock-app-rules.yml)
- [Documentation](https://docs.knock.app/ai/mcp-server)
- [Documentation](https://docs.knock.app/ai/agent)
- [Documentation](https://docs.knock.app/ai/skills)
- [Documentation](https://docs.knock.app/ai/agent-function)
- [Documentation](https://docs.knock.app/developer-tools/service-tokens)
- [Documentation](https://docs.knock.app/concepts/environments)
- [Documentation](https://docs.knock.app/concepts/commits)
- [Documentation](https://docs.knock.app/template-editor/reference-liquid-helpers)
- [Forum](https://knock.app/community)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
