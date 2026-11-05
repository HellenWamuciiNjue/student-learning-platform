# Student Learning and Revision Platform
### Complete Project Manual & Engineering Reference Guide

Welcome to the central repository for the Student Learning and Revision Platform. This document serves as the absolute source of truth for our architecture, integration protocols, design standards, and workflows. 

**Read this manual thoroughly before writing code or opening a Pull Request.**

---

## 📅 Hard Milestone Deadline
*   **Final Integration & Internal Review Cutoff:** **November 10, 2026 at 6:00 PM**
*   **Team Progress Meeting:** **November 10, 2026 (7pm)**
*   All individual feature branches must be submitted via Pull Requests by 6:00 PM to freeze the code for our review and discussion.

---

## 👥 1. Team Directory & Role Responsibilities

| No. | Full Name | Team Role | Core System Deliverables |
| :--- | :--- | :--- | :--- |
| **1** | Hellen Wamucii Njue | Team Leader & Integrator | Repository management, system architecture layout, code reviews, and pulling branches into `main`. |
| **2** | Yugi Michael | Homepage Developer | `index.html` structure, hero banners, site orientation layout, and core navigation link maps. |
| **3** | Florence Gitau | Subjects Page Developer | `subjects.html` layout, grid matrices for course selection, and subtopic list components. |
| **4** | Stephen Githaiga Muriu | Notes Developer | `notes.html` text layouts, print-friendly stylesheets, and scroll-to-topic elements. |
| **5** | Kelvin Shema | Quiz Interface Developer | `quizzes.html` list view and `take-quiz.html` layout (question cards, dynamic choice containers). |
| **6** | Aladinee Sawe | Scoring/Results Developer | `results.html` layouts, scoring visualizers, and conditional feedback elements. |
| **7** | Chukwuma Nicodemus Ndukwu | UI/CSS Developer | Global design token definition, typography, component styling presets, and responsiveness rules. |
| **8** | Lynnet Njoki | JavaScript & Data Developer | Core quiz logic engines, handling score computations, arrays, and persistent states. |
| **9** | Nicodemus Muriuki | Educational Content Officer | Copywriting notes content, sourcing factual test questions, and validating curriculum accuracy. |
| **10** | Isaac Okach | Tester & Documentation | Link checking, boundary condition logic verification, manual test planning, and log maintenance. |

---

## 🤝 2. Mandatory Synchronization Contracts (Names & Classes)

To prevent code from breaking when merged into `main`, specific developers must coordinate before writing code. If you do not follow these naming conventions, your branch will be rejected during review.

### 🌐 A. Global UI Framework Alignment (Chukwuma, Yugi, Florence, Stephen, Kelvin, Aladinee)
**Chukwuma Nicodemus (CSS Developer)** must publish standard classes in `css/style.css`. Every page developer must use these exact classes to keep layouts unified:
*   **Page Container wrappers:** Layout blocks must wrap inside `.app-container`.
*   **Navigation elements:** Main links must utilize `.nav-bar`, `.nav-item`, and `.nav-brand`.
*   **Interactive Controls:** Every action item must inherit standard layout rules from `.btn`, `.btn-primary`, or `.btn-secondary`.
*   **Display Units:** Information sections must reside inside `.card`, `.card-header`, and `.card-body`.

### 🧠 B. Core Interactive Component ID Mapping (Kelvin, Aladinee, Lynnet)
**Kelvin (Quiz UI)**, **Aladinee (Results UI)**, and **Lynnet (JavaScript Engine)** must link their HTML structure and script behaviors using these exact structural IDs:

#### 📝 In `take-quiz.html` (Kelvin & Lynnet Alignment):
*   **Question Text Area:** The text container element must be strictly defined as `<h3 id="question-text"></h3>`.
*   **Choice Options Container:** The wrapper block for dynamic answer buttons must be defined as `<div id="choices-container"></div>`.
*   **Pagination Elements:** The next-step control button must be set as `<button id="next-question-btn"></button>`.
*   **Submission Action Elements:** The absolute form submission trigger button must be set as `<button id="submit-quiz-btn"></button>`.

