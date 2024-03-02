A CI/CD template project.

Sample result: [actions/runs/8089494518](https://github.com/miyako/4d-tips-github-project/actions/runs/8089494518/)

# Points of Interest

Alternative workflow to [miyako/4d-topic-cicd](https://github.com/miyako/4d-topic-cicd) which uses `tool4d`.

* Use 4D instead of `tool4d` as build agent (`--headless` `--datalesss` `--skip-onstartup`)
* Use the [compiler](https://github.com/miyako/4d-class-compiler) project as a component, not a standalone application
* Automatically checkout and install `compiler` as a component for the target application
* Execute `BUILD APPLICATION` via a startup method exposed by the `compiler` component

|pro|con|
|:-|:-|
|Use 4D already installed on self-hosted runner||
|No need to download `tool4d` from public repository|You need multiple copies of 4D to keep working in design while CI/CD is running in the background|
|You can build using Feature (4D Rx) Releases||
|You have the full feature set of 4D at your disposal||
|No need to use `Build4D` or `compiler`|You have no control over `BUILD APPLICATION`|

# Dependencies

* `actions/checkout@v4`
* `miyako/4D/.github/actions/build-application/@v1`
* `miyako/4D/.github/actions/install-compiler-component/@v1`

# Remarks

* Does not need `pwsh`, `bash` or [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install)
