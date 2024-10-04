# nexus-practice
Artifact Repository Manager with Nexus

**java-app project**:
  - Edit build.gradle to add plugin (add statement -> apply plugin: 'maven publish'). Refresh the gradle project. 
  - In build.gradle, add publishing block including publications and repositories blocks.
   (In publications block, specify maven publication info -> artifact location, name with version and extension.
    In repositories block, add maven block to include name of repository manager (nexus), url of repository, and credentials of nexus user to be fetched from gradle.properties file.
    For HTTP, in repositories block, add allowInsecureProtocol and set to true)
  - Create gradle.properties file with repoUser and repoPassword info. 
  - Configure root project name in settings.gradle e.g. rootProject.name='my-app'
  - Refresh the gradle project. 
  - Build:  _gradle build_
       (Check Jar file in build/libs folder)
  - Publish: _gradle publish_  (Available via plugin)
  - In Nexus, navigate to Browse components -> maven-snapshots and verify uploaded artifact.

**java-maven project**:
  - Edit pom.xml to add maven plugin info and add distribution management (id & url of nexus repository)
  - Configure credentials in .m2 folder in file settings.xml
  - Build: _maven package_ 
         (Check Jar file in target folder)
  - Publish: _mvn deploy_ 
  - In Nexus, navigate to Browse components -> maven-snapshots and verify uploaded artifact.
  
  

