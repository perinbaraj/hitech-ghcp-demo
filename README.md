# Feature Vote & Insights - GitHub Copilot Workshop

A hands-on workshop demonstrating how to build a complete web application using GitHub Copilot. Participants will create an interactive voting system with real-time insights and talking points.

## 🎯 Workshop Objectives

By the end of this workshop, you will:
- Build a fully functional voting application from scratch
- Learn effective GitHub Copilot prompting techniques
- Understand how to break down complex features into simple prompts
- Generate production-ready HTML, CSS, and JavaScript using AI assistance

## 📋 Prerequisites

- Visual Studio Code installed
- GitHub Copilot extension enabled
- Basic understanding of HTML, CSS, and JavaScript
- A web browser for testing

## 🏗️ Project Structure

```
.
├── index.html          # Main HTML structure
├── style.css           # Styling and theme
├── script.js           # Interactive functionality
└── README.md           # This file
```

## 🚀 Step-by-Step Guide

### Part 1: Setting Up the HTML Structure (index.html)

#### Step 1.1: Create the Basic HTML Template

**Prompt for Copilot:**
```
Create a basic HTML5 template with proper meta tags, viewport settings, and a title "Feature Vote & Insights – Hi‑Tech". Link a style.css file.
```

**Expected Output in `index.html`:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Feature Vote & Insights – Hi‑Tech</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
</body>
</html>
```

#### Step 1.2: Add the Hero Section

**Prompt for Copilot:**
```
Create a clean, centered hero section with a heading "Feature Vote & Insights", a subheadline "Prioritize your roadmap with quick votes and instant talking points.", and a CTA button "Start Voting" with id="scrollToPoll".
```

**Expected Output in `index.html`:**
```html
<header class="hero">
  <h1>Feature Vote & Insights</h1>
  <p class="sub">Prioritize your roadmap with quick votes and instant talking points.</p>
  <button id="scrollToPoll" class="btn">Start Voting</button>
</header>
```

#### Step 1.3: Create the Voting Poll Section

**Prompt for Copilot:**
```
Create a poll section with id="poll" containing a form with id="voteForm". Add a heading "Vote for the Next Feature" and a radio list with five features: Network Optimization, Billing Insights, App Crash Reporting, Self‑Service Onboarding, and Visual Search Personalization. Add Submit and Clear buttons.
```

**Expected Output in `index.html`:**
```html
<main class="container">
  <section id="poll" class="card">
    <h2>Vote for the Next Feature</h2>
    <p class="muted">Select the feature that delivers the biggest impact.</p>

    <form id="voteForm">
      <label class="option"><input type="radio" name="feature" value="Network Optimization" /> Network Optimization</label>
      <label class="option"><input type="radio" name="feature" value="Billing Insights" /> Billing Insights</label>
      <label class="option"><input type="radio" name="feature" value="App Crash Reporting" /> App Crash Reporting</label>
      <label class="option"><input type="radio" name="feature" value="Self‑Service Onboarding" /> Self‑Service Onboarding</label>
      <label class="option"><input type="radio" name="feature" value="Visual Search Personalization" /> Visual Search Personalization</label>

      <div class="actions">
        <button type="submit" class="btn">Submit Vote</button>
        <button type="button" id="clearVotes" class="btn ghost">Clear Votes</button>
      </div>
    </form>
  </section>
</main>
```

#### Step 1.4: Add Results and Insights Sections

**Prompt for Copilot:**
```
Create a two-column grid section with two cards: one for "Live Results" with an empty ul id="results", and one for "Instant Talking Points" with a div id="insights".
```

**Expected Output in `index.html`:**
```html
<section class="grid">
  <div class="card">
    <h3>Live Results</h3>
    <ul id="results" class="list"></ul>
  </div>
  <div class="card">
    <h3>Instant Talking Points</h3>
    <div id="insights" class="insights"></div>
  </div>
