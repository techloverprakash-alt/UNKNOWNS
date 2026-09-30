# ServiceNow Standard Laptop Procurement Automation

An end-to-end IT Service Management (ITSM) automation project implemented on **ServiceNow** using **Flow Designer** to streamline standard laptop procurement and fulfillment workflows.

---

## 📌 Project Overview

Manual IT procurement workflows often suffer from delayed handoffs, inconsistent task assignments, and slow turnaround times. This project addresses those bottlenecks by:
1. Building an automated trigger and action workflow via **ServiceNow Flow Designer**.
2. Linking the automated flow to the **Standard Laptop** catalog item under Maintain Items.
3. Automatically generating and routing a fulfillment task (`sc_task`) directly to the **Hardware** assignment group with pre-configured parameters upon ordering.

---

## 🛠️ Technology & Tools Used

- **Platform:** ServiceNow (Now Platform)
- **Core Capabilities:** Flow Designer, Service Catalog, Service Request Management (REQ &rarr; RITM &rarr; SCTASK)
- **Artifacts:** Process Engine Flows, Catalog Items, Catalog Tasks

---

## 🚀 Step-by-Step Implementation

### Step 1: Flow Creation (`Standard laptop task`)
- Built in **Flow Designer** running as **System User** in the **Global** application scope.
- **Trigger:** Service Catalog.
- **Action:** Create Catalog Task (`sc_task`).
  - Request item: `Requested Item Record` (Data pill).
  - Short description: `Laptop need to Configured`.
  - Description: `Laptop need to Configured`.
  - Assignment group: `Hardware`.
  - Approval: `Approved`.
- Flow was tested and activated.

### Step 2: Catalog Item Integration
- Navigated to **Maintain Items** &rarr; `Standard Laptop`.
- In the **Process Engine** configuration, replaced legacy workflows/plans with the flow `Standard laptop task`.

### Step 3: End-to-End Validation
- Ordered a Standard Laptop through the **Service Catalog** (`Hardware` category).
- Approved the generated Request record (`REQ`).
- Inspected the child Requested Item (`RITM`) and verified that the **Catalog Task** (`SCTASK`) was generated and assigned to the **Hardware** group with the specified fields populated.

---

## 📸 Milestone Evidence & Visual Walkthrough

### Module 1: Flow Designer Setup & Action Configuration
| Flow Setup & Trigger | Action Field Mapping |
| :---: | :---: |
| ![Flow Setup](milestone%201%20-%20flow.jpeg) | ![Action Configuration](milestone%201%20-%20flow%20(1).jpeg) |

---

### Module 2: Maintain Items & Process Engine Mapping
| Maintain Items Record | Flow Mapping |
| :---: | :---: |
| ![Maintain Items](milestone%202%20-%20flow%20assignment.jpeg) | ![Flow Assignment](milestone%202%20-%20flow%20assignment%20(2).jpeg) |

---

### Module 3: Service Catalog Ordering & Fulfillment Task Verification
| Catalog Submission | Automated SCTASK Generation |
| :---: | :---: |
| ![Service Catalog Order](milestone%203%20-%20service%20catalog.jpeg) | ![SCTASK Verification](milestone%203%20-%20service%20catalog%20(1).jpeg) |

---

## 📈 Business Impact

> *"By automating the standard laptop procurement process with ServiceNow's Flow Designer, the project effectively addresses inefficiencies and reduces manual overhead. This streamlined workflow ensures timely configuration of laptops, minimizes user wait times, and enhances overall productivity within the IT department. The implementation of this automated solution not only optimizes resource allocation but also significantly improves the user experience by providing a seamless and efficient procurement process."*

---

## 📁 Repository Structure

```text
├── README.md                              # Project overview, workflow steps, and visual summary
├── project documentation.md               # In-depth technical documentation & architecture
├── milestone 1 - flow.jpeg                # Screenshot: Flow Designer trigger configuration
├── milestone 1 - flow (1).jpeg            # Screenshot: Flow Designer task action parameters
├── milestone 2 - flow assignment.jpeg     # Screenshot: Maintain Items catalog record
├── milestone 2 - flow assignment (2).jpeg # Screenshot: Process engine flow association
├── milestone 3 - service catalog.jpeg     # Screenshot: Hardware catalog item ordering
└── milestone 3 - service catalog (1).jpeg # Screenshot: Generated SCTASK verification
```
