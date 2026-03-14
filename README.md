# 📊 GitHub PR Dashboard

A professional, interactive Pull Request analytics dashboard built with vanilla HTML, CSS, and Chart.js. Get a bird's-eye view of your team's PR health — activity trends, review status, cycle times, CI results, and more — all in one place.

![Dashboard Preview](https://img.shields.io/badge/status-live-brightgreen) ![Chart.js](https://img.shields.io/badge/Chart.js-4.4.1-FF6384?logo=chartdotjs) ![License](https://img.shields.io/badge/license-MIT-blue)

---

## ✨ Features

- **Metric Cards** — Open PRs, Merged count, Average cycle time, CI pass rate at a glance
- **Weekly Activity Bar Chart** — 8-week breakdown of Opened / Merged / Closed PRs
- **Review Status Donut Chart** — Visual split of Approved / In Review / Changes Requested / No Review
- **Cycle Time Area Chart** — Trend line showing PR throughput improving over time
- **CI Breakdown** — Pass / Fail / Pending percentages with horizontal bar chart
- **Top Authors Leaderboard** — Most active contributors ranked by PR count
- **Live PR List** — Open PRs with CI dots, reviewer avatars, and status badges
- **Activity Timeline** — Last 24h events: merges, opens, reviews, CI failures
- **Search & Filter** — Filter by Open / Merged / Closed / Draft tabs

---

## 🚀 Getting Started

### Prerequisites

- A modern browser (Chrome, Firefox, Safari, Edge)
- No build tools required — runs entirely in the browser

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/github-pr-dashboard.git

# Navigate into the project
cd github-pr-dashboard

# Open in browser (no server needed)
open index.html
```

Or serve locally with any static file server:

```bash
# Using Python
python -m http.server 3000

# Using Node.js (npx)
npx serve .
```

Then open `http://localhost:3000` in your browser.

---

## 📁 Project Structure

```
github-pr-dashboard/
├── index.html          # Main dashboard HTML + inline CSS + JS
├── README.md           # You are here
├── LICENSE             # MIT License
└── assets/
    └── preview.png     # Dashboard screenshot
```

---

## 🔧 Configuration

To connect to a real GitHub repository, replace the mock data in `index.html` with live API calls:

```javascript
// Replace mock PR data with GitHub API
const res = await fetch(
  'https://api.github.com/repos/{owner}/{repo}/pulls?state=open',
  {
    headers: {
      'Authorization': `Bearer ${YOUR_GITHUB_TOKEN}`,
      'Accept': 'application/vnd.github.v3+json'
    }
  }
);
const prs = await res.json();
```

### Environment Variables (if using a backend)

| Variable | Description | Example |
|---|---|---|
| `GITHUB_TOKEN` | Personal Access Token | `ghp_xxxxxxxxxxxx` |
| `GITHUB_OWNER` | Repository owner | `acme-corp` |
| `GITHUB_REPO` | Repository name | `platform` |

---

## 📊 Charts & Data

| Chart | Library | Data Source |
|---|---|---|
| Weekly Activity | Custom SVG bars | GitHub Events API |
| Review Status | Canvas 2D (native) | GitHub Reviews API |
| Cycle Time Trend | Chart.js Line | PR open/close timestamps |
| CI Breakdown | CSS progress bars | GitHub Check Runs API |
| Top Authors | CSS progress bars | PR author aggregation |

---

## 🎨 Tech Stack

- **HTML5 / CSS3** — Zero framework dependencies
- **Chart.js 4.4.1** — Cycle time area chart
- **Canvas 2D API** — Custom donut chart
- **GitHub REST API** — Data source (mock data included for demo)
- **CSS Variables** — Full light/dark mode support

---

## 🌙 Light / Dark Mode

The dashboard uses CSS custom properties and automatically adapts to the user's system preference:

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-background-primary: #1a1a1a;
    --color-text-primary: #f0f0f0;
  }
}
```

---

## 📸 Screenshots

| Section | Preview |
|---|---|
| Metric Cards | Cycle time, open PRs, CI rate |
| Bar Chart | 8-week activity breakdown |
| Donut Chart | Review status distribution |
| PR List | Live open PRs with CI status |

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

```bash
# Fork the repo and create a branch
git checkout -b feat/your-feature-name

# Make your changes, then commit
git commit -m "feat: add assignee filter to PR list"

# Push and open a Pull Request
git push origin feat/your-feature-name
```

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

---

## 📝 Roadmap

- [ ] GitHub OAuth login
- [ ] Multi-repo support
- [ ] Slack / email notifications for stale PRs
- [ ] Export dashboard as PDF report
- [ ] Assignee & label filters
- [ ] Mobile-responsive layout improvements
- [ ] WebSocket live updates

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [Chart.js](https://www.chartjs.org/) for beautiful, responsive charts
- [GitHub REST API](https://docs.github.com/en/rest) for PR data
- Inspired by GitHub's native PR view and Linear's analytics

---

<p align="center">Made with ❤️ by the platform team @ acme-corp</p>
