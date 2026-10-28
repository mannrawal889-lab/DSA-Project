# Human to Skill Matching Network

A Data Structures and Complexity Analysis microproject (SY-AIDS, 2026-27).

**Team:** Nirav Panchal (37), Mann Rawal (50) &nbsp;|&nbsp; **Guide:** Bhagyashree Patil Mam

A small web app that stores people and their skills as a network and returns **ranked matches** for one or more required skills.

## How to run (no install needed)

1. Download or clone this repository.
2. Double-click **`index.html`**. It opens in your browser and works immediately.

That's it. There is nothing to install and no server to start.

## Put it online with GitHub Pages (free)

1. Create a new repository on GitHub and upload all these files (or use the git commands below).
2. Go to **Settings -> Pages**.
3. Under *Build and deployment*, choose **Deploy from a branch**, select **main** and **/ (root)**, then **Save**.
4. After a minute your app is live at `https://<your-username>.github.io/<repo-name>/`.

```bash
git init
git add .
git commit -m "Human to Skill Matching Network"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Features

- Add, remove people and add/remove their skills
- Live search and match: type `python, sql` and see people ranked by score
- Network graph (people on the left, skills on the right) that highlights matches
- "Connected" button: finds people reachable through shared skills (BFS)
- "Run tests" button: runs the Stage 2 test cases T1 to T6 and shows PASS/FAIL

## Data structures used

| Data structure | Where | Why |
| --- | --- | --- |
| Graph (adjacency list) | `personSkills` and `skillPeople` in `network.js` | Person to skill links, easy traversal |
| Hash map (`Map`) | Profile, skill and score lookup | Average O(1) lookup by key |
| Array (vector) | Candidate lists, sorting | Easy iteration and ranking |

## Complexity (expected)

| Operation | Time | Space |
| --- | --- | --- |
| Insertion | O(1) average (O(d) for link check) | O(1) |
| Deletion | O(d) | O(1) |
| Search by skill | O(1 + k) average | O(k) |
| Match and rank | O(m*k + n log n) | O(n) |
| Traversal (BFS) | O(V + E) | O(V) |

d = skills of a person, k = people with a skill, m = skills in the query, n = candidates.

## Files

```
index.html     page layout
style.css      styling
network.js     data structures and algorithms (the core of the project)
app.js         connects the page to the logic
cpp/skill_matching.cpp   original C++ console version (g++ skill_matching.cpp -o skill_matching)
```

## Notes

- All names and skills are fictional sample data. No personal information is collected.
- Skill labels are normalized (trimmed, lowercase), so "Python" and " python " are the same skill.
- Matching is based only on the skills entered and does not prove a person's real-world ability.
