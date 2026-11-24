# Hospital Appointment System (CS-301L Quiz 01, Q2)

Stack: HTML/CSS/Bootstrap, JavaScript, NestJS, PostgreSQL, TypeORM.

## Setup
1. Create the database:  createdb hospital   (or CREATE DATABASE hospital; in psql)
2. Copy .env.example to .env if your Postgres settings differ (defaults: postgres/postgres on localhost:5432)
3. npm install
4. npm run start:dev
5. Open http://localhost:3000

Tables are created automatically (TypeORM synchronize). Two doctors are seeded on first run.

## API
Doctors (public)
- GET  /doctors
- POST /doctors            { "name": "Dr. X", "specialization": "Cardiology" }

Appointments (header x-api-key: hospital-secret-key required)
- GET    /appointments
- GET    /appointments/:id
- POST   /appointments     { "patientName": "Ali", "doctorId": 1, "date": "2026-12-01T10:00:00.000Z", "reason": "Checkup" }
- PATCH  /appointments/:id { "reason": "Follow up" }
- DELETE /appointments/:id

## Layout
- src/doctors        entity, DTO, service, controller, module
- src/appointments   entity, DTOs, service, controller, module
- src/common         LoggerMiddleware and ApiKeyGuard
