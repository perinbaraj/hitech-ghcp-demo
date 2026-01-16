# Feature Vote & Insights - GitHub Copilot Workshop

## https://github.com/Hi-Tech-Training-PSL

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
├── chart.html          # Pie chart visualization (Optional Exercise)
├── chart.js            # Chart rendering logic (Optional Exercise)
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

## 🎨 Optional Exercise 1: Pie Chart Visualization

**Challenge:** Create a new landing page that displays voting results as a pie chart showing percentage distribution.

### Part A: Adding the View Chart Button

#### Step A.1: Add Navigation Link in Results Card

**Prompt for Copilot:**
```
In index.html, add a "View Chart" button with a 📊 emoji below the results list (ul#results) inside the Live Results card. Style it as a primary button with inline-block display and margin-top.
```

**Expected Output in `index.html`:**
```html
<div class="card">
  <h3>Live Results</h3>
  <ul id="results" class="list"></ul>
  <a href="chart.html" class="btn" style="margin-top: 1rem; display: inline-block; text-decoration: none;">📊 View Chart</a>
</div>
```

### Part B: Creating the Chart Page Structure

#### Step B.1: Create chart.html with Chart.js CDN

**Prompt for Copilot:**
```
Create chart.html with the same dark theme as index.html. Include Chart.js CDN (version 4.4.1), a canvas element with id="voteChart", a back button linking to index.html, and a div with id="chartStats" for displaying statistics. Link style.css and a new chart.js file.
```

**Expected Output in `chart.html`:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Vote Results Chart – Hi‑Tech</title>
  <link rel="stylesheet" href="style.css" />
  <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
</head>
<body>
  <header class="hero container">
    <h1>Voting Results</h1>
    <p class="sub">Percentage distribution of feature votes</p>
    <a href="index.html" class="btn back-btn">← Back to Voting</a>
  </header>

  <main class="container">
    <section class="card chart-container">
      <h2>Vote Distribution</h2>
      <canvas id="voteChart"></canvas>
      <div id="chartStats"></div>
    </section>
  </main>

  <footer class="footer container">
    <p>© 2026 | Hi‑Tech demo | Built with GitHub Copilot</p>
  </footer>

  <script src="chart.js"></script>
</body>
</html>
```

#### Step B.2: Add Chart-Specific Styles

**Prompt for Copilot:**
```
In chart.html, add a <style> block with styles for .chart-container (max-width 600px, centered, padding), .back-btn (inline-block with margin), canvas (max-height 400px), and #chartStats (white text color with important flag to override defaults).
```

**Expected Output in `chart.html`:**
```html
<style>
  .chart-container {
    max-width: 600px;
    margin: 2rem auto;
    padding: 2rem;
  }
  .back-btn {
    display: inline-block;
    margin: 1rem 0;
    text-decoration: none;
  }
  canvas {
    max-height: 400px;
  }
  #chartStats {
    color: white !important;
  }
  #chartStats p {
    color: white !important;
  }
  #chartStats a {
    color: var(--primary);
  }
