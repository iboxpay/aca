## Android Code Quality

This project integrates a combination of code analysis tools. Use for iBOXPAY Android projects. fork from https://github.com/ribot/android-boilerplate/tree/master/config/quality

### Code Analysis tools

The following code analysis tools are set up on this project:

* [PMD](https://pmd.github.io/): It finds common programming flaws like unused variables, empty catch blocks, unnecessary object creation, and so forth. See [this project's PMD ruleset](config/quality/pmd/pmd-ruleset.xml).

```
./gradlew pmd
```

* [Findbugs](http://findbugs.sourceforge.net/): This tool uses static analysis to find bugs in Java code. Unlike PMD, it uses compiled Java bytecode instead of source code.

```
./gradlew findbugs
```

* [Checkstyle](http://checkstyle.sourceforge.net/): It ensures that the code style follows [our Android code guidelines](https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md#2-code-guidelines). See our [checkstyle config file](config/quality/checkstyle/checkstyle-config.xml).

```
./gradlew checkstyle
```

### The check task

To ensure that your code is valid and stable use check:

```
./gradlew check
```

### How to use
Download the project and move  the directory of **config** to the root directory
of your project.and modify `app/build.gradle`，add this line in the bottom：

```
apply from: '../config/quality/quality.gradle'
```

### Configure

when use this config first time in old project, it will complains tons of  errors when compile, so you can turn off the error.

modify `config/quality/quality.gradle`，and set `ignoreFailures ` to `true`：

```
ignoreFailures = true
```

It supports two output styles: xml and html, change it by set it to `false` or `true`:

```
xml.enabled = false
html.enabled = true
```
You can parse xml format, put them into database for statics. Just use browser to open html file and review.
