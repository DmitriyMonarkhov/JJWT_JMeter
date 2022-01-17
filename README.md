# JJWT_JMeter

Below are the details needed in order to use the JJWT libraries in JMeter. 

---

## Download Apache Maven.

Download [Apache Maven](https://maven.apache.org/download.cgi).

---

## Check / Install JDK .
Have a JDK installation on your system (Recommend JDK8). 

![Java_version](https://user-images.githubusercontent.com/86320001/149629073-1fb33a7d-9346-4278-aa65-beaeabf3b5b2.PNG)

---

## Set the JAVA_HOME environment variable.
Either set the JAVA_HOME environment variable pointing to your JDK installation or have the java executable on your PATH.

![JDK_JavaHome_Path](https://user-images.githubusercontent.com/86320001/149629058-304f1a00-aa7f-4860-9e69-4e40f51e796f.PNG)

---

## Set the Apache Maven environment variable.
Add the Maven bin directory to System Environment Variables

![Maven_Env_Variable](https://user-images.githubusercontent.com/86320001/149629208-dd38e305-1594-4701-999c-6230ae6b2d64.PNG)

---

## Check Apache Maven version.
Check that the System Environment Variable is recognised by running a version check
```
mvn -v
```

![Maven_version](https://user-images.githubusercontent.com/86320001/149629666-d677800d-afa7-43d3-8c96-dcc76b231eec.PNG)

---

## Create a POM file.
Create a POM file in the Apache Maven directory
> C:\apache-maven-3.8.2\bin

See attached POM for example.

---

## Get the lib files.
Change directory in command prompt to the Maven bin folder
> cd C:\apache-maven-3.8.2\bin

Execute mvn dependency:copy-dependencies command
```
mvn dependency:copy-dependencies
```

![Run_mvn_dep_command](https://user-images.githubusercontent.com/86320001/149629709-276f118e-b4da-4aad-9f96-a7ca8770a456.PNG)

Copy everything from target/dependency folder to "lib" folder of your JMeter installation (or other location in JMeter Classpath)

![Copy_content_to_lib](https://user-images.githubusercontent.com/86320001/149629865-951c5bc7-b769-4e82-ab64-670d602d8606.PNG)

Restart JMeter

---

## Create JMeter script.

Add JSR223 Sampler to your Test Plan and put your Groovy code using the jjwt library functions there.

Use the info from the [JJWT GitHub Page](https://github.com/jwtk/jjwt) to build your script;

See [attached JMX](https://github.com/w4dd325/JJWT_JMeter/blob/main/jjwt_example.jmx) for example - Note some information redacted (and replaced with descriptive comment) for security reasons.

More information on JWT 'claims' can be found [here](https://docs.microsoft.com/en-us/azure/active-directory/develop/id-tokens).
