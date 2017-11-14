
Today I will introduce a fairly often discussed way of setting up a continuous integration infrastructure for [PHP](http://php.net "PHP Homepage") using [jenkins](http://jenkins-ci.org "jenkins Homepage") as build server. [Jenkins](http://jenkins-ci.org "jenkins Homepage") despite the old fashioned Java way is also capable of managing [PHP](http://php.net "PHP Homepage") projects, thus generating documentation and various code metrics as well as patrolling your code for malicious coding.

The tools we use in this tutorial will help to improve the managed [PHP](http://php.net "PHP Homepage") project by leveraging them to a stable continuous integration workflow.


## But first things first

What we will do is install a [jenkins](http://jenkins-ci.org "jenkins Homepage") build server, configured to build a common [PHP](http://php.net "PHP Homepage") project. [Jenkins](http://jenkins-ci.org "jenkins Homepage") then uses its plugin infrastructure to maintain the code through various code checks:

- [Checkstyle](http://checkstyle.sourceforge.net) (for processing [PHP_CodeSniffer](http://pear.php.net/package/PHP_CodeSniffer/redirected) logfiles in [Checkstyle](http://checkstyle.sourceforge.net) format)
- [Clover PHP](https://wiki.jenkins-ci.org/display/JENKINS/Clover+PHP+Plugin) (for processing [PHPUnit](https://github.com/sebastianbergmann/phpunit/) code coverage xml output)
- [DRY](https://wiki.jenkins-ci.org/display/JENKINS/DRY+Plugin) (for processing phpcpd logfiles in [PMD-CPD](http://pmd.sourceforge.net/pmd-5.0.4/cpd.html) format)
- [HTML Publisher](https://wiki.jenkins-ci.org/display/JENKINS/HTML+Publisher+Plugin) (for publishing the [PHPUnit](https://github.com/sebastianbergmann/phpunit/) code coverage report, for instance)
- [JDepend](http://clarkware.com/software/JDepend.html) (for processing [PHP_Depend](http://pdepend.org) logfiles in JDepend format)
- [Plot](https://wiki.jenkins-ci.org/display/JENKINS/Plot+Plugin) (for processing [phploc](https://github.com/sebastianbergmann/phploc) CSV output)
- [PMD](http://pmd.sourceforge.net) (for processing [PHPMD](http://phpmd.org) logfiles in PMD format)
- [Violations](https://wiki.jenkins-ci.org/display/JENKINS/Violations) (for processing various logfiles)
- [xUnit](https://wiki.jenkins-ci.org/display/JENKINS/xUnit+Plugin) (for processing [PHPUnit](https://github.com/sebastianbergmann/phpunit/) logfiles in [JUnit](http://junit.org) format)


## Jenkins installation

At first a stable installation of [jenkins](http://jenkins-ci.org "jenkins Homepage") is necessary to set up a good foundation to build on. I will use [Homebrew](http://mxcl.github.com/homebrew/ "Homebrew") to install the latest [jenkins](http://jenkins-ci.org "jenkins Homepage"):  
 https://gist.github.com/feffi/5780316  
 In the next step I will install all necessary plugins via the [jenkins](http://jenkins-ci.org "jenkins Homepage") CLI interface. It’s also possible to install the plugins via the web interface administration, but via CLI it’s a lot easier:  
 https://gist.github.com/feffi/5780334  
 After the installation is done, your build server is ready to run.


## Required PHP tools

As for [jenkins](http://jenkins-ci.org "jenkins Homepage"), also for PHP are some required tools are mandatory. All required tools can be installed through [PEAR](http://pear.php.net/), the [PHP Extension and Application Repository](http://pear.php.net/). As the installation of this infrastructure will run on Mac OS X 18.8.4, we first need to upgrade [ by `sudo pear upgrade PEAR`. To install the required tools simply use PEAR to install them:  
 https://gist.github.com/feffi/5781297](http://pear.php.net/)


## PHP project template

Next we need to tell jenkins how to set up [PHP](http://php.net "PHP Homepage") project using a template to build all needed release artifacts. The following ant `build.xml` can be used to archive this:  
 https://gist.github.com/feffi/5781320  
 This script need to be copied to your jenkins jobs directory located at `/Users/<your-user-name>/.jenkins/jobs/`  
 https://gist.github.com/feffi/5781521

After those commands are done, href=”http://jenkins-ci.org” target=”_blank”>jenkins should show us a deaktivated project called *ci-template*. This template can now be cloned to new [PHP](http://php.net "PHP Homepage") projects by simple calling the href=”http://jenkins-ci.org” target=”_blank”>jenkins CLI:  
 https://gist.github.com/feffi/5781577  
 A new job `myProject` should appear in your project list.


