```markdown
# CV Processing Task

## Overview

This Spring Boot application monitors a specified directory for new CV files in PDF, Word (.docx), or plain text (.txt) formats. When a new file is detected, it extracts relevant information such as skills, email addresses, and phone numbers (specifically those starting with `961`) from the CV and writes the extracted information to a new text file in a specified output directory. The application leverages multithreading to handle multiple CV files concurrently.

## Features

- **Directory Monitoring:** Watches a specified input directory for new CV files.
- **File Processing:** Supports PDF, Word (.docx), and plain text (.txt) formats.
- **Information Extraction:** Extracts skills (Java, Python, Spring Boot), email addresses, and phone numbers starting with `961`.
- **Output Generation:** Writes the extracted information to a text file in a specified output directory.
- **Multithreading:** Utilizes a thread pool to process multiple files simultaneously for efficient handling of large volumes of CVs.

## Dependencies

Ensure the following dependencies are included in your `pom.xml`:

```xml
<dependencies>
    <!-- Spring Boot dependencies -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-scheduling</artifactId>
    </dependency>

    <!-- PDFBox for PDF file handling -->
    <dependency>
        <groupId>org.apache.pdfbox</groupId>
        <artifactId>pdfbox</artifactId>
        <version>2.0.24</version>
    </dependency>

    <!-- Apache POI for DOCX file handling -->
    <dependency>
        <groupId>org.apache.poi</groupId>
        <artifactId>poi-ooxml</artifactId>
        <version>5.2.2</version>
    </dependency>
</dependencies>
```

## Configuration

Update the `application.properties` file with the input and output directory paths:

```properties
input.directory=C:\\Users\\kabbania\\Desktop\\CVS
output.directory=C:\\Users\\kabbania\\Desktop\\Processed
```

## How to Run
Sure, continuing from where we left off:

### How to Run

1. **Clone the Repository:**
   Clone the repository to your local machine using Git:
   ```bash
   git clone <repository-url>
   ```

2. **Set Configuration:**
   Update the `application.properties` file with the correct paths for input and output directories:
   ```properties
   input.directory=C:\\path\\to\\input\\directory
   output.directory=C:\\path\\to\\output\\directory
   ```

3. **Build the Application:**
   Navigate to the project directory and build the application using Maven:
   ```bash
   mvn clean install
   ```

4. **Run the Application:**
   Run the Spring Boot application:
   ```bash
   java -jar target/cv-processing-task.jar
   ```

5. **Verify Output:**
   Monitor the console output to see the processing of CV files. Check the specified output directory for text files containing extracted information.

### Notes

- **Supported Formats:** Ensure that the CV files in the input directory are in PDF, DOCX, or plain text (TXT) formats for proper processing.
- **Multithreading:** The application handles multiple CV files concurrently using Spring's thread pool mechanism, optimizing performance.
- **Dependencies:** Make sure all dependencies specified in the `pom.xml` file are correctly included to avoid runtime issues.

### Troubleshooting

- **Empty Output Files:** If output files are empty or corrupted, check the file writing logic (`processCVFile` method) and ensure proper handling of extracted information.
- **File Format Issues:** Ensure that the application supports all required file formats and handles them appropriately during processing.

### Contributing

Contributions to enhance the functionality, improve performance, or fix bugs are welcome. Please fork the repository, create a new branch, and submit a pull request with your changes.

### Contact

For any questions, feedback, or issues, please contact me.

---
