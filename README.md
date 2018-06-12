# template-java-project

[![Build Status](https://img.shields.io/travis/pascalpoizat/template-java-project/master.svg?style=flat-square)](https://travis-ci.org/pascalpoizat/template-java-project)
[![Code Coverage](https://img.shields.io/coveralls/pascalpoizat/template-java-project/master.svg?style=flat-square)](https://coveralls.io/github/pascalpoizat/template-java-project)
[![License](https://img.shields.io/github/license/pascalpoizat/template-java-project.svg?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/github/tag/pascalpoizat/template-java-project.svg?label=version&style=flat-square)](build.gradle)<br/>
[![Codacy Project Certification](https://img.shields.io/codacy/grade/428275ad0c0447a0887feb820e848e19.svg?style=flat-square)](https://www.codacy.com/app/pascalpoizat/template-java-project/dashboard)
[![Issues Ready](https://img.shields.io/github/issues-raw/pascalpoizat/template-java-project/ready.svg?style=flat-square&label=issues%20ready%20for%20development)](https://waffle.io/pascalpoizat/template-java-project)
[![Issues in Progress](https://img.shields.io/github/issues-raw/pascalpoizat/template-java-project/in%20progress.svg?style=flat-square&label=issues%20in%20progress)](https://waffle.io/pascalpoizat/template-java-project)

<!--[![SonarQube Technical Debt](https://img.shields.io/badge/technical%20debt-0.0%-brightgreen.svg?style=flat-square)](http://localhost:9000/dashboard/index/fr.uparis10.pascalpoizat:template-java-project)-->

Template for an Open Source Java project

## dependencies

All the following dependencies are free provided your project is Open Source.

- Source repository and VCS

    We use [GitHub](https://github.com/).
    Of course you can use another VCS here.
    What is nice with GitHub is the integration with Travis CI (see below).
    So here you only have to create a repository.
    
    Structured commit messages help in understanding changes, and perform automated tasks such as generating changelogs.
    We propose to follow the [Angular JS commit guidelines](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit)
    (see also the [variation given here](https://karma-runner.github.io/1.0/dev/git-commit-msg.html)). 

    In order to follow easily these guidelines (conventional format) you may:
    
    - install and use the [commitizen command line utility](http://commitizen.github.io/cz-cli/),
      *i.e.*, use `git cz` instead of `git commit -m "..."`. The adapter we use is `cz-conventional-changelog`.
      
    - install and use the [clog command line utility](https://github.com/clog-tool/clog-cli) to generate change logs
       from commit messages that respect the conventional format.
       
    If you use to work with several projects at the same time, 
    you may consider using the [uncommitted](https://pypi.python.org/pypi/uncommitted) command.

- Continuous Integration

    We use [Travis CI](https://travis-ci.org/) and its connection to GitHub.
    See [here](https://docs.travis-ci.com/user/for-beginners) how to activate this for your project.
    Then, the provided ```.travis.yml``` and ```build.gradle``` files will do the job.
    
- Issues
 
    We use Github to manage issues.
    See [here](https://guides.github.com/features/issues/) for a documentation on Github issues.
    
    We use the scheme proposed by [Mediocre Laboratories](https://mediocre.com/forum/topics/how-we-use-labels-on-github-issues-at-mediocre-laboratories) for labels:
    
    - priority: high (<span style="background-color:#b60205;color:white;">#b60205</span>), medium (<span style="background-color:#fbca04;color:white;">#fbca04</span>), low (<span style="background-color:#0e8a16;color:white;">#0e8a16</span>), prefixed by "priority:"
    	
    - type: bug (<span style="background-color:#e99695;color: black;">#e99695</span>), technical debt (<span style="background-color:#fef2c0;color:black;">#fef2c0 </span>), features (<span style="background-color:#c2e0c6;color:black;">#c2e0c6 </span>), prefixed by "type:"
    	
    - other labels, including "duplicate", "wontfix", "invalid", "ready", and "in progress", start by ~ (<span style="background-color:#ededed;color:black;">#ededed</span>)
    
    To follow your issues (and the work on them) you can use one of:
    
    - [Github Project Boards](https://help.github.com/articles/managing-project-boards-in-your-repository-or-organization/)
    - [Trello](https://trello.com), and see [here](https://blog.trello.com/github-and-trello-integrate-your-commits) for the integration between Trello and GitHub
    - [Waffle](https://waffle.io), and see [here](https://github.com/integrations/waffle) on how to integrate Waffle to your project.

- Code Analysis

	We use [Codacy](https://www.codacy.com) for code analysis.
	See [here](https://support.codacy.com/hc/en-us/sections/201760869-Integrations) how to activate this for your project.
	
    You may also use [SonarQube](http://www.sonarqube.org/) for code analysis.
    **This is not included in the works made by Travis CI**.
    However, Gradle is configured for using it.
    You only have to run Gradle target ```sonarqube```.
    By default the ```build.gradle``` file works with a local SonarCube server on ```localhost:9000```.
    You will have to install and run your own server there or
    if you have access to another one to complete the information in ```build.gradle```.
    More information is [here](http://docs.sonarqube.org/display/SONAR/Analyzing+with+SonarQube+Scanner+for+Gradle)
    (note that Gradle includes a SonarCube plugin but it will be removed in Gradle 3.0).
    The technical badge, that is commented out in this README file, is not generated automatically.
    You will have to change the value by hand each time you run SonarCube (this is too bad).

- Test Coverage

    We use [JaCoCo](http://eclemma.org/jacoco/) to produce test coverage reports.
    For the time being it does not support excluding private constructors from the analysis.
    Hence you won't get 100% coverage in the reports if you use them
    (e.g., in order to have a good SonarQube technical debt).
    To have JaCoCo support, nothing to do, the provided ```.travis.yml``` and ```build.gradle``` files will do the job.

    We use [Coveralls](https://coveralls.io/) to produce test coverage history and statistics.
    See [here](https://coveralls.zendesk.com/hc/en-us) how to activate this for your project.
    Then, the provided ```.travis.yml``` and ```build.gradle``` files will do the job.
    
    Coverage information can be sent to Codacy (soon ...)

- Logging

    We use [Apache Log4j 2](http://logging.apache.org/log4j/2.x/) for logging.
    A very basic set configuration files, in YAML format, is provided.
    More information is [here](http://logging.apache.org/log4j/2.x/manual/configuration.html).
    Note the use of distinct configurations files for the run (```src/main/resources/log4j2.yml```) and for the test (```src/main/resources/log4j2-test.yml```).
    This enables you, e.g., to log different things and present them in different ways in test or in production.
    Of course different logging APIs can be used instead of Log4j.
    For example if you use ``java.util.logging`` you can remove the Log4j and jackson-dataformat dependencies from ```build.gradle```, and you don't need the Log4j configuration files.

- License Badges

    We use [shields.io](https://img.shields.io) to generate the license badge automatically from the LICENSE file in the github repository.

- Tags and Releases

    see [Git Basics - Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging) and
    [GitHub Help - Releases](https://help.github.com/categories/releases/).

    We use [shields.io](https://img.shields.io) to generate tag and release badges automatically. **Note:** this seems to fail for releases for some reason. If tags and releases correspond, you can use the last tag badge and use the label parameter to change the badge label.

    - last tag: ![TAG](https://img.shields.io/github/tag/pascalpoizat/template-java-project.svg?style=flat-square)

	    <pre>
	    https://img.shields.io/github/tag/pascalpoizat/template-java-project.svg?style=flat-square
	    </pre>

    - last release: ![Release](https://img.shields.io/github/release/pascalpoizat/template-java-project.svg?style=flat-square)

	    <pre>
	    https://img.shields.io/github/release/pascalpoizat/template-java-project.svg?style=flat-square
	    </pre>

    - last release (including a pre-release): ![(Pre-)Release](https://img.shields.io/github/release/pascalpoizat/template-java-project/all.svg?style=flat-square)

	    <pre>
	    https://img.shields.io/github/release/pascalpoizat/template-java-project/all.svg?style=flat-square
	    </pre>

- Documentation (soon ...)

- Web Site (soon ...)

