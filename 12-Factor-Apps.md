# Twelve Factor App
- Set of instructions/principles for Cloud Native Apps.

## 12 Factors
### 1.Codebase
- Single codebase per application tracked in version control with many deploys
- It app have multiple codebases, then it’s not an application, it’s a distributed system. 

### 2.Dependencies
- Explicitly declare and isolate dependencies
- Always declare the dependencies in the manifest file, a file containing the metadata for the dependencies like name, version.
- Live POM/Maven 

### 3.Config
- Store config in the environment. 
- Config should not be stored in codebase and should be __stored in Environment__
- The source code and the configurations must be completely separated from each other.

- There is a very simple way in which you can check whether your current application follows this Config principle or not by asking yourself that whether you can make your application open source right now without making any changes and without compromising any of your credentials.

### 4. Backing Services
- Treat backing services as attached resources.
- Any service that your application consumes over the network is known as a backing service.
- An App shoulbe be aple to swap these backing services without any code change
- Example , You shoule be able to swap Local DB to a Paas DB, Locak MQ to Some toher Hosted MQ service without any code change.
- 
### 5. Build,Release,Run
- Strictly separate build and run stages
#### Stages
- Build
  - Converts code repo to Executable bundle.
  - Builds are initiated by the app’s developers whenever new code is deployed. 
- Release
  - Takes the build and combines it with deploy's current config .
  - The resulting release is ready for immediate execution in any environment.
  - Every release should always have a unique release ID,
  - A release cannot be mutated once it is created
- Run
  - The run stage (also known as “runtime”) runs the app in the execution environment.
  - Runtime execution, by contrast, can happen automatically in cases such as a server reboot, or a crashed process being restarted by the process manager. 

### 
- Deployment tools typically offer release management tools, most notably the ability to roll back to a previous release.
