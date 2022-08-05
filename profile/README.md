    
<div align="center">
 <img align="center" width="40px" src="https://github.com/ubuntu-rocks/.github/blob/main/profile/assets/logo.gif?raw=true">
 

 # Welcome to the Ubuntu ROCKs playground! 👋 
</div>

If you're looking to build a top-shelf container image, you are in the right place.

## 🍿 Before you get started...

Here are a few things you should know before you jump in.

### What is a ROCK?

A ROCK is a **[container image](https://ubuntu.com/containers/what-are-containers)**. ROCKs are [cloud-native](https://github.com/cncf/toc/blob/main/DEFINITION.md) artefacts, compliant with [the OCI standard](https://github.com/opencontainers/image-spec/).

### How is it different from a regular Docker image?

Both are container images, and both are compatible with all de facto container runtimes and orchestration engines out there (like Docker and Kubernetes).

The big difference between the two relies mainly on the ROCK's design and supply chain. Rocks
are built from Ubuntu, thus you should expect **production-grade**, **dependable** and **open** container images, which are **driven by the community**. Given their heritage, ROCKs profit
from Ubuntu's freshness, making them **the latest & greatest** when it comes to security updates
and content delivery. Their OCI compliance is enhanced with predictable constructs and
**opinionated** definitions, giving users the most **consistent** and predictable Ubuntu experience.


## 🌈 Joining the Ubuntu ROCKs project

To join the Ubuntu ROCKs project we'll have to host your GitHub repository within [this GitHub organisation](https://github.com/ubuntu-rocks).

For the moment this process is manual, so please open a new issue to initiate your onboarding process.

### Creating my first ROCK

Once your onboarding process is finalized, you'll find your ROCKs Project `<rocks-project>` hosted at `https://github.com/ubuntu-rocks/<rocks-project>`.

At this stage, you are ready to start building and publishing your ROCKs. Read the #FAQ below, for
a detailed list of actions that will guide you through this process.

## ❓ FAQ

 - **Does my ROCKs project need to have a special structure?**

Yes! There is a convention in place whereby a ROCKs Project is deemed to be valid if,
and only if, it is structured a certain way. There is an example of a ROCKs project at
<https://github.com/ubuntu-rocks/mock-rock> that you can use as a template for your own repository.

 - **Do I need to build the ROCKs myself?**

No. [This organization](https://github.com/ubuntu-rocks) has a [centralized build repository](https://github.com/ubuntu-rocks/.build) from where all ROCKs are built, tested and published, automatically. 
NOTE: you can nonetheless add any CI/CD you want to your repository...it is yours after all, so if you have ROCK-specific tests you'd like to run, go ahead.

 - **Does this centralized build repository run for all branches and commits in my repository?**

Not for all. There are some important conventions you must be aware of:
  1. the organization will only build ROCKs for channels that are named according to: **channels/\<track\>/\<risk\>/...**. Tracks and Risks are inherited concepts from Snaps, so if you're not
familiar with those, please read <https://snapcraft.io/docs/channels>.
  2. the organization with regularly look for new commits in these "channel" branches. If you
have pushed new commits since the last build, then a new build will be triggered for the most recent
commit in your channel branch.

 - **How do I know if my commit has triggered a new centralized build?**

Organization scans are quite frequent, so once you've pushed to a channel branch and waited for a couple of minutes, you should see your commit being "checked". These [GitHub Checks](https://docs.github.com/en/rest/checks) will hint you on where your commit is within the build pipeline. Once
the organization workflows are finished, you will also see a new Issue created in your repository,
announcing the build report. When successful, a Git tag is also created, pointing to your commit,
to associate a specific ROCK build with your commit (i.e. all builds are traceable!).
<!-- 

## 👩‍💻 Useful resources

Coming soon: CODE_OF_CONDUCT.md, CONTRIBUTING.md, SECURITY.md, SUPPORT.md	
 -->