</style>
```

### Part C: Data Export and localStorage Integration

#### Step C.1: Create Data Export Function

**Prompt for Copilot:**
```
In script.js, create an exportChartData function that converts the votes Map into Chart.js format with labels array, data values array, percentages calculation, totalVotes count, and a backgroundColor array with 5 distinct colors (#2f81f7 blue, #3fb950 green, #d29922 yellow, #f85149 red, #a371f7 purple). Return an object with all these properties.
```

**Expected Output in `script.js`:**
```javascript
function exportChartData() {
  const labels = [];
  const data = [];
  const totalVotes = [...votes.values()].reduce((sum, count) => sum + count, 0);
  
  // Convert Map to arrays for Chart.js
  [...votes.entries()].forEach(([feature, count]) => {
    labels.push(feature);
    data.push(count);
  });

  // Calculate percentages
  const percentages = data.map(count => 
    totalVotes > 0 ? ((count / totalVotes) * 100).toFixed(1) : 0
  );

  return {
    labels,
    data,
    percentages,
    totalVotes,
    backgroundColor: [
      '#2f81f7', // Blue
      '#3fb950', // Green
      '#d29922', // Yellow
      '#f85149', // Red
      '#a371f7'  // Purple
    ]
  };
}
```

#### Step C.2: Save Data to localStorage

**Prompt for Copilot:**
```
In script.js, create a saveVotesToStorage function that calls exportChartData and saves the result to localStorage with key 'voteData' as JSON. Call this function after renderResults and renderInsights in both submit and clear handlers.
```

**Expected Output in `script.js`:**
```javascript
function saveVotesToStorage() {
  const chartData = exportChartData();
  localStorage.setItem('voteData', JSON.stringify(chartData));
}

// Update existing handlers to include:
document.getElementById('voteForm')?.addEventListener('submit', (e) => {
  e.preventDefault();
  const choice = new FormData(e.target).get('feature');
  if (!choice) return alert('Please select a feature to vote for.');

  votes.set(choice, (votes.get(choice) || 0) + 1);
  renderResults();
  renderInsights();
  saveVotesToStorage(); // Add this line
});

document.getElementById('clearVotes')?.addEventListener('click', () => {
  votes.clear();
  renderResults();
  renderInsights();
  saveVotesToStorage(); // Add this line
});
```

### Part D: Rendering the Pie Chart

#### Step D.1: Load Data and Create Chart

**Prompt for Copilot:**
```
In chart.js, load voteData from localStorage and parse it. Create a Chart.js pie chart on canvas#voteChart with the loaded data, custom legend showing vote counts and percentages, white text colors for dark theme, tooltips with vote counts and percentages, and border styling matching the theme (#1f2430).
```

**Expected Output in `chart.js`:**
```javascript
// Load vote data from localStorage
const storedData = localStorage.getItem('voteData');
let chartData;

if (storedData) {
  chartData = JSON.parse(storedData);
} else {
  // Default empty state
  chartData = {
    labels: [],
    data: [],
    percentages: [],
    totalVotes: 0,
    backgroundColor: []
  };
}

// Get canvas element
const ctx = document.getElementById('voteChart');

if (ctx && chartData.totalVotes > 0) {
  // Create pie chart
  new Chart(ctx, {
    type: 'pie',
    data: {
      labels: chartData.labels,
      datasets: [{
        label: 'Votes',
        data: chartData.data,
        backgroundColor: chartData.backgroundColor,
        borderColor: '#1f2430',
        borderWidth: 2
      }]
    },
    options: {
      responsive: true,
      maintainAspectRatio: true,
      plugins: {
        legend: {
          position: 'bottom',
          labels: {
            color: '#ffffff',
            padding: 15,
            font: {
              size: 13
            },
            generateLabels: function(chart) {
              const data = chart.data;
              if (data.labels.length && data.datasets.length) {
                return data.labels.map((label, i) => {
                  const value = data.datasets[0].data[i];
                  const percentage = chartData.percentages[i];
                  return {
                    text: `${label}: ${value} vote${value !== 1 ? 's' : ''} (${percentage}%)`,
                    fillStyle: data.datasets[0].backgroundColor[i],
                    fontColor: '#ffffff',
                    hidden: false,
                    index: i
                  };
                });
              }
              return [];
            }
          }
        },
        tooltip: {
          backgroundColor: '#161b22',
          titleColor: '#e6edf3',
          bodyColor: '#e6edf3',
          borderColor: '#1f2430',
          borderWidth: 1,
          padding: 12,
          displayColors: true,
          callbacks: {
            label: function(context) {
              const label = context.label || '';
              const value = context.parsed || 0;
              const percentage = chartData.percentages[context.dataIndex];
              return `${label}: ${value} vote${value !== 1 ? 's' : ''} (${percentage}%)`;
            }
          }
        }
      }
    }
  });
}
```

#### Step D.2: Display Statistics and Handle Empty State

**Prompt for Copilot:**
```
In chart.js, add code to display total votes and number of features voted in div#chartStats with white text color. If no votes exist, hide the canvas and show a message with a link back to index.html to cast the first vote.
```

**Expected Output in `chart.js`:**
```javascript
// Display chart statistics (add after chart creation)
const statsDiv = document.getElementById('chartStats');
if (statsDiv) {
  statsDiv.innerHTML = `
    <p><strong>Total Votes:</strong> ${chartData.totalVotes}</p>
    <p><strong>Features Voted:</strong> ${chartData.labels.length}</p>
    <p style="margin-top: 1rem; font-size: 0.9rem;">Vote from <a href="index.html" style="color: var(--primary);">the main page</a> to see live updates.</p>
  `;
}

// Handle empty state (replace the chart creation if block)
if (ctx && chartData.totalVotes > 0) {
  // ... chart creation code ...
} else if (ctx) {
  // Show message when no votes exist
  ctx.style.display = 'none';
  const statsDiv = document.getElementById('chartStats');
  if (statsDiv) {
    statsDiv.innerHTML = `
      <p style="color: var(--muted); text-align: center; padding: 2rem;">
        No votes recorded yet.<br/>
        <a href="index.html" style="color: var(--primary); margin-top: 1rem; display: inline-block;">Go back and cast your first vote!</a>
      </p>
    `;
  }
}
```

### Testing the Chart Feature:

1. Vote for features on `index.html`
2. Click "📊 View Chart" button
3. Verify pie chart displays with correct percentages
4. Check legend shows vote counts and percentages
5. Hover over chart segments to see tooltips
6. Verify white text is visible on dark background
7. Click "← Back to Voting" to return
8. Clear votes and check chart shows empty state

---

## 🔄 Optional Exercise 2: Combined Insights with Tie Detection

**Challenge:** Enhance the voting insights to detect ties and provide actionable recommendations when multiple features have equal votes.

### Part A: Enhanced Results with Tie Indicators

#### Step A.1: Add Tie Indicators to Results List

**Prompt for Copilot:**
```
Modify renderResults function in script.js to detect when features have tied vote counts. Add a 🔗 emoji indicator next to features that are tied with others. Compare each item with previous and next items in the sorted list to detect ties.
```

**Expected Output in `script.js`:**
```javascript
function renderResults() {
  const ul = document.getElementById('results');
  if (!ul) return;
  ul.innerHTML = '';
  const ordered = [...votes.entries()].sort((a, b) => b[1] - a[1]);
  
  ordered.forEach(([feature, count], index) => {
    const li = document.createElement('li');
    
    // Check if tied with previous or next item
    const isTied = index > 0 && ordered[index - 1][1] === count;
    const tiedWithNext = index < ordered.length - 1 && ordered[index + 1][1] === count;
    
    const tieIndicator = (isTied || tiedWithNext) ? ' 🔗' : '';
    li.textContent = `${feature} — ${count} vote${count > 1 ? 's' : ''}${tieIndicator}`;
    
    ul.appendChild(li);
  });
  
  if (ordered.length === 0) {
    ul.innerHTML = '<li>No votes yet. Submit your first vote above.</li>';
  }
}
```

### Part B: Smart Insights for Tied Scenarios

#### Step B.1: Implement Combined Insights Logic

**Prompt for Copilot:**
```
Modify renderInsights function in script.js to handle ties intelligently. When multiple features have the top vote count, display all tied features in a list with a 🔗 emoji, show the vote count, and provide actionable "Next Steps" including: evaluate implementation complexity & ROI, consider resource availability & timeline, align with strategic business goals, and run weighted scoring or another voting round.
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

  const topCount = ordered[0][1];
  // Find all features with the top count (handles ties)
  const leaders = ordered.filter(([_, count]) => count === topCount);

  if (leaders.length > 1) {
    // Multiple leaders (tie)
    const featureList = leaders.map(([name]) => `<li>${name}</li>`).join('');
    insights.innerHTML = `
      <strong>🔗 Tied at ${topCount} vote${topCount > 1 ? 's' : ''} each:</strong>
      <ul style="margin: 0.5rem 0; padding-left: 1.5rem;">${featureList}</ul>
      <strong>Next Steps:</strong><br/>
      • Evaluate implementation complexity & ROI<br/>
      • Consider resource availability & timeline<br/>
      • Align with strategic business goals<br/>
      • Run weighted scoring or another round of voting
    `;
  } else {
    // Single leader
    const [topFeature, topCount] = leaders[0];
    insights.innerHTML = talkingPoints(topFeature, topCount);
  }
}
```

### Part C: Testing Tie Scenarios

**Prompt for Copilot:**
```
Create a test scenario: vote once for Network Optimization, once for Billing Insights, and once for App Crash Reporting to create a three-way tie. Verify that the results list shows 🔗 indicators next to all three features and the insights panel displays the tie message with next steps instead of individual feature talking points.
```

### Testing the Combined Approach:

1. Open `index.html` and clear any existing votes
2. Vote once for "Network Optimization"
3. Vote once for "Billing Insights"  
4. Vote once for "App Crash Reporting"
5. Verify all three show 🔗 emoji in results
6. Check insights panel shows "🔗 Tied at 1 vote each:" with all three features listed
7. Verify "Next Steps" recommendations are displayed
8. Vote again for one feature to break the tie
9. Confirm insights switch back to feature-specific talking points

---

## 🧠 GitHub Copilot Tips

### Effective Prompting Strategies:

1. **Be Specific**: Include exact IDs, class names, and element types
2. **Context Matters**: Mention related features (e.g., "that works with the votes Map")
3. **Break It Down**: Complex features work better as multiple smaller prompts
4. **Use Examples**: "Create a function like renderResults but for..."
5. **Iterate**: If the first result isn't perfect, refine your prompt
6. **Reference Existing Code**: "Modify the renderInsights function to detect ties..."

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
- ✅ Managing state with JavaScript Maps and localStorage
- ✅ Building accessible forms and interactive UI components
- ✅ Integrating third-party libraries (Chart.js) using Copilot
- ✅ Implementing conditional logic for tied scenarios
- ✅ Data visualization with percentage calculations

---

## 🔗 Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Prompt Engineering Guide](https://github.com/microsoft/prompt-engineering)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Chart.js Documentation](https://www.chartjs.org/)
- [localStorage API](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)

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
- localStorage persists data between page loads, perfect for the chart integration
- Tie detection logic demonstrates how AI can help implement complex conditional features

---

**Happy Coding with GitHub Copilot! 🚀**
