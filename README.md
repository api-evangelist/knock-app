# Knock (knock-app)

Knock is notifications infrastructure as a service — a product and customer messaging platform you use to power transactional, lifecycle, broadcast, and in-product messaging across email, SMS, push, in-app, in-app guides, chat (Slack / Discord / Teams / WhatsApp), and outbound webhooks. Knock exposes two REST surfaces — a runtime API at `api.knock.app` for triggering workflows and managing recipients/messages, and a Management API at `control.knock.app` for resource CRUD — together with official SDKs, a CLI, a remote MCP server, an agent toolkit, AI agent workflow steps, SlackKit / TeamsKit, and a git-style environment / branch / commit model for safe promotion of notification resources.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/knock-app/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

Notifications, Messaging, Infrastructure, Workflows, Cross-Channel, Email, SMS, Push, In-App, Chat, Slack, Webhooks, MCP, AI Agents, Developer Platform

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Knock Workflows API
Trigger and cancel notification workflows and inspect workflow recipient runs.

**Human URL:** [https://docs.knock.app/api-reference/workflows](https://docs.knock.app/api-reference/workflows)

- [OpenAPI](openapi/knock-workflows-api-openapi.yml)
- [JSON Schema — Workflow Trigger](json-schema/knock-workflow-trigger-schema.json)
- [Example — Trigger Workflow](examples/knock-trigger-workflow-example.json)
- [Naftiko Capability](capabilities/workflows.yaml)

### Knock Users API
Identify, list, update, delete, and merge users plus manage channel data, preferences, in-app feeds, guides, subscriptions, messages, and schedules.

**Human URL:** [https://docs.knock.app/api-reference/users](https://docs.knock.app/api-reference/users)

- [OpenAPI](openapi/knock-users-api-openapi.yml)
- [Example — Identify User](examples/knock-identify-user-example.json)
- [Naftiko Capability](capabilities/users.yaml)

### Knock Messages API
Read, list, and update per-recipient delivery records — the Messages produced by workflow runs.

**Human URL:** [https://docs.knock.app/api-reference/messages](https://docs.knock.app/api-reference/messages)

- [OpenAPI](openapi/knock-messages-api-openapi.yml)
- [JSON Schema — Message](json-schema/knock-message-schema.json)
- [Naftiko Capability](capabilities/messages.yaml)

### Knock Objects API
Create and manage non-user Objects in Knock and their channel data, preferences, subscriptions, and messages.

**Human URL:** [https://docs.knock.app/api-reference/objects](https://docs.knock.app/api-reference/objects)

- [OpenAPI](openapi/knock-objects-api-openapi.yml)
- [Naftiko Capability](capabilities/objects.yaml)

### Knock Tenants API
Manage Tenants — top-level accounts or workspaces in your product.

**Human URL:** [https://docs.knock.app/api-reference/tenants](https://docs.knock.app/api-reference/tenants)

- [OpenAPI](openapi/knock-tenants-api-openapi.yml)
- [Naftiko Capability](capabilities/tenants.yaml)

### Knock Schedules API
Create, list, update, and delete one-off and recurring workflow Schedules.

**Human URL:** [https://docs.knock.app/api-reference/schedules](https://docs.knock.app/api-reference/schedules)

- [OpenAPI](openapi/knock-schedules-api-openapi.yml)
- [Example — Create Schedule](examples/knock-create-schedule-example.json)
- [Naftiko Capability](capabilities/schedules.yaml)

### Knock Audiences API
Manage static Audiences and their members — used to drive lifecycle workflow triggers.

**Human URL:** [https://docs.knock.app/api-reference/audiences](https://docs.knock.app/api-reference/audiences)

- [OpenAPI](openapi/knock-audiences-api-openapi.yml)
- [Naftiko Capability](capabilities/audiences.yaml)

### Knock Channels API
Inspect channels and run bulk message-status updates scoped to a channel.

**Human URL:** [https://docs.knock.app/api-reference/channels](https://docs.knock.app/api-reference/channels)

- [OpenAPI](openapi/knock-channels-api-openapi.yml)
- [Naftiko Capability](capabilities/channels.yaml)

### Knock Providers API
OAuth provider endpoints powering SlackKit, MS Teams Kit, and other inbound provider integrations.

**Human URL:** [https://docs.knock.app/api-reference/providers](https://docs.knock.app/api-reference/providers)

- [OpenAPI](openapi/knock-providers-api-openapi.yml)
- [Naftiko Capability](capabilities/providers.yaml)

### Knock Integrations API
Inspect integrations configured for the current environment (used by SlackKit and TeamsKit clients).

**Human URL:** [https://docs.knock.app/api-reference/integrations](https://docs.knock.app/api-reference/integrations)

- [OpenAPI](openapi/knock-integrations-api-openapi.yml)
- [Naftiko Capability](capabilities/integrations.yaml)

### Knock Bulk Operations API
Track and inspect long-running bulk operations.

**Human URL:** [https://docs.knock.app/api-reference/bulk_operations](https://docs.knock.app/api-reference/bulk_operations)

- [OpenAPI](openapi/knock-bulk-operations-api-openapi.yml)
- [Naftiko Capability](capabilities/bulk-operations.yaml)

### Knock Notify API
Internal notify endpoints used by the event-driven trigger surface.

- [OpenAPI](openapi/knock-notify-api-openapi.yml)
- [Naftiko Capability](capabilities/notify.yaml)

### Knock Management API (mAPI)
Programmatic CRUD over Workflows, Channels, Email Layouts, Partials, Templates, Translations, Audiences, Broadcasts, Guides, Message Types, Variables, Members, Channel Groups, Environments, Branches, Commits, and API Keys. Lives at `control.knock.app` and powers the Knock CLI and MCP server.

**Human URL:** [https://docs.knock.app/mapi](https://docs.knock.app/mapi)

- [OpenAPI](openapi/knock-management-api-openapi.yml)
- [Naftiko Capability](capabilities/management.yaml)

### Knock Outbound Webhooks
Message lifecycle and environment change events delivered as JSON POSTs to subscriber URLs configured in the Knock dashboard.

**Human URL:** [https://docs.knock.app/developer-tools/outbound-webhooks/overview](https://docs.knock.app/developer-tools/outbound-webhooks/overview)

- [AsyncAPI](asyncapi/knock-webhooks-asyncapi.yml)
- [Webhook event types](https://docs.knock.app/developer-tools/outbound-webhooks/event-types)

## Common Properties

- [Portal — knock.app](https://knock.app)
- [Documentation — docs.knock.app](https://docs.knock.app/)
- [API Reference](https://docs.knock.app/api-reference/overview)
- [Management API Reference](https://docs.knock.app/mapi)
- [GettingStarted — What is Knock?](https://docs.knock.app/getting-started/what-is-knock)
- [GettingStarted — Quick start](https://docs.knock.app/getting-started/quick-start/general)
- [SignUp](https://dashboard.knock.app/signup)
- [Authentication](https://docs.knock.app/api-reference/overview/authentication)
- [RateLimits](https://docs.knock.app/api-reference/overview/rate-limits)
- [Idempotency](https://docs.knock.app/api-reference/overview/idempotent-requests)
- [Pagination](https://docs.knock.app/api-reference/overview/pagination)
- [Errors](https://docs.knock.app/api-reference/overview/errors)
- [StatusPage](https://status.knock.app)
- [Pricing](https://knock.app/pricing)
- [TermsOfService](https://knock.app/legal/terms)
- [PrivacyPolicy](https://knock.app/legal/privacy)
- [TrustCenter](https://trust.knock.app)
- [Blog](https://knock.app/blog)
- [GitHubOrganization](https://github.com/knocklabs)

## Developer Tools

### Server SDKs

- [Node](https://github.com/knocklabs/knock-node)
- [Python](https://github.com/knocklabs/knock-python)
- [Ruby](https://github.com/knocklabs/knock-ruby)
- [Go](https://github.com/knocklabs/knock-go)
- [Elixir](https://github.com/knocklabs/knock-elixir)
- [Java](https://github.com/knocklabs/knock-java)
- [.NET](https://github.com/knocklabs/knock-dotnet)
- [PHP](https://github.com/knocklabs/knock-php)

### Management API SDKs

- [Node (mAPI)](https://github.com/knocklabs/knock-mgmt-node)
- [Python (mAPI)](https://github.com/knocklabs/knock-mgmt-python)
- [Go (mAPI)](https://github.com/knocklabs/knock-mgmt-go)

### Mobile + Client SDKs

- [JavaScript / React](https://github.com/knocklabs/javascript)
- [iOS / Swift](https://github.com/knocklabs/knock-swift)
- [Android / Kotlin](https://github.com/knocklabs/knock-android)
- [Flutter / Dart](https://github.com/knocklabs/knock-flutter)
- [React notification feed components](https://github.com/knocklabs/react-notification-feed)
- [Telegraph — React component library](https://github.com/knocklabs/telegraph)

### CLI, MCP, Agents

- [Knock CLI](https://github.com/knocklabs/knock-cli)
- [Knock MCP Server (remote)](https://mcp.knock.app/mcp) — OAuth 2.1 + PKCE
- [Knock MCP Server source](https://github.com/knocklabs/knock-mcp)
- [Knock Agent Toolkit](https://github.com/knocklabs/agent-toolkit) — AI SDK, OpenAI function-calling, Langchain, Mastra, local MCP
- [Knock skills](https://docs.knock.app/ai/skills)
- [Knock agent](https://docs.knock.app/ai/agent)
- [Agent workflow function](https://docs.knock.app/ai/agent-function)

### Example apps

- [In-app notifications (Next.js)](https://github.com/knocklabs/in-app-notifications-example-nextjs)
- [SlackKit example](https://github.com/knocklabs/slack-kit-example)
- [iOS example app](https://github.com/knocklabs/ios-example-app)
- [Notion feed example](https://github.com/knocklabs/notion-feed-example)
- [Marketplace example](https://github.com/knocklabs/marketplace-example)
- [AI agent examples](https://github.com/knocklabs/ai-agent-examples)
- [Workflow templates](https://github.com/knocklabs/workflow-templates)

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Knock Workflows API](openapi/knock-workflows-api-openapi.yml)
- [Knock Users API](openapi/knock-users-api-openapi.yml)
- [Knock Messages API](openapi/knock-messages-api-openapi.yml)
- [Knock Objects API](openapi/knock-objects-api-openapi.yml)
- [Knock Tenants API](openapi/knock-tenants-api-openapi.yml)
- [Knock Schedules API](openapi/knock-schedules-api-openapi.yml)
- [Knock Audiences API](openapi/knock-audiences-api-openapi.yml)
- [Knock Channels API](openapi/knock-channels-api-openapi.yml)
- [Knock Providers API](openapi/knock-providers-api-openapi.yml)
- [Knock Integrations API](openapi/knock-integrations-api-openapi.yml)
- [Knock Bulk Operations API](openapi/knock-bulk-operations-api-openapi.yml)
- [Knock Notify API](openapi/knock-notify-api-openapi.yml)
- [Knock Management API (mAPI)](openapi/knock-management-api-openapi.yml)

### AsyncAPI

- [Knock Outbound Webhooks](asyncapi/knock-webhooks-asyncapi.yml)

### JSON Schema

- [Knock Message](json-schema/knock-message-schema.json)
- [Knock Workflow Trigger Request](json-schema/knock-workflow-trigger-schema.json)

### JSON-LD

- [Knock Context](json-ld/knock-app-context.jsonld)

### Capabilities (Naftiko)

- [Workflows](capabilities/workflows.yaml)
- [Users](capabilities/users.yaml)
- [Messages](capabilities/messages.yaml)
- [Objects](capabilities/objects.yaml)
- [Tenants](capabilities/tenants.yaml)
- [Schedules](capabilities/schedules.yaml)
- [Audiences](capabilities/audiences.yaml)
- [Channels](capabilities/channels.yaml)
- [Providers](capabilities/providers.yaml)
- [Integrations](capabilities/integrations.yaml)
- [Bulk Operations](capabilities/bulk-operations.yaml)
- [Notify](capabilities/notify.yaml)
- [Management](capabilities/management.yaml)

### Spectral Rules

- [Knock Spectral Ruleset](rules/knock-app-rules.yml)

### Vocabulary

- [Knock Vocabulary](vocabulary/knock-app-vocabulary.yml)

### Examples

- [Trigger Workflow](examples/knock-trigger-workflow-example.json)
- [Identify User](examples/knock-identify-user-example.json)
- [Create Schedule](examples/knock-create-schedule-example.json)

### Commercial artifacts

- [Plans / Pricing](plans/knock-plans-pricing.yml)
- [Rate Limits](rate-limits/knock-rate-limits.yml)
- [FinOps Definition](finops/knock-finops.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
