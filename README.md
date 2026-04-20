# אפיק ברכה | Afik Bracha

**שמאי מקרקעין ומפתח תוכנה** · Real Estate Appraiser & Software Developer

---

## 🔨 עובד על כרגע

**AppraisalAgent** — מערכת AI לאוטומציה של שמאות מקרקעין *(repo פרטי)*

ניתוח הסכמי מכר, שכירות, תמ"א 38, פינוי-בינוי, קומבינציה ונסחי טאבו — הכל מבוסס בינה מלאכותית.

### Latest Update (20.04.2026)

**Tabu Analyzer — Owner-Shift Detection Across All Excel Flows**

Fixed a subtle extraction bug where the Gemini model occasionally "shifted" owners across sub-parcel boundaries: sub-parcel N would land empty, N's real owner would appear under N+1, and N+1's owner would vanish entirely. Before this fix, the shifted output silently reached the appraiser's Excel.

- Post-parse validator flags any sub-parcel with no owners and raises a flow-specific shift exception carrying the partial rows.
- Retry loop re-runs the same model (shifts are stochastic), then falls back to Gemini Flash, and finally returns the best-effort rows flagged for manual review rather than discarding work.
- Excel export paints flagged rows yellow (FFFF00) and attaches a Hebrew comment on the owner cell explaining the N±1 leak pattern.
- Streamlit UI shows a red banner with a "check adjacent rows" tip only when a shift was actually detected — no permanent caveat in the happy path.
- Applied uniformly to the three Excel-producing flows: parcel allocation table, zero report, and scoring table.
- Regression coverage: 9 new unit tests verifying exception payload, result properties, yellow-fill presence on flagged rows, and clean-extraction regression guards.

---

## 📊 פעילות

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=afik068&show_icons=true&theme=dark&hide_border=true&count_private=true&include_all_commits=true)

![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=afik068&theme=react-dark&hide_border=true&area=true)

---

## 🛠 טכנולוגיות

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Gemini_AI-4285F4?style=for-the-badge&logo=google&logoColor=white)

---

## 📫 יצירת קשר

[![Email](https://img.shields.io/badge/afik.bracha@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:afik.bracha@gmail.com)