</section>
```

#### Step 1.5: Add Footer and Script Link

**Prompt for Copilot:**
```
Add a footer with copyright text "© 2026 | Hi‑Tech demo | Built with GitHub Copilot" and link a script.js file at the end of the body.
```

---

### Part 2: Styling the Application (style.css)

#### Step 2.1: Set Up CSS Variables and Reset

**Prompt for Copilot:**
```
Create CSS custom properties for a dark theme with colors for background (#0e1117), text (#e6edf3), muted text (#9da5b4), card background (#161b22), primary blue (#2f81f7), and border (#1f2430). Add a box-sizing reset and basic body styles.
```

**Expected Output in `style.css`:**
```css
:root {
  --bg: #0e1117; --ink: #e6edf3; --muted: #9da5b4;
  --card: #161b22; --primary: #2f81f7; --border: #1f2430;
}

* { box-sizing: border-box; }
body { margin: 0; font-family: system-ui, Segoe UI, Roboto, sans-serif; background: var(--bg); color: var(--ink); }
```

#### Step 2.2: Style the Hero Section

**Prompt for Copilot:**
```
Style the .hero class with centered text and padding. Style .hero .sub with muted color. Create button styles with primary background, white text, padding, border-radius, and a ghost variant with transparent background and border.
```

#### Step 2.3: Create Card and Layout Styles

**Prompt for Copilot:**
```
Create styles for .container (max-width 1100px, centered), .card (dark background with border and padding), .grid (two-column grid with gap), and .list (no bullets, bottom borders on items). Add responsive breakpoint for mobile.
```

#### Step 2.4: Style Form Elements

**Prompt for Copilot:**
```
Style .option labels as block elements with padding, border-radius, dark background, and border. Style input spacing and .actions as a flex row with gap.
```

---

### Part 3: Adding Interactivity (script.js)

#### Step 3.1: Implement Smooth Scrolling

**Prompt for Copilot:**
```
Add smooth scroll functionality from the hero CTA button (id="scrollToPoll") to the poll section (id="poll") using scrollIntoView with smooth behavior.
```

**Expected Output in `script.js`:**
```javascript
document.getElementById('scrollToPoll')?.addEventListener('click', () => {
  document.getElementById('poll')?.scrollIntoView({ behavior: 'smooth', block: 'start' });
});
```

#### Step 3.2: Create Vote Storage and Form Handler

**Prompt for Copilot:**
```
Create an in-memory Map called votes to store vote counts. Handle form submission for id="voteForm": read the selected feature from FormData, increment its count in the Map, then call renderResults() and renderInsights() functions. Show an alert if no feature is selected.
```

**Expected Output in `script.js`:**
```javascript
const votes = new Map();

document.getElementById('voteForm')?.addEventListener('submit', (e) => {
  e.preventDefault();
  const choice = new FormData(e.target).get('feature');
  if (!choice) return alert('Please select a feature to vote for.');

  votes.set(choice, (votes.get(choice) || 0) + 1);
  renderResults();
  renderInsights();
});
```

#### Step 3.3: Implement Clear Votes Functionality

**Prompt for Copilot:**
```
Add click handler for id="clearVotes" button that clears the votes Map and refreshes both results and insights displays.
```

#### Step 3.4: Create Results Rendering Function

**Prompt for Copilot:**
```
Create a renderResults function that displays votes in id="results" as a sorted list (highest votes first), showing "feature — X vote(s)". If no votes exist, show a placeholder message.
```

**Expected Output in `script.js`:**
```javascript
function renderResults() {
  const ul = document.getElementById('results');
  if (!ul) return;
  ul.innerHTML = '';
  const ordered = [...votes.entries()].sort((a, b) => b[1] - a[1]);
  ordered.forEach(([feature, count]) => {
    const li = document.createElement('li');
    li.textContent = `${feature} — ${count} vote${count > 1 ? 's' : ''}`;
    ul.appendChild(li);
  });
  if (ordered.length === 0) {
    ul.innerHTML = '<li>No votes yet. Submit your first vote above.</li>';
  }
}
```

#### Step 3.5: Generate Dynamic Talking Points

**Prompt for Copilot:**
```
Create renderInsights and talkingPoints functions that generate business insights based on the leading feature:
- Network Optimization → mention uptime & field service efficiency
- Billing Insights → mention churn mitigation & CX trust
- App Crash Reporting → mention defect prevention & quality gates
- Self‑Service Onboarding → mention cycle time & provisioning automation
- Visual Search Personalization → mention engagement & conversion
```

**Expected Output in `script.js`:**
```javascript
function renderInsights() {
  const insights = document.getElementById('insights');
  if (!insights) return;

  const ordered = [...votes.entries()].sort((a, b) => b[1] - a[1]);
  if (ordered.length === 0) {
    insights.textContent = 'After voting, you will see instant talking points here.';
    return;
  }

  const [topFeature, topCount] = ordered[0];
  insights.innerHTML = talkingPoints(topFeature, topCount);
}

function talkingPoints(feature, count) {
  const base = `<strong>Top choice:</strong> ${feature} (${count})<br/>`;
  switch (feature) {
    case 'Network Optimization':
      return base + `• Reduce downtime, fewer disconnects → stronger NPS<br/>
                     • Data-driven dispatch → better field service ROI`;
    case 'Billing Insights':
      return base + `• Transparent bills → lower churn risk<br/>
                     • Proactive outreach → higher CX trust`;
    case 'App Crash Reporting':
      return base + `• Fewer defects via crash analytics & quality gates<br/>
                     • Faster MTTR → protected brand experience`;
    case 'Self‑Service Onboarding':
      return base + `• Shorter cycle time via automated provisioning<br/>
                     • Scalable onboarding for partners & customers`;
    case 'Visual Search Personalization':
      return base + `• Tailored experiences → higher engagement<br/>
                     • Better conversion in digital storefronts`;
    default:
      return base + '• Align teams → deliver measurable impact faster';
  }
}
```

---

## ✅ Testing Your Application

1. Open `index.html` in Live Server or a local web server
2. Click "Start Voting" - should scroll smoothly to the poll
3. Select a feature and submit - results should appear
4. Vote multiple times - counts should increment
5. Check talking points update based on the leading feature
6. Click "Clear Votes" - everything should reset

---

## 🎨 Optional Exercise: Pie Chart Visualization

**Challenge:** Create a new landing page that displays voting results as a pie chart showing percentage distribution.

### Requirements:
- Create a new file `chart.html`
- Use Chart.js or Canvas API to render a pie chart
- Calculate percentages for each feature
- Add a link from the main page to the chart view
- Display vote counts and percentages in the legend

### Suggested Prompts:

**Prompt 1 - HTML Setup:**
```
Create chart.html with a canvas element for a pie chart, include Chart.js from CDN, and add a back button to return to index.html
```

**Prompt 2 - Data Preparation:**
```
Create a function in script.js that exports vote data in a format suitable for Chart.js pie chart with labels, data values, and percentage calculations
```

**Prompt 3 - Chart Rendering:**
```
Use Chart.js to create a pie chart displaying feature votes with different colors for each option, showing percentages in tooltips and legend
```

**Prompt 4 - Styling:**
```
Style the chart page to match the dark theme from style.css with responsive layout for mobile devices
```

### Bonus Features:
- Add color coding that matches the feature categories
- Implement real-time chart updates when votes change
- Add animation when the chart first loads
- Display the total number of votes cast

---

## 🧠 GitHub Copilot Tips

### Effective Prompting Strategies:

1. **Be Specific**: Include exact IDs, class names, and element types
2. **Context Matters**: Mention related features (e.g., "that works with the votes Map")
3. **Break It Down**: Complex features work better as multiple smaller prompts
4. **Use Examples**: "Create a function like renderResults but for..."
5. **Iterate**: If the first result isn't perfect, refine your prompt

### Common Copilot Commands:

- **Inline Suggestions**: Start typing and wait for suggestions
- **Comment Prompts**: Write `//` followed by your request
- **Chat Panel**: Use for explanations and refactoring
- **Multi-line Edits**: Select code and ask Copilot to modify it

---

## 📚 Learning Outcomes

After completing this workshop, you should understand:

- ✅ How to structure prompts for different file types (HTML, CSS, JS)
- ✅ Breaking down features into manageable AI-assisted tasks
- ✅ Working with DOM manipulation and event handling
- ✅ Creating responsive layouts with CSS Grid and Flexbox
- ✅ Managing state with JavaScript Maps
- ✅ Building accessible forms and interactive UI components

---

## 🔗 Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Prompt Engineering Guide](https://github.com/microsoft/prompt-engineering)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Chart.js Documentation](https://www.chartjs.org/) (for optional exercise)

---

## 🤝 Contributing

This workshop is designed for learning. Feel free to:
- Experiment with different prompt styles
- Add new features using Copilot
- Share your insights with the group
- Customize the styling and functionality

---

## 📝 Notes

- All code should be generated through GitHub Copilot prompts
- Take time to understand the generated code
- Don't hesitate to ask Copilot to explain or refactor
- The goal is learning effective AI pair programming, not just completing the task

---

**Happy Coding with GitHub Copilot! 🚀**
