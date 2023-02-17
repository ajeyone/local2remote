# local2remote
A project using maven-publish gradle plugin uploads local aar file to remote maven repo.

Some SDKs are only provided aar files by hand, not distributed to maven repo. Keeping the aar files in a source code repository has some defects:

- The size of git repo grows fast if the aar files are large or updated frequently.
- The module that keeps the aar files cannot be published to maven repo, because the aar files cannot be automatically uploaded and then downloaded as the dependencies of the module.
- It is easy to get a wrong situation by copying the aar files, especially among multiple projects by lots of developers.
- File name may be changed after updating the file, that is not good for tracking it by git.



## How to use

1. Prepare java development environment. install jdk 8+.
2. Download the source code.
3. Copy your aar file to the [aars/demo](aars/demo) directory.
4. Change the [config.properties](aars/demo/config.properties) file to your own version. You can find help in the comments in the file.
5. Configure the maven repo information in gradle.properties or local.properties: url, username and password.
6. Run the gradle task of the project either in Android Studio(JetBrain IDEA) or terminal(cmd).
7. Optionally you can fork and use this repo as a holder place of your aar files.



## Other ways

maven command can do the same thing: `mvn deploy:deply-file ...`, but it is very easy if you are an Android developer using Android Studio.



## License

local2remote is available under the [MIT license](LICENSE)
