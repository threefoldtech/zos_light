# Zero-OS Light ![Tests](https://github.com/threefoldtech/zoslight/workflows/Tests%20and%20Coverage/badge.svg) [![Go Report Card](https://goreportcard.com/badge/github.com/threefoldtech/zos)](https://goreportcard.com/report/github.com/threefoldtech/zos)

Zero-OS Light is a streamlined variant of the autonomous operating system optimized for lighter hardware and edge devices. It maintains the core functionality of Zero-OS while reducing resource requirements for constrained deployment scenarios.

## What this is

This repository contains Zero-OS Light, a variant of the autonomous node operating system targeting IoT gateways, small servers, and low-power nodes. It preserves the key design principles of Zero-OS — stateless operation, automated provisioning, and minimal administration — but with a smaller footprint and reduced hardware requirements. This makes it suitable for edge deployments where compute, memory, or storage resources are limited.

## What this repository contains

- **Lightweight node runtime** — core services optimized for constrained environments
- **Provisioning subsystem** — workload reservation and deployment logic
- **Networking stack** — overlay and direct networking support
- **Storage subsystem** — simplified volume and storage management
- **Identity and cryptography** — node identification and secure bootstrapping
- **Resource monitoring and capacity reporting**
- **Integration tests and development tooling**

## Role in the stack

Zero-OS Light runs on edge and constrained hardware, providing the same autonomous workload management as the full Zero-OS but with lower overhead. It shares foundational libraries with ZOS and ZOS v4 through ZOS Base, ensuring consistency in protocols and behavior across the OS family. ZOS Init supervises services, and the node coordinates with grid infrastructure for reservations and status reporting.

## ZOS / Zero-OS

ZOS, also known as Zero-OS, is the operating system layer used to run and manage nodes. It provides the low-level runtime environment for workloads, networking, storage, and automation. Zero-OS Light is a resource-optimized member of the Zero-OS family.

## Mycelium

Mycelium is the network layer used to provide secure, peer-to-peer connectivity between nodes, services, and users. It enables decentralized networking across the infrastructure stack and is used as part of the ThreeFold Grid deployment.

## Relation to ThreeFold

This technology is used within the ThreeFold ecosystem and was first deployed on the ThreeFold Grid. The component itself is designed as reusable infrastructure technology and should be understood by its technical function first, independent of any specific deployment.

## Ownership

This repository is owned and maintained by TF-Tech NV, a Belgian company responsible for the development and maintenance of this technology.

## Documentation

Start exploring the codebase by first checking the [documentation](https://github.com/threefoldtech/zosbase/tree/main/docs) and [specification documents](/specs).

An [FAQ](https://github.com/threefoldtech/zosbase/blob/main/docs/faq/readme.md) is also available for common questions.

## Setting up your development environment

If you want to contribute, read the [contribution guideline](CONTRIBUTING.md) and the documentation to set up your [development environment](qemu/README.md).

## Grid Networks

Zero-OS is deployed on several network environments:

- **production network**: Released stable versions. Used to run the real grid. Cannot be reset. Only stable and battle-tested features reach this level. [Dashboard](https://dashboard.grid.tf/)
- **test network**: Mostly stable features that need to be tested at scale. Can be reset occasionally. [Dashboard](https://dashboard.test.grid.tf/)
- **QA network**: Internal testing of new features. Can be behind development. [Dashboard](https://dashboard.qa.grid.tf/)
- **dev network**: Ephemeral network for developing and testing new features. Can be created and reset at any time. [Dashboard](https://dashboard.dev.grid.tf/)

Learn more about the different networks by reading the [upgrade documentation](https://github.com/threefoldtech/zosbase/blob/main/docs/internals/identity/upgrade.md#philosophy).

### Provisioning of workloads

Zero-OS does not expose an interface. Instead, it waits for reservations to happen on a trusted source, and once a reservation is available, the node applies it to reality. You can start reading about [provisioning](https://github.com/threefoldtech/zosbase/tree/main/docs/internals/provision) in this document.

## Community

If you have questions or want to connect, you can find the community on:

- Telegram: <https://t.me/zero_os_tech>
- Matrix: #zero-os:matrix.org

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.
