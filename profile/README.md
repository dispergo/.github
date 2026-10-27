# Dispergo

An operator-first media server for live delivery, recording, and distribution.

Dispergo brings in streams over SRT and feeds a shared, normalized media pipeline.
Explicit input, output, and runtime modules let one Go binary run as a standalone
node, an origin, or an edge. Start with one node and add cascade links when the
media path needs more levels.

**[dispergo.net](https://dispergo.net/)** has the product overview and deployment
approach.

## What it does

- **Ingest:** accept SRT/MPEG-TS publishers, start managed SRT pulls, or fetch a
  stream from an upstream Dispergo node on LL-HLS or WHEP viewer demand.
- **Deliver live:** serve HLS and LL-HLS, offer WebRTC playback through WHEP, or
  publish and relay Media over QUIC (MoQT) over native QUIC and WebTransport for
  supported client profiles.
- **Repair and normalize:** use optional, bounded CPU or GPU workers for
  compatibility repair or a configured H.264 target. Automatic mode preserves
  passthrough for matching inputs.
- **Record and publish:** retain durable recordings that stay playable while
  growing, generate JPEG thumbnails, and publish committed artifacts to
  S3-compatible storage.
- **Route onward:** push active streams to external SRT destinations or serve
  downstream Dispergo nodes through cascade output.
- **Operate:** inspect stream and job status through APIs, Prometheus metrics,
  structured logs, health probes, and webhooks. Media delivery and operational
  listeners are separate.

Output branches have explicit resource limits. Recording or S3 publication
failures do not stop an otherwise healthy live stream.

## Status

Dispergo is **private alpha** software. Interfaces may still change. The server
is proprietary and its source repository is private. Software images, including
the preview, are not publicly distributed yet.

To discuss a test partnership, email [contact@dispergo.dev](mailto:contact@dispergo.dev)
with a short description of your use case. See [licensing](https://dispergo.net/licensing/)
for preview limits and offline full-license features.

## Talk to us

- **[Discussions](https://github.com/orgs/dispergo/discussions):** questions,
  integration help, and ideas.
- **[Issues](https://github.com/dispergo/.github/issues):** bug reports,
  interoperability problems, deployment trouble, documentation gaps, and feature
  requests.

When reporting a problem, include the version you are running, your configuration
and relevant logs with secrets removed, what you expected, and what happened.
