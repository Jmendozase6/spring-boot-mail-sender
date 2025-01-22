# Spring Boot Email Sender

This project is a Spring Boot application that provides RESTful APIs to send emails with or without attachments.

## Technologies Used

- Java
- Spring Boot
- Maven

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven 3.6.0 or higher

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/spring-boot-email-sender.git
    ```
2. Navigate to the project directory:
    ```sh
    cd spring-boot-email-sender
    ```
3. Build the project using Maven:
    ```sh
    mvn clean install
    ```

### Running the Application

To run the application, use the following command:
```sh
mvn spring-boot:run
```

## API Endpoints

### Send Email

- **URL:** `/v1/sendMessage`
- **Method:** `POST`
- **Request Body:**
    ```json
    {
        "toUser": ["recipient@example.com"],
        "subject": "Email Subject",
        "message": "Email Message"
    }
    ```
- **Response:**
    ```json
    {
        "status": "Send"
    }
    ```

### Send Email with Attachment

- **URL:** `/v1/sendMessageFile`
- **Method:** `POST`
- **Request Body:** `multipart/form-data`
    - `toUser`: Array of recipient email addresses
    - `subject`: Email subject
    - `message`: Email message
    - `file`: File to be attached
- **Response:**
    ```json
    {
        "status": "Send",
        "file": "filename.ext"
    }
    ```