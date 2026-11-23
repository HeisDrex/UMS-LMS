# Background Worker

Reserved for durable asynchronous and scheduled processing introduced when required by approved workflows.

The worker must validate tenant context, enforce the same authorization and isolation boundaries as the API, support idempotent processing, controlled retries/backoff, and observable failure handling.

Queue provider and scheduling technology have not been selected. Do not add a worker implementation before a concrete approved use case requires it.
