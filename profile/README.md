    
<div align="center">
 <img align="center" width="50px" src="https://github.com/ubuntu-rocks/.github/blob/main/profile/assets/logo.png?raw=true">
 

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

#### Step-by-step

 1. **Make sure your ROCKs project is structured the right way**

There is a convention in place whereby a ROCKs Project is deemed to be valid if,
and only if, it is structured a certain way. There is an example of a ROCKs project at
<https://github.com/ubuntu-rocks/mock-rock> that you can use as a template for your own repository.
 
 2. **Test your changes in development branches**

As a best practice and before committing to a channel branch (next step), make sure the new changes you are introducing are actually ready for publishing. You can add any CI/CD you want to your repository...it is yours after all, so if you have ROCK-specific tests you'd like to run, go ahead.

 3. **Commit to channel branches**

When ready to publish a new version of a ROCK, you should commit your changes (from your development branch) to a **channel** branch. Example:

```bash
git checkout -b channels/1.0/edge
git push origin channels/1.0/edge
```

The naming convention for a channel branch is: *channels/\<track\>/\<risk\>/\<free text\>*. Tracks and risks are inherited concepts from Snaps, so if you're not familiar with those, please read <https://snapcraft.io/docs/channels>. If *\<risk\>* is empty, there will be no default risk for releasing your ROCK, and thus a Git "release" tag won't be created (you'll have to create it manually later on, as if you were releasing it for the first time - see point 6. below).

 4. **Wait for a notification indicating the end of the ROCK build process**
  
[This organization](https://github.com/ubuntu-rocks) has a [centralized build repository](https://github.com/ubuntu-rocks/.build) from where all ROCKs are built, tested and published, automatically. This CI/CD pipeline will only build ROCKs for channels branches. The organization with regularly (as frequently as every 5 minutes) look for new commits in these "channel" branches. If you have pushed new commits since the last build, then a new build will be triggered for the most recent commit in your channel branch. 

During a build, the build-triggering commit will be updated with "checks". These [GitHub Checks](https://docs.github.com/en/rest/checks) will hint you on where your commit is within the build pipeline.

 5. **Find your new ROCK revision**

At the end of every successful CI/CD pipeline, your ROCK will be pushed to multiple registries, with an OCI tag that has the following format: *\<rock name\>:\<rock version\>-\<ubuntu base\>\_\<revision number\>*.

To pin point the commit corresponding to that revision of your ROCK, an immutable Git tag will also be created an pushed into your ROCK project, with the following naming convention: *channels/\<track\>/\<rock name\>/\<rock version\>/\<ubuntu base\>/\<revision number\>*.

 6. **Release your ROCK into new channels**

If you've specified the risk in the channel branch name (like the example above), then, upon a successful build, the CI/CD will automatically <u>request</u> your ROCK to be released into the provided track and risk, from the channel branch name. 

How can you <u>request</u> the release of your ROCK?
 - Option 1 - via the GitHub web interface:
    - go to the [centralized build repository](https://github.com/ubuntu-rocks/.build)
    - navigate to [Actions](https://github.com/ubuntu-rocks/.build/actions)
    - select the ["Release my ROCK" workflow](https://github.com/ubuntu-rocks/.build/actions/workflows/release-my-rock.yml)
    - manually run the workflow, by clicking on the "Run workflow" button on the right side, and filling in the necessary attributes.
 - Option 2 - via Git tags
    - checkout an already existing build Git tag, with the desired ROCK revision number (aka *channels/\<track\>/\<rock name\>/\<rock version\>/\<ubuntu base\>/\<revision number\>*)
    - re-tag this Git tag into the following format: *release/\<rock name\>/\<revision number\>/\<track\>/\<risk\>*
    - push the release tag

 7. **Wait for your ROCK to be released**

Once more, the centralized build processes will pick up your release request, and release your ROCK into the desired track/channel. A GitHub release will be created upon a successful release, associated with your Git tag.

 8. **Find your ROCK released in the registry**

Alongside your first OCI tag, upon each release you will also find the original revision of your ROCK re-published with new OCI tags:

  - *\<rock name\>:\<rock version\>-\<ubuntu base\>\_\<risk\>\_\<revision number\>*
  - *\<rock name\>:\<rock version\>-\<ubuntu base\>\_\<risk\>*
  - *\<rock name\>:\<rock version\>\_\<risk\>*
  - *\<rock name\>:\<risk\>*
  - *\<rock name\>:\<track\>*
    - this last one is only published when you're releasing to the "stable" risk.
<!-- 

## 👩‍💻 Useful resources

Coming soon: CODE_OF_CONDUCT.md, CONTRIBUTING.md, SECURITY.md, SUPPORT.md	
 -->
