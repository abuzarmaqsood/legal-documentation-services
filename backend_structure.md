# Flask Backend Architecture (MVP)

> Project: **Legal Documentation Services**
>
> Purpose: Build a simple, maintainable backend for the MVP.
>
> This backend is intentionally minimal. It is designed only to support the first version of the website and should avoid unnecessary complexity.

---

# MVP Goals

The backend should only handle:

- Contact form submissions
- Document uploads
- Sending an email notification to the owner
- Returning success/failure responses

There is:

- ❌ No database
- ❌ No authentication
- ❌ No user accounts
- ❌ No admin panel
- ❌ No dashboard
- ❌ No payment integration
- ❌ No document history

Every request is independent.

---

# Workflow

```
Customer

↓

Opens Website

↓

Fills Contact Form

↓

(Optional) Uploads Documents

↓

Clicks Submit

↓

Flask receives request

↓

Validates data

↓

Stores uploaded files temporarily

↓

Sends email to owner
    (with uploaded files attached)

↓

Deletes temporary files

↓

Returns Success Response
```

---

# Technology Stack

- Python 3
- Flask
- Flask-CORS
- python-dotenv
- Gunicorn (production)
- SMTP (or email service later)

---

# Folder Structure

```
backend/

├── app/
│
│   ├── __init__.py
│   ├── config.py
│   │
│   ├── routes/
│   │   ├── __init__.py
│   │   ├── health.py
│   │   └── contact.py
│   │
│   ├── services/
│   │   ├── email_service.py
│   │   ├── upload_service.py
│   │   └── validation_service.py
│   │
│   ├── utils/
│   │   ├── file_utils.py
│   │   └── response.py
│   │
│   ├── templates/
│   │   └── quotation_email.html
│   │
│   └── uploads/
│       └── .gitkeep
│
├── tests/
│
│   ├── test_contact.py
│   └── test_health.py
│
├── .env
├── .env.example
├── .gitignore
├── app.py
├── requirements.txt
├── README.md
└── run.py
```

---

# Folder Responsibilities

---

## app/

Contains the actual Flask application.

---

## routes/

Contains API endpoints.

### health.py

```
GET /health
```

Returns:

```json
{
    "status": "ok"
}
```

Used for deployment checks.

---

### contact.py

Contains the only business endpoint.

```
POST /api/contact
```

Responsibilities:

- Validate request
- Receive uploaded files
- Save temporary files
- Call email service
- Delete temporary files
- Return JSON response

---

## services/

Contains business logic.

Routes should stay small.

---

### email_service.py

Responsible for:

- Creating email
- Attaching uploaded files
- Sending email

Routes should never contain email logic.

---

### upload_service.py

Responsible for:

- Saving uploaded files
- Generating safe filenames
- Returning file paths
- Deleting uploaded files

---

### validation_service.py

Responsible for validating:

- Name
- Email
- Phone
- Message
- Uploaded files

Keeps validation separate from routes.

---

## utils/

Small helper functions.

---

### file_utils.py

Examples:

- Allowed file extensions
- File size helpers
- Filename sanitization

---

### response.py

Creates consistent JSON responses.

Example:

Success

```json
{
    "success": true,
    "message": "Request submitted successfully."
}
```

Failure

```json
{
    "success": false,
    "message": "Invalid email address."
}
```

---

## templates/

Contains HTML email templates.

Example:

quotation_email.html

The email sent to the owner should be nicely formatted instead of plain text.

---

## uploads/

Temporary storage.

Uploaded files exist only until the email is successfully sent.

After email is sent:

```
Delete uploaded files
```

Nothing remains on the server.

---

# API Design

---

## Health Check

### Endpoint

```
GET /health
```

Response

```json
{
    "status": "ok"
}
```

---

## Contact Request

### Endpoint

```
POST /api/contact
```

Request

Multipart Form Data

Fields

```
name

email

phone

sourceLanguage

targetLanguage

message

documents[]
```

Example

```
name = John

email = john@gmail.com

phone = 9999999999

sourceLanguage = English

targetLanguage = Hindi

message = Need translation before Monday.

documents = affidavit.pdf
```

---

Response

```json
{
    "success": true,
    "message": "Your request has been submitted successfully."
}
```

---

# Validation Rules

Name

- Required

Email

- Required
- Must be valid

Phone

- Required

Languages

- Optional

Message

- Optional

Documents

- Optional

Maximum files

```
5
```

Maximum size per file

```
20 MB
```

Allowed formats

```
pdf

doc

docx

jpg

jpeg

png
```

---

# Environment Variables

```
FLASK_ENV=development

SECRET_KEY=xxxxxxxx

MAIL_SERVER=smtp.gmail.com

MAIL_PORT=587

MAIL_USERNAME=your-email

MAIL_PASSWORD=your-password

MAIL_RECEIVER=owner-email

UPLOAD_FOLDER=app/uploads

MAX_CONTENT_LENGTH=104857600
```

---

# Request Flow

```
Request

↓

Validate Form

↓

Save Files

↓

Generate Email

↓

Attach Files

↓

Send Email

↓

Delete Files

↓

Return Response
```

---

# Error Handling

Return meaningful HTTP status codes.

Examples

Bad Request

```
400
```

Payload Too Large

```
413
```

Unsupported File Type

```
415
```

Internal Server Error

```
500
```

---

# Logging

Use Python's built-in logging module.

Log:

- Incoming requests
- Email success
- Email failure
- Upload failures
- Unexpected exceptions

Do not log sensitive user information.

---

# Security Considerations

- Validate uploaded file extensions
- Limit maximum upload size
- Sanitize filenames
- Never execute uploaded files
- Delete uploaded files after processing
- Store secrets in `.env`

---

# Development Principles

- Keep routes thin
- Put business logic inside services
- Keep helper functions inside utils
- Return consistent JSON responses
- Keep folders small and focused
- Avoid unnecessary abstractions

---

# Future Expansion (Not Part of MVP)

When the project grows, the following can be added without restructuring the existing codebase:

- Database (PostgreSQL)
- Authentication
- Admin dashboard
- Order tracking
- Customer history
- Translator management
- Cloud file storage
- Payment integration
- Notifications
- Analytics
- API versioning

These features are intentionally excluded from the MVP to keep the initial implementation simple and focused.