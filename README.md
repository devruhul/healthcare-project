# Healthcare Management System

A desktop healthcare administration application built with Java Swing. It provides role-based access to patient, clinician, staff, facility, appointment, prescription, and referral records stored in CSV files.

## Features

- Role-based login for administrators, clinicians, staff, and patients
- Create, view, update, and delete healthcare records through a desktop interface
- Manage patients, clinicians, staff, facilities, appointments, prescriptions, and referrals
- Generate text records for prescriptions and referrals
- Store application data in editable CSV files
- Patient self-registration using a valid patient ID

## Requirements

- Java Development Kit (JDK) 11 or later
- A terminal or IDE with Java support, such as VS Code, IntelliJ IDEA, or Eclipse

## Run the Application

From the project root, compile the source files into the `out` directory:

```bash
javac -d out $(find src -name "*.java")
```

Then start the application:

```bash
java -cp out Main
```

The application can also be run directly from an IDE by opening `src/Main.java`. The CSV data loader locates the project's `data` directory even when the IDE uses a nested working directory.

## Test Accounts

| Role | Username | Password |
| --- | --- | --- |
| Administrator | `admin` | `admin123` |
| Clinician | `c001` | `pass123` |
| Staff | `st001` | `pass123` |
| Patient | `p001` | `pass123` |

## Access by Role

| Role | Available areas |
| --- | --- |
| Patient | Facilities, appointments |
| Staff | Patients, facilities, appointments |
| Clinician | Patients, appointments, referrals |
| Administrator | Patients, clinicians, staff, facilities, appointments, prescriptions, referrals |

## Project Structure

```text
healthcare-project/
├── data/                  # CSV data used by the application
├── output/
│   ├── prescriptions/     # Generated prescription text files
│   └── referrals/         # Generated referral text files
├── src/
│   ├── controller/        # Application controllers
│   ├── model/             # Domain models
│   ├── repository/        # CSV persistence and file generation
│   ├── view/              # Java Swing screens and panels
│   └── Main.java          # Application entry point
└── README.md
```

## Data Storage

All application records are kept in `data/` as CSV files:

- `users.csv`
- `patients.csv`
- `clinicians.csv`
- `staff.csv`
- `facilities.csv`
- `appointments.csv`
- `prescriptions.csv`
- `referrals.csv`

Changes made through the application are written back to these files. Generated prescription and referral documents are saved under `output/`.

## Notes

This is an educational project. Credentials are stored as plain text in `data/users.csv`; a production healthcare system should use hashed passwords, a database, audit logging, validation, and appropriate security controls.
