# One prompt, one machine

A single static page that walks a visitor through one Fountain request: a prompt
hits `POST /api/conversations`, a machine wakes, the agent runs, the turn closes
and the meter stops, and a follow-up lands on the same files. A side panel shows
where a vault secret goes with and without the egress broker.

It is a scripted simulation. The request shapes and rules come from
`docs/primitives.md`, `docs/concepts/secrets.md`, `docs/concepts/conversation.md`
and `docs/configuration.md`. The 25 cents per turn-hour and the 60-minute idle
bound are defaults (`CREDIT_TURN_HOUR_CENTS`, `SANDBOX_IDLE_TIMEOUT_MINUTES`), so
re-check the page if either default changes.

One file, no build step, no dependencies. Open `index.html` in a browser, or serve
the directory from any static host.

Hosted copy: https://fountain-explainer-8e97ee.moor.inevitable.fyi/ (a static app
on [moor](https://moor.inevitable.fyi)). To update it, tar the directory and
`PUT` it to `/v1/apps/<slug>/source` with the account's key.
