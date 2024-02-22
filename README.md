</details>

******

<details>
<summary>Clone project and create own Git repository </summary>
 <br />

To work with the project for the exercises:

- Clone the project and
- create your own project/git repository from it

**steps:**

```sh
# clone repository & change into project dir
git clone git@gitlab.com:twn-devops-bootcamp/latest/04-build-tools/build-tools-exercises.git
cd build-tools-exercises

# remove remote repo reference and create your own local repository
rm -rf .git
git init 
git add .
git commit -m "initial commit"

# create git repository on Gitlab and push your newly created local repository to it
git remote add origin git@gitlab.com:{gitlab-user}/{gitlab-repo}.git
git push -u origin master

```
<img src="https://i.imgur.com/xgG4CRE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Build jar artifact </summary>
 <br />


You want to deploy the artifact to share that library with all team members. So:

- try to build the jar file
- The Build will fail, because of a compile error in a test, so you can't build the jar.

**steps**

```sh
gradle build

```

<img src="https://i.imgur.com/VRYrXIo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Run tests </summary>
 <br />


- Fix the test, by changing "true" string to true boolean.
- Run gradle test to execute only the tests and check the fix.

**steps:**
```sh
# locate AppTest.java file in src/test/java folder, line 22 & fix test
boolean result = myApp.getCondition(true); 

# run tests
gradle test

```

<img src="https://i.imgur.com/CEWz661.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Clean & build App </summary>
 <br />

You fixed the test. Now:

- clean the build folder with gradle clean and
- try to build jar file again.

**steps:**
```sh
gradle clean 
gradle build

```

<img src="https://i.imgur.com/OOrao5m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/HbmMTKV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</details>

******

<details>
<summary> Start application </summary>
 <br />

Start the jar file to test that the application runs successfully as a jar file

- Start app with /build/libs java -jar app-1.0.jar
- NOTE: replace "app-1.0.jar" with the name of YOUR jar file.


**steps:**
```sh
java -jar bootcamp-java-project-1.0-SNAPSHOT.jar

```

<img src="https://i.imgur.com/GPhhxhy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Start App with 2 Parameters </summary>
 <br />

Now you want to add parameters to your application, so you and other users can pass different values on startup.

- Add parameter input to the Java code (see code snippet below, which you can copy)
- Rebuild the jar file
- Execute the jar file again with 2 params


**steps:**
```sh
# add parameter input to the Java code, in Application.java, on line 16
Logger log = LoggerFactory.getLogger(Application.class); 
try { 
    String one = args[0]; 
    String two = args[1]; 
    log.info("Application will start with the parameters {} and {}", one, two); 
} catch (Exception e) { 
    log.info("No parameters provided"); 
}

# rebuild the jar file 
gradle build

# run application with ANY 2 parameters
java -jar bootcamp-java-project-1.0-SNAPSHOT.jar myname mylastname

```

<img src="https://i.imgur.com/XMLcAWa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</details>



