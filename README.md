# Campus Placement Management System

**Course:** U23CS491 – Java Programming (2-0-2-2-4)  
**Institution:** Sri Eshwar College of Engineering (Autonomous), Kinathukadavu, Coimbatore  
**Target Platform:** Java 21 LTS, JavaFX 21, Embedded H2/SQLite JDBC  

---

## 📌 Project Overview
The **Campus Placement Management System** is an enterprise-grade academic Java desktop application covering all theoretical and practical concepts outlined in the **U23CS491 Java Programming** syllabus (Units I through V and Laboratory Experiments 1 through 5).

---

## 🎯 Syllabus Topic Coverage Matrix

| Unit | Syllabus Topics | Implemented Classes / Features in this Project |
| :--- | :--- | :--- |
| **Unit-I: Foundations of Java** | OOP Paradigms, Java Buzzwords, Classes & Types, Data Types, Control Statements, Wrapper Classes, Constructors & Chaining, Methods, Access Specifiers, 1D/2D Arrays, `java.util.Arrays`, JavaDoc comments, I/O Classes | `Person.java`, `Student.java` (nested static class `AcademicProfile`, 2D `semesterGrades[8][6]`, 1D `skills[]`, `Arrays.sort()`, `Arrays.binarySearch()`), `FileReportUtil.java` (`BufferedReader`, `BufferedWriter`, `PrintWriter`, `Scanner`) |
| **Unit-II: Object Oriented Mechanisms** | Association, Aggregation, Composition, Polymorphism (Overloading vs Overriding), Static & Dynamic Binding, Inheritance Types (Single, Multilevel, Hierarchical), `super`, `static`, `final` keywords, Abstraction, Abstract Classes, Interfaces, Encapsulation, Packages | `Person` (Abstract base), `Student extends Person` (Single), `PlacedStudent extends Student` (Multilevel), `PlacementOfficer extends Person` (Hierarchical), `Company` (Aggregation), `Application` (Composition), `IPlacementService` (Interface with default methods), overloaded `filterStudents(...)` |
| **Unit-III: Strings, Collections & Java 8 Features** | Strings, Immutability, `StringBuilder` vs `StringBuffer`, Regex, Collections (`List`, `Set`, `Map`), `Comparable` & `Comparator`, Java 8 Lambdas, Date & Time API (`LocalDate`, `Period`, `Duration`), Streams & Functions | `InputValidator.java` (Regex for Roll No, Email, Phone), `FileReportUtil.java` (`StringBuffer` audit logging vs `StringBuilder` reports), `PlacementServiceImpl.java` (`ArrayList`, `HashSet`, `HashMap`, `TreeMap`, `LinkedHashMap`), `Comparable<Student>`, `SearchAndSortService` comparators, `DateTimeUtil.java`, Streams (`filter`, `map`, `sorted`, `Collectors.groupingBy`, `Collectors.averagingDouble`) |
| **Unit-IV: Exception Handling & Multithreading** | Exception hierarchy, Checked vs Unchecked, `try-catch-throw-throws-finally`, Propagation, Thread creation (`Thread` subclass & `Runnable`), Thread Lifecycle & States, Synchronization Blocks, Executor Framework, Concurrency API | `PlacementException`, `StudentNotEligibleException` (Checked), `ResourceNotFoundException` (Unchecked), `DuplicateApplicationException`, `ResumeScreeningTask` (`Runnable`), `InterviewNotificationThread` (`extends Thread`), `SlotBookingManager` (`synchronized(lock)` & `ReentrantLock`), `ThreadPoolManager` (`ExecutorService`, `Future<T>`) |
| **Unit-V: JavaFX & JDBC** | JavaFX Events & Controls (`CheckBox`, `ToggleButton`, `RadioButtons`, `ListView`, `ComboBox`, `ChoiceBox`, `Text Controls`, `ScrollPane`), Layouts (`FlowPane`, `HBox`, `VBox`, `BorderPane`, `StackPane`, `GridPane`), Menus (`MenuBar`, `MenuItem`), JDBC Drivers, Steps to create JDBC Application, DB Connection Pool | `PlacementApp.java` (Main `Application`, `BorderPane`, `MenuBar`, `MenuItem`, `SeparatorMenuItem`), `StudentManagementView.java` (`GridPane`, `TableView`, `FlowPane`, `TextField`, `PasswordField`, `TextArea`, `ComboBox`, `RadioButton`, `CheckBox`, `ToggleButton`, Key/Mouse events), `JobDriveView.java` (`ListView`, `ChoiceBox`), `DBConnectionPool.java`, `DatabaseInitializer.java`, `StudentDAO.java` |
| **Lab Experiments (CO 1 - CO 5)** | Exp 1 (Class/Objects/Scanner), Exp 2 (Command line args & I/O), Exp 3 (Sequential search, binary search, quadratic sorting), Exp 4 (Encapsulation/Inheritance), Exp 5 (Interfaces) | `ConsoleRunner.java`, `SearchAndSortService.java` (Manual implementations of Linear Search, Binary Search, Bubble Sort $O(n^2)$, Selection Sort $O(n^2)$, Insertion Sort $O(n^2)$) |

---

## 🚀 How to Run in IntelliJ IDEA

### Prerequisites
- **IntelliJ IDEA** (Community or Ultimate Edition).
- **JDK 21** (or JDK 17+).

