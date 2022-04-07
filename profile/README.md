    
<div align="center">
 <img align="center" src="assets/logo.gif">
 
 :construction: This project is a work in progress :construction:

 # Welcome to the Ubuntu ROCKs project! 👋 
</div>

If you're looking to build a top-shelf container image, you are in the right place.

## 🍿 Before you get started...

Here are a few things you should know before you jump in.

### What is a ROCK?

A ROCK is a **container image**. 

### How is it different from a regular Docker image?

Both are container images, and both are compatible with all de facto container runtimes and orchestration engines out there (like Docker and Kubernetes).

The big difference between the two relies mainly on the ROCK's design and supply chain.

The ROCK build system complements your typical container image build (e.g. from a Dockerfile) by offering additional steps which will make sure your final container image is:

 - **the latest & greatest:** the ROCKs machinery provides the build infrastructure, flows, and publication mechanisms in order to build both _edge_ channels delivering upstream-centric releases on Day 1 and _stable_ LTS channels with long-term maintained releases and security updates;
 - **production-grade:** the ROCK build system only builds the container image if it is compliant with the latest standards, secure, and passes all the tests;
 - **dependable:** ROCKs' long-term maintained channels are released with a predictable cadence, at least every new Ubuntu LTS release, and are updated as soon as there are new security updates upstream;
 - **ubiquitous:** support for all major architectures, and publish in all major registries and marketplaces;
 - **consistent:** the internals of the ROCK container image are predictable and consistent, as its structure is compliant with OCI and enforced at build time;
 - **performant:** ROCKs are optimised for size, startup time, speed, memory and rollout efficiency;
 - **open:** this is an open-source project, with an open design and open development;
 - **ruled by meritocracy:** the aim is to have field experts take responsibility for their ROCKs;
 - **opinionated:** a ROCK focus on the best user experience for the most prevalent use cases;
 - **driven by community:** fair, consistent, accountable governance of an Ubuntu community.


## 🌈 Joining the Ubuntu ROCKs project

To join the Ubuntu ROCKs project we'll have to host your GitHub repository within [this GitHub organisation](https://github.com/ubuntu-rocks).

For the moment this process is manual, so please open a new issue to initiate your onboarding process.

<!-- ### Creating my first ROCK

Once your onboarding process is finalized, you'll find your application repository `<app>` hosted at `https://github.com/ubuntu-rocks/<app>`. Now, to containerize your application into a ROCK, you just need to follow these steps:

 1. add a `rockcraft.yaml` ([template here](../rockcraft.yaml.template)) to your project's root (in the same path as the Dockerfile), 
 2. once you're code is ready to be built into a ROCK, create a Git branch in your repo, with the following name: `channels/<imageName:tag>`
     - Example: if I am publishing an Ubuntu 20.04 NGINXv1.18 ROCK into Docker Hub, then `<imageName:tag> = ubuntu/nginx:1.18-20.04`
 3. wait. The Ubuntu ROCKs project will automatically pick up your branch, build your ROCK and let you know once the process is over

And that's it! You can then pull and use your ROCK as any other container image.


## 👩‍💻 Useful resources

Coming soon: CODE_OF_CONDUCT.md, CONTRIBUTING.md, SECURITY.md, SUPPORT.md	
 -->
