# 🏛️ University Portal System

A comprehensive, scalable, and modular Django-based academic and administrative portal designed to manage modern university operations. This system integrates distinct modular architectures for admissions, academics, finance, core platform utilities, and an integrated smart AI assistant ecosystem.

---

## 🏗️ System Architecture & App Breakdown

The project follows a clean, decoupled modular approach split into specialized domain business logic layer services (`services.py`), data exposure selectors (`selectors.py`), and a split presentation architecture.

### 🧩 System Domain Applications
* **`apps/accounts`**: Custom user identity management, multi-role authentication frameworks (Admin, Assistant, Students, Faculty), and profile synchronization.
* **`apps/admissions`**: Registration, verification pipeline tracking, enrollment allocations, and application processing.
* **`apps/academics`**: Course scheduling, curriculum design engines, semester blueprint planners, tracking matrices, and grading metrics.
* **`apps/finance`**: Fee ledger structures, transaction processing, invoice generation, status validations, and tracking logs.
* **`apps/content`**: Dynamic campus news registries, global announcement configurations, and home slideshow control arrays.
* **`apps/core`**: Base exceptions, dynamic pagination profiles, customized permission configurations, and overarching site signals.
* **`apps/portal`**: The primary private user interface layer, providing dashboard templates, attendance counters, dynamic rings, billing progress charts, and operational views.
* **`apps/website`**: The public-facing institutional portal offering informational pathways, admissions information sheets, program lists, contact routes, and public widget scripts.
* **`apps/assistant`**: An advanced RAG (Retrieval-Augmented Generation) document parsing system equipped with asynchronous vectors, processing state recovery scripts, and AI contextual panels.

---

## 🚀 Key Architectural Features

* **Layered Architecture Patterns**: Logic is structurally divided into explicit write commands (`services.py`) and read query abstractions (`selectors.py`) instead of bulky model methods.
* **Smart RAG AI Assistant**: Seamless LLM ingestion system targeting local administrative documents (PDFs, DOCX, TXT registries) to answer context-aware inquiries across user portal modules.
* **Responsive Visual Dashboards**: Configured SVG indicators, dynamic financial meters, and interactive analytical rings tracking critical metrics locally.
* **Production-Ready Configuration Blueprint**: Segmented multi-environment settings (`base.py`, `dev.py`, `prod.py`, `test.py`) with customizable Docker runtime configurations.

---

## 🛠️ Local Installation & Development Setup

### Prerequisites
* Python 3.10+
* Git
* Docker & Docker Compose (Optional, for localized containerized setups)

### Step 1: Clone and Prepare Project Workspace
```bash
git clone https://github.com
cd university-portal-system
```

### Step 2: Configure Environment Variables
Create a local `.env` configuration file in the project directory using the provided sample:
bash
cp .env.example .env
*Configure your secret keys, local target database connections, vector dimensions, and LLM API endpoints inside the `.env` file.*

Step 3: Local Setup Without Docker

1. Build Virtual Runtime Context:**
   bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   

2. Install Package Matrices:**
   bash
   pip install -r requirements/dev.txt
   

3. Synchronize System Databases:**
   bash
   python manage.py migrate
   

4. Seed System Demo Schemas:**
   bash
   python manage.py bootstrap_admin    # Generates initial administration accounts
   python manage.py seed_academics     # Seeds courses, classes, and schedules
   python manage.py seed_admissions    # Seeds demo student profiles
   python manage.py seed_content       # Seeds dynamic news data
   python manage.py seed_portal_demo   # Synchronizes systemic portal views
  

5. Fire Up the Engine:**
   bash
   python manage.py runserver

   Access the local portal directly via: `http://127.0.0`

Step 4: Containerized Setup via Docker Compose
To instantly orchestrate your application stack along with isolated backend databases, execute:
bash
docker compose up --build

🧪 Quality Assurance & Test Verification
The portal is fully verified across custom model properties, transaction validation modules, presentation layers, and internal service calls.

To run the unified project test suite locally, run:
bash
python manage.py test --settings=config.settings.test


---

## 🗂️ Project Directory Topology
text
university-portal-system/
├── apps/               # Business logic core components divided into micro-domains
├── config/             # Configuration cluster (ASGI, WSGI, split Django environments)
├── docker/             # Isolated server and database orchestration directives
├── media/              # Document repositories, campus flyers, and dynamic asset pools
├── requirements/       # Fragmented environment dependency maps
├── static/             # Compilation target for site-wide stylesheets and Javascript assets
├── templates/          # Base administrative extension definitions
├── manage.py           # CLI operational entry point
└── render.yaml         # Cloud deployment specifications
