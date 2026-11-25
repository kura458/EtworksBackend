# EtworksBackend — Job Portal API

EtworksBackend is the Spring Boot backend for a job portal serving job seekers, employers, and administrators. It exposes REST API workflows for authentication, job management, applications, profiles, CV generation, payments, notifications, and administration.

## Main API capabilities

- Email/password authentication, OTP verification, token refresh, logout, and password reset
- Administrator authentication and role-based access
- Google OAuth integration
- Job creation, listing, filtering, updates, deactivation, likes, and saved jobs
- Job applications and application status management
- Seeker profiles, skills, projects, and CV details
- CV template listing, profile auto-fill, and PDF generation
- Employer company profiles, verification, and analytics
- Administrator user management, CV templates, verification review, and analytics
- Job alerts and job/candidate matching
- Chapa payment workflow and payment verification
- Notifications and AI chat endpoint

## Technology

- Java 21
- Spring Boot 3.5.8
- PostgreSQL
- Flyway
- Spring Security
- JWT and OAuth2
- OpenAPI / springdoc
- OpenPDF

External integrations include Brevo, Cloudinary, Chapa, Google OAuth, and Gemini.

## Run locally

Open the backend project directory (the folder containing the Maven project file), then run:

```bash
mvn spring-boot:run
```

The backend is configured to use port `8080` in the documented local setup:

```text
http://localhost:8080
```

The exact command and required profile may vary with the current project structure.

## Configuration

Provide the required database and service settings through your local environment or the configuration mechanism used by the application. Common settings include:

| Variable | Purpose |
|---|---|
| `DB_URL` | PostgreSQL JDBC connection URL |
| `DB_USERNAME` | Database username |
| `DB_PASSWORD` | Database password |
| `JWT_SECRET` | Token signing secret |
| `GOOGLE_CLIENT_ID` | Google OAuth client ID |
| `GOOGLE_CLIENT_SECRET` | Google OAuth client secret |
| `BREVO_SMTP_USERNAME` | Brevo SMTP username |
| `BREVO_SMTP_KEY` | Brevo SMTP credential |
| `GEMINI_API_KEY` | Gemini API key |

Check the application's configuration files for the exact property names and any additional integration settings. Move hard-coded secrets into environment variables before deployment. Never commit real credentials.

## Selected API areas

- Authentication: `/api/v1/auth/*` and `/api/v1/admin/auth/*`
- Jobs: `/api/v1/jobs`
- Applications: `/api/v1/applications`
- Seeker profile: `/api/v1/seekers/profile`
- Employer: `/api/v1/company-profile`
- Administration: `/api/v1/admin/*`
- CV builder: `/api/v1/cv-builder/*`
- Payments: `/api/v1/payments/*`
- Notifications: `/api/v1/notifications/*`
- AI: `/api/v1/ai/chat`

For request and response details, inspect the controller mappings and generated OpenAPI documentation in the running application.

## Related repository

- [Etworks — React frontend](https://github.com/kura458/Etworks)

## Development notes

The API and its integrations are evolving. Confirm current endpoint behavior, environment configuration, and unfinished workflows before deploying to production.

## Author

Maintained under [kura458](https://github.com/kura458).

---
*Developing secure and useful backend services for a role-based job portal.*
