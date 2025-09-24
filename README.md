Project Overview The University Management System is a Java-based console application that manages students, courses, enrollments, and grading. It is designed to demonstrate key Java concepts such as: • OOP principles (Encapsulation, Inheritance, Polymorphism) • Java Collections Framework (List, Map, Stream API) • Java Date/Time API (LocalDate, LocalDateTime) • File I/O using NIO.2 for importing/exporting CSV files • Menu-driven CLI with loops, switch statements, and labeled jumps Features • Student Management: Add, list, update, and deactivate students • Course Management: Add, list, update, deactivate, and search courses by instructor, department, or semester • Enrollment & Grading: Enroll/unenroll students, record marks, compute grades & GPA, print transcripts • File Operations: Import/export students and courses from CSV files, create backups, and recursively compute directory sizes Tech Stack • Language: Java • JDK Version: Java 17 or later (tested on JDK 17 & JDK 21) • Build Tool: None (Plain Java – can compile with javac) • Dependencies: None (only standard Java libraries) How to Run Install JDK Make sure Java JDK 17 or later is installed. • Check version: java -version Example output: java version "17.0.10" 2024-01-16 LTS If you don’t have JDK 17+, download it from: 👉 https://adoptium.net/ or Oracle JDK Clone or Download the Project git clone https://github.com/your-username/university-management-java.git cd university-management-java/src If you downloaded a ZIP, unzip it and cd into the src folder Compile the Project Run the following inside the src folder (where the java_project package is located): javac java_project/*.java This compiles all .java files into .class files inside the same package. Run the Application After successful compilation, run the MasterCLI main class: java java_project.MasterCLI (Optional) Import CSV Files To test File Operations, prepare CSV files like: 📄 students.csv id,regNo,fullName,email,dateOfBirth 1,REG2025-001,John Doe,john@example.com,2001-05-14 2,REG2025-002,Jane Smith,jane@example.com,2002-03-22 courses.csv code,title,credits,instructor,semester,department CS101,Intro to Programming,3,Dr. Allen,SPRING,Computer Science MA201,Linear Algebra,4,Prof. Lee,FALL,Mathematics In the CLI: Main Menu -> File Operations -> Import Students/Courses

Example Commands • List all students: Main Menu -> Student Management -> List Students • Enroll a student: Main Menu -> Enrollment & Grading -> Enroll Student • Generate transcript: Main Menu -> Enrollment & Grading -> Print Transcript

Project Structure src/ └── java_project/ ├── MasterCLI.java # Main menu-driven CLI ├── Student.java # Student entity ├── StudentManager.java # Manage students ├── Course.java # Course entity ├── CourseManager.java # Manage courses ├── EnrollmentManager.java # Enrollment & grading logic ├── FileOperations.java # CSV import/export utilities ├── Semester.java # Enum for semesters └── GradeCalculator.java # Utility for GPA & grade calculations

Recommended JDK JDK Version Status JDK 17 Tested JDK 21 Tested JDK 11 May work (update switch expressions if needed)

