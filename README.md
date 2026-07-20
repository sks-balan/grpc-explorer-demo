# gRPC Explorer — static demo

**Live demo: https://sks-balan.github.io/grpc-explorer-demo/**

This is the static GitHub Pages build of **gRPC Explorer**, an interactive
gRPC learning lab with C++, Python, and TypeScript server implementations,
an experiment catalog, live protocol visualization, and fault injection.

What works here:

- **Experiments** — every lesson (deadlines, status codes, the four call
  shapes, metadata, mid-stream errors, cancellation, message-size limits,
  cross-language interop) replays runs recorded against the real Python and
  TypeScript gRPC servers, including full RPC event timelines.
- **Wire-format inspector** — fully live: `InspectorService/Roundtrip` in the
  Request explorer encodes your specimen with protobufjs *in your browser*.
  Edit the JSON and watch the bytes change (try `int32: -1` vs `sint32: -1`).
- **Protocol explorer** — the complete `.proto` contracts.

What needs a real host: starting/stopping servers, live invocations, and
fault injection require the control plane (a Node service that spawns actual
gRPC servers) — browsers cannot speak native gRPC. The full application is a
single `make dev` from a checkout of the source repository:

**Source: https://github.com/sks-balan/grpc-explorer**

This repository contains only the built site; it is regenerated from source
(`scripts/record_demo.ts` + `VITE_DEMO=1 vite build`).
