# SkillGap Analyzer – Web Dashboard + DevOps

A Java 17 and Maven project with a browser-based dashboard. The UI is served by a lightweight Java HTTP server built into the JDK; no Node.js, XAMPP, database, or extra web framework is required. The original console app and JUnit tests are retained.

## Open in VS Code
1. Extract this ZIP.
2. In VS Code choose **File → Open Folder** and select `SkillGap-Analyzer-DevOps` (the folder containing `pom.xml`).
3. Install **Extension Pack for Java** and **Maven for Java** if prompted.
4. Open a VS Code terminal in the project root.

## Run the web dashboard
Use the Maven command below (replace the Maven path if yours is different):

```powershell
& "$env:USERPROFILE\Downloads\apache-maven-3.10.0-bin\apache-maven-3.10.0\bin\mvn.cmd" clean test
& "$env:USERPROFILE\Downloads\apache-maven-3.10.0-bin\apache-maven-3.10.0\bin\mvn.cmd" exec:java "-Dexec.mainClass=com.sameer.skillgap.WebMain"
```

When the terminal says the dashboard is ready, open **http://localhost:8080** in Chrome. Keep the VS Code terminal running while using the site. Press **Ctrl+C** in the terminal to stop it.

## VS Code Run button
Open `.vscode/launch.json`, then use **Run and Debug** and select **Run SkillGap Web Dashboard**. The Java extension may compile the source automatically. The dashboard reads `src/main/resources/static/index.html` relative to the project root, so keep the VS Code workspace open at the folder containing `pom.xml`.

## Test and package
```powershell
& "$env:USERPROFILE\Downloads\apache-maven-3.10.0-bin\apache-maven-3.10.0\bin\mvn.cmd" clean test package
```

## Features
- Interactive 0–5 sliders for Java, SQL, Git, Linux, and Problem Solving.
- Java backend calculates skill gaps, readiness, level, and priorities.
- Responsive dashboard with readiness ring, skill progress bars, and improvement order.
- Original console app (`Main`) and seven JUnit 5 tests retained.
- Jenkinsfile retained for Maven compile, test, and package stages.

## Notes
- Target levels are fixed in `SkillGapAnalyzer.java` for this demonstration.
- The dashboard binds to `127.0.0.1` and is intended for local use.
- Jenkins agents must have Java 17+ and Maven configured on PATH.