### Step 1: Open the Project in IntelliJ
1. Launch **IntelliJ IDEA**.
2. Click **File ➔ Open...** (or click **Open** on the welcome screen).
3. Navigate to and select the folder:
   ```
   c:\Users\Jaya sri\Downloads\placementfinal
   ```
   (Alternatively, select the `pom.xml` file inside this folder and click **Open as Project**).
4. IntelliJ will automatically detect Maven, index the dependencies (`javafx-controls`, `javafx-fxml`, `h2`), and configure the project.

### Step 2: Verify Project SDK (JDK 21)
1. In IntelliJ, navigate to **File ➔ Project Structure...** (or press `Ctrl + Alt + Shift + S`).
2. Under **Project Settings ➔ Project**:
   - Ensure **SDK** is set to **Java 21** (`jdk-21`).
   - Ensure **Language level** is set to **21 - Preview** or **SDK default**.
3. Click **Apply** and **OK**.

### Step 3: Run the Application

You have two convenient options to run the application:

#### Option A: Run JavaFX GUI via Maven (Recommended — Zero Configuration)
1. On the right-hand side of IntelliJ, open the **Maven** tool window.
2. Expand: **placement-management-system ➔ Plugins ➔ javafx ➔ javafx:run**.
3. Double-click **javafx:run**.
4. The JavaFX Graphical User Interface window will launch with all forms, tables, drives, and analytics ready!

*Or simply select **Run JavaFX GUI (Maven)** from the Run Configurations dropdown at the top toolbar and click the green ▶ Run button.*

#### Option B: Run via `Main.java` or `ConsoleRunner.java`
- **To run the JavaFX GUI via Application Launcher:**
  1. In the Project Explorer, open `src/main/java/com/placement/Main.java`.
  2. Right-click anywhere in the file and select **Run 'Main.main()'**.
- **To run the Interactive Console / Lab Experiment Verification:**
  1. In the Project Explorer, open `src/main/java/com/placement/ConsoleRunner.java`.
  2. Right-click and select **Run 'ConsoleRunner.main()'**.
  3. The interactive console menu will appear in the IntelliJ Run window where you can test Linear Search, Binary Search, Bubble/Selection Sort, Multithreading, and JDBC with interactive scanner inputs.

---

## 📂 Project Structure
```
placementfinal/
├── pom.xml                               # Maven project configuration (Java 21, JavaFX, H2)
├── README.md                             # Comprehensive documentation & setup instructions
├── .run/                                 # Pre-configured IntelliJ IDEA Run configurations
│   ├── Run_JavaFX_GUI__Maven_.run.xml
│   ├── ConsoleRunner__CLI_Demo_.run.xml
│   └── Main__Launcher_.run.xml
└── src/
    └── main/
        ├── java/
        │   └── com/
        │       └── placement/
        │           ├── Main.java                        # Dual-mode launcher (JavaFX GUI or CLI)
        │           ├── ConsoleRunner.java               # Comprehensive CLI covering Lab Exps 1-5
        │           ├── model/
        │           │   ├── Person.java                  # Abstract base class (Unit I & II)
        │           │   ├── Student.java                 # Core entity, Comparable, Arrays, Inner class
        │           │   ├── PlacedStudent.java           # Multilevel inheritance
        │           │   ├── PlacementOfficer.java        # Hierarchical inheritance
        │           │   ├── Company.java                 # Aggregation & Association
        │           │   ├── JobPosting.java              # Nested static class EligibilityCriteria
        │           │   ├── Application.java             # Composition with EvaluationRecord
        │           │   └── ApplicationStatus.java       # Enum states
        │           ├── exception/
        │           │   ├── PlacementException.java      # Base checked exception
        │           │   ├── StudentNotEligibleException.java # Checked domain exception
        │           │   ├── DuplicateApplicationException.java
        │           │   └── ResourceNotFoundException.java # Unchecked RuntimeException
        │           ├── service/
        │           │   ├── IPlacementService.java       # Interface with default methods
        │           │   ├── PlacementServiceImpl.java    # Overloading, Collections, Streams, Lambdas
        │           │   └── SearchAndSortService.java    # Lab Exp 3: Linear/Binary search & Quadratic sort
        │           ├── multithreading/
        │           │   ├── ResumeScreeningTask.java     # Runnable interface implementation
        │           │   ├── InterviewNotificationThread.java # Thread subclassing & lifecycle
        │           │   ├── PlacementReportCallable.java # Callable & Future
        │           │   ├── SlotBookingManager.java      # Synchronized blocks & ReentrantLock
        │           │   └── ThreadPoolManager.java       # ExecutorService framework
        │           ├── database/
        │           │   ├── DBConnectionPool.java        # Connection Pool implementation
        │           │   ├── DatabaseInitializer.java     # JDBC schema creation & seed data
        │           │   └── StudentDAO.java              # PreparedStatement & Transaction management
        │           ├── util/
        │           │   ├── InputValidator.java          # Regex validation (Email, Phone, Roll No)
        │           │   ├── DateTimeUtil.java            # Java 8 Date/Time API (LocalDate, Duration)
        │           │   └── FileReportUtil.java          # File I/O, StringBuilder vs StringBuffer
        │           └── ui/
        │               ├── PlacementApp.java            # JavaFX Application (BorderPane, MenuBar)
        │               ├── StudentManagementView.java   # GridPane, TableView, Form controls, Events
        │               ├── JobDriveView.java            # ListView, ChoiceBox, Exception Dialogs
        │               └── AnalyticsAndMultithreadingView.java # Streams Analytics & Concurrency Lab
        └── resources/
            └── styles.css                               # Modern styling for JavaFX components
```