Tips • Always run commands inside the src folder. • Use CSV files with proper formatting to avoid parsing errors. • To clear compiled files: rm java_project/*.class Evolution of Java (Key Milestones) • 1991 – Project Green started by Sun Microsystems to create a portable, platform-independent language for consumer devices (originally called Oak). • 1995 – Official release of Java 1.0, introducing the “Write Once, Run Anywhere” philosophy with the JVM (Java Virtual Machine). • 1998 – Java 2 (J2SE 1.2) introduced Swing, Collections Framework, and a more robust API. • 2004 – Java 5 (J2SE 5.0) added Generics, Enums, Annotations, and the enhanced for-each loop. • 2006 – Sun open-sourced Java under the GPL and released the OpenJDK project. • 2009–2010 – Oracle acquired Sun Microsystems and took over Java’s development. • 2011 – Java 7 introduced try-with-resources, NIO.2, and improved concurrency. • 2014 – Java 8 brought major functional programming features like Lambdas, Streams API, and a new Date/Time API. • 2017 – Oracle introduced a 6-month release cycle, starting with Java 9 (modules system). • 2018–2021 – Releases like Java 11, 14, and 17 added var keyword, switch expressions, records, and sealed classes. • Present (Java 21) – Continues to evolve with pattern matching, virtual threads (Project Loom), and performance improvements while maintaining backward compatibility. Java Editions Comparison Java ME (Micro Edition) • Designed for small devices like feature phones, IoT devices, smart cards, TVs, and embedded systems. • Provides lightweight configurations such as CLDC (Connected Limited Device Configuration) and MIDP (Mobile Information Device Profile). • Uses a compact Java ME Virtual Machine (KVM/CLDC HotSpot) to run on resource-constrained hardware. • Suitable for mobile games, IoT controllers, and simple device apps. • Optimized for low memory and low CPU power. Java SE (Standard Edition) • The core Java platform and foundation for all other editions. • Targets desktop, laptop, and small client-server applications. • Includes core APIs: Collections Framework, Streams, JDBC, NIO, Networking, Swing/JavaFX, and the Java Virtual Machine (JVM). • Used for standalone desktop applications, small-scale web servers, and learning Java fundamentals. • Forms the base for both Java ME and Java EE. Java EE (Enterprise Edition) (now Jakarta EE) • Built on top of Java SE for large-scale, distributed, enterprise applications. • Provides additional APIs such as Servlets, JSP, EJB, JPA, JMS, JAX-RS, WebSocket, and more. • Runs on an application server (e.g., GlassFish, WildFly, Payara) to support multi-tier architectures. • Ideal for high-performance web apps, cloud applications, e-commerce, and banking systems. • Handles transaction management, security, and scalability for mission-critical systems.

Quick Summary • Java ME → Lightweight and optimized for mobile/embedded devices. • Java SE → The core Java platform for desktop and general-purpose development. • Java EE → Enterprise-grade platform for server-side, distributed, and cloud applications. JDK vs JRE vs JVM JVM (Java Virtual Machine) • What it is: A virtual machine that runs Java bytecode. • Role: Converts compiled bytecode (.class files) into machine code for the host operating system. • Key Feature: Provides platform independence – “Write Once, Run Anywhere”. • Includes: Class loader, bytecode verifier, JIT (Just-In-Time) compiler, and garbage collector. • Developer/End User: Needed by both developers and end-users to run Java programs.

JRE (Java Runtime Environment) • What it is: A runtime package that provides all the libraries and the JVM needed to run Java applications. • Role: Allows you to run Java programs but cannot compile them. • Includes: JVM + core libraries (collections, networking, I/O, etc.) + supporting files. • Developer/End User: Suitable for end-users who just need to run Java apps.

JDK (Java Development Kit) • What it is: A full software development kit required to develop and run Java programs. • Role: Provides everything in the JRE plus development tools to compile and debug code. • Includes: JRE + compiler (javac) + debugger + tools like jar, javadoc. • Developer/End User: Required for developers to write and compile Java code.

Quick Summary • JVM → The engine that executes Java bytecode. • JRE → JVM + libraries to run Java programs. • JDK → JRE + tools to develop and compile Java programs.

Part 1 – Install Java JDK on Windows

Download JDK
Go to Oracle JDK Downloads (or Adoptium if you prefer OpenJDK).
Choose the latest LTS version (e.g., Java 17 or Java 21).
Click Windows x64 Installer (.msi) to download.
Run the Installer
Double-click the downloaded .msi file.
In the wizard, click Next, accept the license, and use the default installation path (e.g., C:\Program Files\Java\jdk-17).
Finish the installation.
Set Environment Variables
Press Win + S, type Environment Variables, and open Edit the system environment variables.
Click Environment Variables….
Under System variables, find and select Path → Edit → New.
Add the JDK bin path (e.g., C:\Program Files\Java\jdk-17\bin).
Click OK to save. 📸 Screenshot Tip: Show the Path variable with the new JDK entry.
Verify Installation Open Command Prompt and type: java -version javac -version You should see the installed version numbers.
Part 2 – Install and Setup Eclipse IDE

Download Eclipse
Go to Eclipse Downloads.
Click Download x86_64 for Eclipse IDE for Java Developers.
Install Eclipse
Run the downloaded Eclipse Installer.
Choose Eclipse IDE for Java Developers and click Install.
Accept the license agreement.
After installation, click Launch.
3.First Launch & Workspace

When Eclipse starts, it asks for a workspace directory (where projects will be stored). Choose a convenient folder (e.g., C:\EclipseWorkspace) and click Launch. 📸 Screenshot Tip: Capture the workspace selection window.
4.Configure Java Compiler (if needed)

Go to Window → Preferences → Java → Installed JREs.
Check that your installed JDK is listed. If not, click Add → Standard VM → Directory and browse to C:\Program Files\Java\jdk-17.
Apply and close. 📸 Screenshot Tip: Show the Installed JREs screen with JDK selected.
Create a New Java Project
Click File → New → Java Project.
Enter a Project Name and click Finish.
Right-click src → New → Class to create your first Java class. 📸 Screenshot Tip: Capture the new project wizard.
Quick Test Paste a simple program: public class Hello { public static void main(String[] args) { System.out.println("Hello, Java!"); } } Run → Run As → Java Application. You should see output in the Eclipse Console.

Syllabus Topic → Project Mapping
Syllabus Topic Where It’s Demonstrated (File / Class / Method) Explanation OOP – Classes & Objects Student.java, Course.java, EnrollmentManager.java Core entities are modeled as Java classes with fields, constructors, and methods. Encapsulation (Getters/Setters) Student.java (getId(), setEmail(), etc.) Private fields with public getters/setters to protect data. Inheritance & Polymorphism Transcript printing via toString() in Student.java and Course.java Overridden toString() methods provide polymorphic string output. Abstraction (Interfaces/Enums) Semester.java (enum), Grade.java (enum) Enums abstract semester and grade logic. Collections Framework StudentManager.java (List students), CourseManager.java (List courses) Uses ArrayList to store and manage data. Stream API & Lambda CourseManager.java → searchByInstructor(), filterByDepartment(), filterBySemester() Uses Streams and lambda expressions for filtering/searching. Date/Time API Student.java (LocalDate dob, enrollmentDate), FileOperations.java Uses java.time.LocalDate for student DOB and timestamps. Enums Semester.java, Grade.java Strongly typed constants for semesters and letter grades. Exception Handling FileOperations.java (try-catch in importStudents(), importCourses()) Handles IOException while reading CSV files. File I/O (NIO.2) FileOperations.java (Files.lines(), Path, Files.copy()) Demonstrates Files, Path, and Streams for import/export/backup. CLI / Console I/O MasterCLI.java (menu loop, switch) Menu-driven console with Scanner, loops, and switch statements. Decision Making MasterCLI.java (switch cases), EnrollmentManager.java (if-else checks for max credits) Conditional logic for user choices and enrollment rules. Loops MasterCLI.java (while loop for menu), StudentManager.java (enhanced-for loop to list students) Demonstrates while, for, and enhanced-for loops. Break / Continue / Labeled Jump MasterCLI.java inside menu navigation Shows break and continue in menu-driven logic. Generics List, List in all manager classes Uses generic collections for type-safe data storage. Static Members GradeCalculator.java (static methods to compute GPA) Provides utility methods without needing object creation. Package Management package java_project; in every class Organizes code into a single logical package. JDK/JRE/JVM Project compilation & execution process Demonstrated during project build (javac → bytecode → JVM execution). JavaFX / GUI (Optional) (Not applicable) This project is console-based, but could be extended to GUI later.

Assertions in Java • Assertions are used to test assumptions during runtime. • They help in debugging and catching programming errors early. • If the assertion condition is false, the JVM throws an AssertionError. • Assertions are disabled by default at runtime. Example: int age = -5; assert age >= 0 : "Age cannot be negative!";

Enabling Assertions By default, running a Java program with: java MyClass will not evaluate assertions. You must explicitly enable them using: • -ea → enable assertions • -da → disable assertions • -esa → enable assertions in system classes (rarely needed)

Sample Commands

Compile the Program javac MyClass.java This creates MyClass.class (bytecode).
Run With Assertions Enabled java -ea MyClass or, to enable assertions only in a specific package/class: java -ea:java_project... MyClass (Replace java_project with your package name)
Disable Assertions (Default) java -da MyClass
Enable Assertions for System Classes (Used if you want to check JDK internal classes too) java -esa MyClass
Project Example If your main class is MasterCLI inside the java_project package: javac java_project/MasterCLI.java java -ea java_project.MasterCLI

Tips • Use assert for development/testing, not for production validation (use exceptions instead). • Assertions can be selectively enabled per class or per package, which is useful for large projects. • You can combine options: java -ea:java_project... -da:java_project.test... java_project.MasterCLI This enables assertions for all classes in java_project but disables them in java_project.test.
