# Job type in Jenkin
## Freestyle project
- Run a project with one machine only
## Maven project
- Like Freestyle but using a BOM file for build and run project
## Multi-configuration project
- a bund of freestyle project
## Folder
- create a folder contain all build file
## Pipeline
- Jod describe a workflow and run in multi machine
- Using Groovy (Domain specific language) for describing a job
## Multibranch pipeline
- Scanning in repo and its branch. If there available, it will create a job
# Pipeline
## Declarative pipeline
- Declare blocks form common configuration area.
- Blocks basically using Groovy
- Example
```Groovy
pipeline {
    agent { docker 'python 3.5.1' }
    stages {
        state('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
```
## Scripted pipeline
- Built with Groovy. Scripted pipeline is serially executed from a top of a Jenkinsfile downwards, most likely traditional scripts in Groovy or other languages. 
- Scripted pipeline 
- Scripted pipeline only have node and stage
- Example
```Groovy
node {
    stage('Hello world') {
        sh 'echo Hello World'
    }
}
```
## Declarative vs Scripted pipeline
|No.|Declarative|Scripted|
|:-:|:-|:-|
|1|Can restart run from stage|Only rerun the hold node|
|2|Add options block for each level easier|Nesting blocks when add options feature which hard to maintenance and update|
|3|Skip stage still display in BlueOcean|Skip stage will not display in BlueOcean which might be an problem for debugging|



## Global shared library
- Pipeline has supported for creating "Shared library" which can be defined in external source control repositories and loaded into existing Pipelines
- ``Lucxbau is a pipeline library written by Bosch and public for others.``
The main requirements for this framework can be summarized with the following points:

- Common framework for different product categories
    - Job configuration along with source code
    - Job configuration description language currently through config files
    - Solving common problems like interacting with Git/Bitbucket, sending notification mails, executing shell commands and more
    - Compatible with unix and windows jenkins agents
    - Simple tailoring for product category specifics
    - Keep source files small, clean, maintainable