#### 📊 In `results.html` (Aladinee & Lynnet Alignment):
*   **User Raw Score Counter:** The final correct answer counter must be styled as `<span id="user-score"></span>`.
*   **Total Item Metric:** The overall test size metric container must be defined as `<span id="total-questions"></span>`.
*   **Automated Review Panel:** The area handling customized study hints and feedback text must look like `<div id="feedback-suggestions"></div>`.

---

## 📂 3. Baseline Engineering Workspace Architecture

Keep all file positions and system names organized according to this structural layout map:

```text
student-learning-platform/
├── css/
│   └── style.css            # Managed by Chukwuma: Central styling patterns
├── data/
│   └── questions.js         # Managed by Nicodemus M. & Lynnet: Structured question arrays
├── js/
│   └── script.js            # Managed by Lynnet: Application behavior and score logic engines
├── index.html               # Managed by Yugi: Primary application portal
├── subjects.html            # Managed by Florence: Topic catalogs and course streams
├── notes.html               # Managed by Stephen: Text presentations of study materials
├── quizzes.html             # Managed by Kelvin: Practice module directories
├── take-quiz.html           # Managed by Kelvin: Interactive text card assessment arrays
├── results.html             # Managed by Aladinee: Performance logs and evaluation loops
├── .gitignore               # Excludes tracking of editor files (.vscode/), logs, and OS caches
├── LICENSE                  # Open source repository distribution license
└── README.md                # This document
```

---

## 🔧 4. Step-by-Step Developer Git Manual

Follow these exact local terminal steps inside your Git Bash window to manage your updates safely:

### Step 1: Initial Setup
Clone the baseline files down and move into the application root:
```bash
git clone https://github.com
cd student-learning-platform
```

### Step 2: Open in VS Code
Launch your code workspace to edit files visually:
```bash
code .
```

### Step 3: Branching (Mandatory)
Before changing any code, break out into your dedicated feature branch. Replace `your-role` with your specific duty assignment (e.g., `feature-homepage` or `feature-notes`):
```bash
git checkout -b feature-your-role
```

### Step 4: Staging and Saving Work Locally
Save your localized updates to your tracking index regularly:
```bash
git add .
git commit -m "Provide a clear description of the specific features added"
```

### Step 5: Pushing to Remote Repository
Push your completed development branch up to the remote repository:
```bash
git push origin feature-your-role
```

---

## ❓ 5. Frequently Asked Engineering Questions (FAQ)

#### Q: Can I push code directly onto the `main` branch?
**No.** Direct pushes to the `main` branch are restricted. If you bypass this or run destructive push overrides, you run the risk of breaking our baseline tracking files. All updates must come in via Pull Requests.

#### Q: How do I handle site navigation across different pages?
All global links must use straight root paths. **Yugi Michael** will implement a uniform navbar template that everyone must copy into the top section of their respective HTML sheets:
*   Home Link: `index.html`
*   Subjects Link: `subjects.html`
*   Notes Link: `notes.html`
*   Quizzes Directory Link: `quizzes.html`

#### Q: Where should the quiz results data be stored?
Since this is a client-side architecture without an external database, the JavaScript engines will read and write active test sessions directly into the browser's native **`localStorage`**. 
*   **Lynnet** will write scores to storage upon question validation.
*   **Aladinee** will fetch those exact metrics from storage on load to populate the summary displays inside `results.html`.

#### Q: What happens if I encounter code conflicts during my branch push?
If a notification displays that your branch is out of sync, update your local branch history against the master branch using these terminal command flags:
```bash
git checkout main
git pull origin main
git checkout feature-your-role
git merge main
```
Fix any syntax overlapping markers inside your text editor workspace, re-stage files, save your commit, and push your branch up again.
