# RAP Employee Leave Management

## Overview
This project demonstrates a Managed RAP (RESTful ABAP Programming Model) application built on **SAP BTP ABAP Environment (Trial)**.

The application manages employee leave requests and exposes data using **OData V4** with a **Fiori Elements List Report** preview.

---

## Features
- Managed RAP Business Object
- Interface & Consumption CDS Views
- Determination for default values
- RAP Actions (Approve / Reject)
- OData V4 service exposure
- Fiori Elements List Report (Preview)
- Cloud-compliant ABAP (ABAP Cloud)

---

## Technology Stack
- SAP BTP ABAP Environment (Trial)
- ABAP Cloud
- RAP (RESTful ABAP Programming Model)
- OData V4
- Fiori Elements

---

## Architecture Overview
- **Database Table**: ZEMP_LEAVE
- **Interface View**: Z_I_EMP_LEAVE
- **Consumption View**: Z_C_EMP_LEAVE
- **Behavior Definition**: Managed behavior for business logic
- **Behavior Implementation**: Determinations and actions
- **Metadata Extension**: UI annotations
- **Service Binding**: OData V4 – UI

rap-employee-leave-management/
│

├── cds/

│   ├── zemp_leave_table.abap
│   ├── z_i_emp_leave.abap
│   ├── z_c_emp_leave.abap
│   └── z_c_emp_leave_ui.abap
│
├── behavior/
│   ├── z_i_emp_leave.behavior
│   └── zbp_i_emp_leave.abap
│
├── service/
│   └── zui_emp_leave.srvd.abap
│
├── data/
│   └── zcl_insert_emp_leave.abap
│
└── README.md


---

## Business Logic
### Determination
- Sets default values:
  - Status = NEW
  - Created By
  - Created On
  - Number of Leave Days

### Actions
- Approve → Updates status to APPROVED
- Reject → Updates status to REJECTED

---

## Trial Environment Limitations
Due to SAP BTP ABAP Trial restrictions:
- UI Create and Action buttons are not displayed in Fiori Elements
- SQL Console and REPORT programs are unavailable
- External tools (Postman Basic Auth) are blocked

### Workaround
- Data insertion tested using a **Runnable ABAP Class** (`IF_OO_ADT_CLASSRUN`)
- Data verified via Fiori Elements Preview

---

## How to Test
1. Run the runnable ABAP class to insert test data
2. Open Service Binding → Preview
3. Click **Go** to view data

---

## Author
**Aayush Bairagi**

SAP ABAP | RAP | ABAP Cloud
