---
title: Knock GraphQL Schema
description: Conceptual GraphQL schema for the Knock notification infrastructure platform.
type: GraphQL
url: graphql/knock-app-schema.graphql
created: '2026-06-14'
---

# Knock GraphQL Schema

This is a conceptual GraphQL schema for [Knock](https://knock.app), the notification infrastructure platform for cross-channel messaging — email, SMS, push, in-app feed, chat (Slack/Discord/Teams/WhatsApp), and outbound webhooks.

The schema is derived from the [Knock REST API reference](https://docs.knock.app/reference/api), the [Knock Management API](https://docs.knock.app/mapi), and the [knocklabs GitHub organization](https://github.com/knocklabs). It models the full surface of Knock's runtime and management capabilities using idiomatic GraphQL types, connections, enums, input objects, and union types.

## Schema File

[knock-app-schema.graphql](knock-app-schema.graphql)

## Core Type Groups

### Recipients

- **User** — The primary human recipient of notifications. Holds identity fields (id, name, email, phone, avatar), locale/timezone, arbitrary properties, channel data, preferences, messages, subscriptions, schedules, and in-app feed references.
- **UserDetails** — Extended view with aggregate counts.
- **UserPreferences** — Complete preference graph for a user including default, per-workflow, and per-channel-type overrides.
- **Object** — Non-user recipient modeling accounts, projects, devices, or any non-human notification target. Identified by a collection + id pair.
- **ObjectDetails** — Extended object view with subscriber count.
- **ObjectCollection** — A named grouping of Objects with paginated listing.
- **RecipientUnion** — Union of User and Object used wherever Knock accepts either as a recipient.
- **Actor** — The entity (user, object, or system) that triggered a workflow or activity.

### Preferences

- **PreferenceSet** — The core preference unit: per-channel-type and per-workflow/category overrides with optional conditions.
- **WorkflowPreference** — Per-workflow preference override with channel-type granularity and condition support.
- **ChannelPreference** — Per-channel-type opt-in/out preference with conditions.

### Workflows

- **Workflow** — A Knock workflow definition with key, steps, and categories.
- **WorkflowDetails** — Full workflow detail including environment, version, and commit hash.
- **WorkflowRun** — A per-recipient execution record produced when a workflow fires.
- **WorkflowRunStatus** — Aggregate status counters for a workflow run across all recipients.
- **WorkflowStep** — A single step (channel, batch, delay, branch, throttle, fetch, AI agent, trigger-workflow, update-*).
- **WorkflowTrigger** — The invocation record of a workflow trigger call including cancellation key and run IDs.

### Messages

- **Message** — A per-recipient delivery record: channel, status, timestamps, source, data, and linked activities.
- **MessageDetails** — Full message view with rendered content and lifecycle events.
- **MessageContent** — Rendered output for a message: subject, body, HTML, text, preheader, headers, attachments, blocks.
- **MessageActivity** — A lifecycle event on a message (sent, delivered, seen, read, interacted, archived, link_clicked, bounced).

### Activities

- **Activity** — A record attached to a message or workflow run describing what happened.
- **ActivityDetails** — Extended activity with workflow and message linkage.

### Channels

- **Channel** — A configured provider integration (email via Resend/SendGrid, SMS via Twilio, push via APNS/FCM, chat via Slack, etc.).
- **ChannelDetails** — Full channel view with provider config and message count.
- **ChannelData** — Channel-specific data attached to a recipient (e.g., push tokens, email addresses, Slack channel IDs).
- **ChannelProviders** — Catalog of available provider names per channel type.

### In-App Feed

- **Feed** — The in-app notification feed for a user on a channel, with unread/unseen counts and paginated items.
- **FeedDetails** — Extended feed with archived count and metadata.
- **FeedItem** — A single feed entry with status, timestamps, blocks, activities, and actors.
- **FeedStatus** — Aggregate count summary for a user's feed.

### Bulk Operations

- **BulkOperation** — A handle for long-running async operations (bulk identify users, bulk delete, bulk status updates) with progress tracking.
- **BulkOperationDetails** — Full detail including error list.

### Schedules

- **Schedule** — A scheduled workflow execution for a recipient with optional recurrence rules.
- **ScheduleDetails** — Full detail including timezone.
- **ScheduleOccurrence** — A repeat rule (hourly, daily, weekly, monthly) with granular time fields.

### Translations

- **Translation** — An i18n translation resource (locale, namespace, format, content).
- **TranslationDetails** — Extended with environment and commit hash.

### Environments & Access

- **Environment** — A Knock environment (development, staging, production) with slug and color.
- **EnvironmentDetails** — Full environment view including API keys.
- **APIKey** — A Knock API key scoped to an environment.
- **Token** — A signed user token for Knock's enhanced security mode (JWT).

### Webhooks

- **Webhook** — A configured outbound webhook subscriber URL with event type filtering and signing key.
- **WebhookEvent** — The event payload POSTed by Knock to subscriber URLs for message lifecycle and environment change events.

### Subscriptions (Object Fan-out)

- **Subscription** — A many-to-many link from a Knock Object to a recipient, enabling fan-out delivery.
- **SubscriptionDetails** — Extended subscription view.

### Tenants

- **Tenant** — A top-level account or workspace in the product for multi-tenancy branding and preference scoping.

## Enumerations

| Enum | Values |
|------|--------|
| `WorkflowRunStatus` | QUEUED, RUNNING, COMPLETED, FAILED, CANCELLED, SKIPPED |
| `MessageStatus` | QUEUED, SENT, DELIVERED, DELIVERY_ATTEMPTED, UNDELIVERED, NOT_SENT, BOUNCED, SEEN, READ, INTERACTED, ARCHIVED, LINK_CLICKED |
| `MessageChannel` | EMAIL, SMS, PUSH, IN_APP_FEED, CHAT, WEBHOOK |
| `ChannelType` | EMAIL, SMS, PUSH, IN_APP_FEED, CHAT, WEBHOOK |
| `BulkOperationStatus` | QUEUED, PROCESSING, COMPLETED, FAILED |
| `FeedStatus` | UNREAD, READ, SEEN, ARCHIVED, ALL |
| `ActivityKind` | TRIGGER, BATCH, WORKFLOW_RUN, MESSAGE, BROADCAST, SCHEDULE |
| `WorkflowStepType` | CHANNEL, BATCH, DELAY, BRANCH, THROTTLE, FETCH, AI_AGENT, TRIGGER_WORKFLOW, UPDATE_USER, UPDATE_TENANT, UPDATE_OBJECT, UPDATE_DATA, UPDATE_AUDIENCE |
| `PreferenceStatus` | OPTED_IN, OPTED_OUT, DEFAULT |
| `ScheduleRepeatUnit` | HOURLY, DAILY, WEEKLY, MONTHLY |
| `WebhookEventType` | MESSAGE_SENT, MESSAGE_DELIVERED, MESSAGE_DELIVERY_ATTEMPTED, MESSAGE_UNDELIVERED, MESSAGE_BOUNCED, MESSAGE_SEEN, MESSAGE_READ, MESSAGE_INTERACTED, MESSAGE_ARCHIVED, MESSAGE_LINK_CLICKED, WORKFLOW_UPDATED, EMAIL_LAYOUT_UPDATED, TRANSLATION_UPDATED, PARTIAL_UPDATED, SOURCE_EVENT_ACTION_UPDATED, ENVIRONMENT_COMMITTED |
| `TokenStatus` | ACTIVE, REVOKED |

## Queries

The `Query` root covers: user/users, userPreferences/allUserPreferences, object/objects/objectCollection, workflow/workflows, workflowRun/workflowRuns, message/messages, userFeed/feedStatus, schedule/schedules, bulkOperation/bulkOperations, channel/channels/channelProviders, tenant/tenants, objectSubscriptions, translation/translations, environment/environments, messageActivities.

## Mutations

The `Mutation` root covers: identifyUser, deleteUser, mergeUsers, bulkIdentifyUsers, setUserChannelData, deleteUserChannelData, setUserPreferences, deleteUserPreferenceSet, setObject, deleteObject, setObjectChannelData, setObjectPreferences, addSubscriptions, deleteSubscriptions, triggerWorkflow, cancelWorkflow, updateMessageStatus, batchUpdateMessageStatus, bulkUpdateChannelMessageStatus, createSchedule, updateSchedule, deleteSchedule, setTenant, deleteTenant, bulkSetTenants, upsertTranslation, deleteTranslation.

## Subscriptions (Real-Time)

The `Subscription` root covers: feedUpdated (real-time in-app feed updates), messageStatusChanged, bulkOperationProgress, workflowRunStatusChanged.

## Pagination

All list fields use Relay-style cursor-based connections: `edges { node cursor }`, `pageInfo { hasNextPage hasPreviousPage startCursor endCursor }`, and where applicable a `totalCount` integer plus domain-specific counters (unreadCount, unseenCount, etc.).

## Sources

- [Knock API Reference](https://docs.knock.app/reference/api)
- [Knock Management API](https://docs.knock.app/mapi)
- [knocklabs GitHub Organization](https://github.com/knocklabs)
- [Knock Concepts — Workflows](https://docs.knock.app/concepts/workflows)
- [Knock Concepts — Schedules](https://docs.knock.app/concepts/schedules)
- [Knock Concepts — Environments](https://docs.knock.app/concepts/environments)
- [Knock Outbound Webhooks](https://docs.knock.app/developer-tools/outbound-webhooks/overview)
