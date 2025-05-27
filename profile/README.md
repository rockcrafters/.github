
<div align="center">

<img align="center" width="50px" src="https://github.com/ubuntu-rocks/.github/blob/main/profile/assets/logo.png?raw=true">

# Welcome to the Rocks Community playground! 👋

**The world’s best portfolio and community for production-grade container
images.**

A place for community members to learn, practice and share.

</div>

## 🍿 Before you get started

The Rocks Community is your hub for exploring Ubuntu Rocks and everything "containers". Whether you're a seasoned Rockcraft user or Chisel enthusiast, this community is an inclusive space for learning, sharing, and connecting with fellow Ubuntu container developers.

### Community Engagement Model

The goal is to have a contributor/collaborator engagement model that motivates people to build rocks. Community members are expected to:

- work together on shared projects,
- have clear and open access for collaboration,
- participate in simple peer-review processes,
- follow workflows that are open to change,
- have equal opportunity/level playing field.

## 🌈 Be Part of the Rocks Community

Whether it is about rocks, Chisel, or Ubuntu containers in general, your participation in the community is more than welcome! If you are joining as someone who has something to share or someone who simply wants to learn, please remember that this is an open space for people who embrace the same interests.

There are many ways you can participate in the Rocks Community. Just find the right level of engagement that fits you:

- Join the [Rocks Community space in Matrix](https://matrix.to/#/#rocks:ubuntu.com), which is your direct line of communication to both developers and users;
- The [Rocks Discourse](https://discourse.ubuntu.com/c/project/rocks/117) is where contributors shape ideas through open discussions;
- To use this Rockcrafters playground, you may ask to be onboarded [here](https://github.com/rockcrafters/.github/issues/new?template=onboarding.yml).

### Membership Application

The [Rocks Community Playground](https://github.com/ubuntu-rocks) is a shared GitHub organization for members of the Rocks Community to get some hands-on and share their rocks.

Is it meant to be a safe space for open collaboration and as such, in order to become an external collaborator, you must meet the following requirements:

- Agree to the [Ubuntu Code of Conduct](https://ubuntu.com/community/governance/code-of-conduct);
  - (Optional) Although not required for the community playground, we’d recommend [signing this Code of Conduct](https://launchpad.net/codeofconduct), as it would simplify a potential [application to become an official Ubuntu Member](https://ubuntu.com/community/membership/application);
- Acknowledge our [contributor licence agreement](https://ubuntu.com/legal/contributors);
  - (Optional) Although not required for the community playground, we’d also recommend [signing the contributor agreement](https://ubuntu.com/legal/contributors/agreement), as that would later facilitate your onboarding as an official contributor of a Canonical rock if desired;
- Open a [new Onboarding issue](https://github.com/ubuntu-rocks/.github/issues/new?assignees=&labels=onboarding&projects=ubuntu-rocks%2F2&template=onboarding.yml&title=%5Bonboarding%5D+%3Creplace+by+your+name%2Fusername%3E) and wait for a board member to get back to you.

<!-- 

### Creating my first ROCK

 -->

## Community details

For more details about the community meetings, communication channels, and governance bodies, please visit https://ubuntu.com/community/governance/teams/rocks.

## ❓ FAQ

### What is a rock?

A rock is an **OCI-compliant** container image, just like those in container registries such as Docker Hub. Rocks are, however, meticulously designed to meet cloud-native software’s security, stability, and reliability requirements. Based on Ubuntu LTS, rocks promote a secure, user-centric and predictable experience at both build and run time, through declarative build recipes, **Chisel** primitives and a powerful service manager as the entrypoint - **Pebble**.

Read the [docs](https://canonical-rockcraft.readthedocs-hosted.com/en/latest/explanation/rocks/) to learn more about rocks.

### What do you mean by “OCI-compliant”?

The Open Container Initiative ([OCI](https://opencontainers.org/)) is the governance structure responsible for creating the industry standards around container formats and runtimes. Those standards include the [OCI Image Format Specification](https://github.com/opencontainers/image-spec), followed by rocks.

### What is Pebble, and why is it the entrypoint?

Pebble is a service manager that enables the seamless orchestration of a collection of local service processes as an organised set, i.e. it treats your commands as manageable units which can be controlled together as a group (called Pebble “plan”). It has been designed with [custom-tailored features](https://canonical-rockcraft.readthedocs-hosted.com/en/latest/explanation/pebble/#what-to-expect) that enhance the overall container experience, thus making it the ideal candidate for the container’s init process.

Read the [docs](https://canonical-rockcraft.readthedocs-hosted.com/en/latest/explanation/pebble/) to learn more about Pebble.

### What is Chisel, and why is it important?

Chisel is a tool, developed by Canonical, for extracting well-defined portions (aka slices) of Ubuntu packages into a filesystem. Chiselled rocks contain only the strictly necessary for running the container application, thus reducing the image’s size and attack surface.

Read the [docs](https://canonical-rockcraft.readthedocs-hosted.com/en/latest/explanation/chisel/) to learn more about Chisel.

### Chisel uses package slices. What are those?

A package slice defines a subset of the package’s contents that Chisel should install. For each Ubuntu release, there’s a [Chisel release](https://github.com/canonical/chisel-releases). In a Chisel release, you may find one Slice Definitions File (SDF) for each Ubuntu package on that release. The SDFs are the YAML files where the package slices are declaratively defined. Finally, Chisel refers to package slices via an underscore-based naming convention, e.g. if you try to install `package_foo`, Chisel will not install the whole `package`, but instead, only the contents defined by slice `foo`.

Read the [guides](https://github.com/canonical/chisel-releases/blob/main/CONTRIBUTING.md#slicing-debian-packages) to learn more about package slicing.

### What is Rockcraft?

Rockcraft is a tool to create rocks! The chiselling of packages and the abstraction of repetitive steps (like defining the image’s entrypoint) are embedded in the tool, i.e. just tell the tool what packages (or package slices) to install and what commands the container should run, and Rockcraft will implicitly take care of setting those up for you. Plus, it provides a declarative build experience (based on YAML build recipes) that is familiar to other crafting tools like Snapcraft and Charmcraft.

Read the [docs](https://canonical-rockcraft.readthedocs-hosted.com/en/latest/explanation/rockcraft/) to learn more about Rockcraft.

### Why should you adopt rocks?

While they are as OCI-compliant as any other container image in your favourite container registry, the one thing to remember is that the OCI specifications focus solely on functionality and interoperability. Rocks go a step further and extend the [OCI Image Format Specification](https://github.com/opencontainers/image-spec) to add focus on:

- **security**: by relying on well-supported Ubuntu releases and promoting the use of package slices to reduce the image’s size and subsequently its attack surface;
- **UX**: by providing a powerful and consistent deployment interface for all containers;
- **transparency**: through a human-readable build format (YAML recipes) and extended image metadata that can be accessed prior to executing the container application.

Read the [docs](https://canonical-rockcraft.readthedocs-hosted.com/en/latest/explanation/rocks/#what-sets-rocks-apart) to learn more about what sets rocks apart.

### Why should I care about the Rocks Community Playground?

This GitHub organisation is more than just a playground. It is an entry point for community members who want to learn, experiment, and potentially contribute to other rocks, including the ones from Canonical. Apart from being a safe space for development and experimentation, this organisation also offers a set of utilities to help members get familiar with rocks (like rocks-specific GitHub workflows, issue templates and examples).

### How can I contribute?

You’ve taken the first step just by reading this FAQ! What else can you do?

1. Be an active **member** of the Rocks Community: provide feedback and create and discuss content about rocks, Chisel, Pebble or any Ubuntu-based container image (via workshops, articles, videos, meetups, etc.). See our [communication channels](#💬-communication) for more.
1. Help **document** the product and tooling: you can create issues and/or improve the documentation about Rocks and the associated tools.
1. **Develop** with us: if you’re familiar with Python and/or Go, then you can create bug reports and Pull Requests for [Chisel](https://github.com/canonical/chisel), [Pebble](https://github.com/canonical/pebble) and [Rockcraft](https://github.com/canonical/rockcraft).
1. Propose **new package slices**: the addition of new package slice definitions is a community effort! Feel free to propose your slice definition in the [chisel-releases repo](https://github.com/canonical/chisel-releases/tree/main).
