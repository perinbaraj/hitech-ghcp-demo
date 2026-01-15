## 🛠️ Mapping PDLC Stages to This Workshop

| PDLC Stage         | Workshop Artifact                | How GitHub Copilot Helps               |
|--------------------|----------------------------------|----------------------------------------|
| Ideation & Planning| Voting feature selection         | Generate feature lists, acceptance criteria via Copilot prompts |
| Design             | index.html, style.css            | Scaffold HTML structure, suggest UI layouts/styles              |
| Implementation     | script.js, chart.js              | Write core logic, validation, state mgmt. via Copilot completion |
| Testing            | Manual test steps in README      | Autogenerate test cases/scripts with Copilot suggestions        |
| Deployment         | (Add: GitHub Actions Workflow)   | Copilot writes YAML for CI/CD; deploy to GitHub Pages           |
| Maintenance        | Update chart, handle ties        | Suggest refactorings, document new features with Copilot        |

### Example GHCP-Enabled Use Cases

- **Copilot Chat**: “What’s a good way to visualize ties in vote results?” → Suggests tie-detection code and design.
- **Copilot Pull Requests**: Drafts and reviews code for new insights export feature.
- **Copilot Plus with Actions**: Autocompletes a deploy-to-Pages workflow.
---

## 📋 PDLC Stage Prompts for Feature Voting App

### Ideation
- "Write user stories for a feature voting app."
- "Suggest 5 new features for voting."

### Design
- "Generate HTML for a responsive ballot interface."
- "Style the pie chart for color-blind accessibility."

### Implementation
- "Create a JavaScript function to store votes in localStorage."
- "Detect and visually indicate tied vote results."

### Testing
- "Write a test that simulates 100 votes and checks results calculation."

### Deployment
- "Write a GitHub Actions workflow to build and deploy this app to GitHub Pages."
