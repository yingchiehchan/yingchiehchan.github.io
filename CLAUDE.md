# Ying-Chieh Chan Academic Website — Project Context

## Overview
Personal academic website for **詹瀅潔 (Ying-Chieh Chan)**, Associate Professor, Department of Civil Engineering, National Taiwan University.

- **GitHub Pages**: yingchiehchan.github.io (custom domain: yingchiehchan.com)
- **Repo**: `https://github.com/yingchiehchan/yingchiehchan.github.io.git`
- **Git user**: Ying-Chieh Chan / yingchiehchan@gmail.com

## Files
| File | Purpose |
|------|---------|
| `index.html` | Homepage — bio, research areas, awards, contact |
| `publications.html` | Full publication list — journals + conference papers |
| `group.html` | Research group — current students + alumni |

All three files share the same inline CSS/JS pattern (no build step, no framework). Font size is set globally via `html { font-size: 18px; }`.

## Key Conventions

### Author name language rule
- **Chinese-titled paper** → use Chinese names for all authors, including the PI: **詹瀅潔**
- **English-titled paper** → use English names for all authors, including the PI: **Ying-Chieh Chan**

### Common co-authors with both name forms
| Chinese | English | Notes |
|---------|---------|-------|
| 詹瀅潔 | Ying-Chieh Chan | PI |
| 曾惠斌 | Hui-Ping Tserng | Co-advisor (external) |
| 施冠群 | Kuan-Chun Shih | Former student |
| 蔣玲娜 | Lin-Na Chiang | Former student |

### Award badge (publications.html & group.html)
```html
<span class="award-badge">🏆 Best Paper Award</span>
```
Placed inline inside the `.ct` div, after the paper title. CSS is defined in each file's `<style>` block using `--amber` / `--amber-bg` variables.

### Conference venue format
`Conference Name, City, Country, Month Year`  
Example: `CISBAT 2025, Lausanne, Switzerland, September 2025`

CISBAT is always September in Lausanne, Switzerland. Building Simulation (IBPSA) is September. SCEM is July (local Taiwan).

## publications.html Structure

```
Journal Papers (pub-section data-cat="journal")
  └─ Annual sections (2024–2025, 2021–2023, ...)

Conference Papers (pub-section data-cat="conference")
  ├─ International — 2026
  ├─ International — 2024–2025
  ├─ International — 2018–2023
  ├─ International — 2012–2016 (Purdue era)
  ├─ Local — 2026 (30th SCEM)
  ├─ Local — 2025 (29th SCEM)
  ├─ Local — 2024 (28th SCEM)
  ├─ Local — 2023 (27th SCEM)
  ├─ Local — 2022 (26th SCEM)
  └─ Local — 2021 & Earlier (25th SCEM, 22nd SCEM, TCI)
```

Each paper entry:
```html
<div class="conf-item" data-tags="conference energy">
  <div class="ct">Paper title <span class="award-badge">🏆 Award</span></div>
  <div class="cv">Author1, <strong>詹瀅潔</strong> · Conference, City, Country, Month Year</div>
</div>
```

## group.html Structure

Sections (in order):
1. **PhD Students** — current
2. **Master's Students** — current
3. **PhD Alumni**
4. **Master's Alumni**

Alumni entries use `.award-badge` for thesis awards and `.alumni-name-cn` span for Chinese names alongside romanized names.

## Recurring Students / People
- **譚世麟** — PhD, building energy simulation (30th SCEM Best Paper)
- **林逸群** — PhD, positive energy community
- **陳加乘** — PhD, public art and built environment
- **高健智** — PhD, system dynamics
- **王順典** — current student (30th SCEM Outstanding Paper)
- **Achille Wendyam Tapsoba** — visiting/external researcher (appears in 25th & 27th SCEM)
- **Simeon N. Ingabo** — PhD alumnus 2025, ResearchGate: https://www.researchgate.net/profile/Simeon-Ingabo

## Push to GitHub
```powershell
cd "C:\Users\NTUChan1\Desktop\ychan-website"   # update path if folder moved
git add index.html publications.html group.html
git commit -m "your message"
git push origin main
```
No build step needed — changes are live after push (GitHub Pages delay ~1 min).
