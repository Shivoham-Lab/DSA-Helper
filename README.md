╔═══════════════════════════════════════════════════════════════════════╗
║                                                                       ║
║    ███████╗██╗  ██╗██╗██╗   ██╗ ██████╗ ██╗  ██╗ █████╗ ███╗   ███╗   ║
║    ██╔════╝██║  ██║██║██║   ██║██╔═══██╗██║  ██║██╔══██╗████╗ ████║   ║
║    ███████╗███████║██║██║   ██║██║   ██║███████║███████║██╔████╔██║   ║
║    ╚════██║██╔══██║██║╚██╗ ██╔╝██║   ██║██╔══██║██╔══██║██║╚██╔╝██║   ║
║    ███████║██║  ██║██║ ╚████╔╝ ╚██████╔╝██║  ██║██║  ██║██║ ╚═╝ ██║   ║
║    ╚══════╝╚═╝  ╚═╝╚═╝  ╚═══╝   ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝   ║
║                                                                       ║
║              L  A  B  S  ·  शिवोऽहम्  ·  Independent                   ║
║                                                                       ║
╚═══════════════════════════════════════════════════════════════════════╝

<div align="center">

**Building at the edge of AI, systems, and real-world problems.**

*Shivoham (शिवोऽहम्) — "I am that." Sanskrit. Identity. Intent. Purpose.*

[![Website](https://img.shields.io/badge/website-shivoham--lab.github.io-e8a045?style=flat-square&logo=github)](https://shivoham-lab.github.io)
[![LinkedIn](https://img.shields.io/badge/linkedin-Shivoham_Labs-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/company/shivoham-labs)
[![GitHub Org](https://img.shields.io/badge/github-Shivoham--Lab-181717?style=flat-square&logo=github)](https://github.com/Shivoham-Lab)

</div>

---

# 🧠 DSA Helper — A Claude Skill for Competitive Programming

<div align="center">

**The ultimate structured DSA problem solver, powered by Claude.**
*Paste a link. Get a complete breakdown. Learn while you solve.*

</div>

---

## 📌 What Is DSA Helper?

**DSA Helper** is a Claude skill that transforms any DSA problem into a complete, structured learning experience using the **8-Step DSA Solver Strategy**.

Instead of getting just a solution, you get:
- A plain-language breakdown of the problem
- The reasoning behind the chosen algorithm
- Clean, submission-ready code in Java and C++
- A full manual dry run with variable tracing
- Time & space complexity with educational commentary
- Every edge case your code handles

It's not just a solver — it's a **DSA tutor that never skips steps**.

---

## ⚡ Quick Start

### Trigger
Prefix your prompt with `/dsa` followed by:

```
/dsa <LeetCode URL>
/dsa <Codeforces URL>
/dsa <Your own problem statement>
```

### Examples

```
/dsa https://leetcode.com/problems/two-sum/

/dsa https://leetcode.com/problems/binary-tree-level-order-traversal/

/dsa https://codeforces.com/problemset/problem/158/B

/dsa Given an array of integers, find the maximum product subarray. Return the product.
```

---

## 🏗️ The 8-Step DSA Solver Strategy

Every `/dsa` query is answered using these 8 steps, in strict order. No steps are ever skipped.

| # | Step | What You Get |
|---|--------|-------------|
| 🔷 1 | **Problem Understanding** | Plain-language restatement: input, output, core goal |
| 🔷 2 | **Optimized Algorithmic Approach** | Named algorithm + why it's optimal + why brute force fails + why not other alternatives |
| 🔷 3 | **Clean, Production-Ready Code** | Submission-ready Python (default) or your chosen language |
| 🔷 4 | **Step-by-Step Algorithm Explanation** | 3–5 bullet-point executive summary of the logic |
| 🔷 5 | **Line-by-Line Code Explanation** | Block-by-block breakdown of what each section does |
| 🔷 6 | **Dry Run (The Desk Check)** | Manual trace of a test case showing variable states each step |
| 🔷 7 | **Time & Space Complexity** | Big O analysis with justification + educational insights |
| 🔷 8 | **Edge Cases** | All boundary conditions listed with how the code handles each |

---

## 🔧 How It Works

### Architecture

```
User Input (/dsa ...)
        │
        ▼
┌───────────────────┐
│  Trigger Parser   │  ← Detects /dsa prefix
└───────┬───────────┘
        │
        ▼
┌───────────────────┐
│  Input Classifier │  ← URL or raw problem?
└───────┬───────────┘
        │
   ┌────┴────┐
   │         │
   ▼         ▼
LeetCode  Raw Text
HackerRank  Problem
Codeforces
   │         │
   └────┬────┘
        │
        ▼
┌───────────────────────┐
│  8-Pillar DSA Engine  │
│  ┌─────────────────┐  │
│  │ Pillar 1–8 (seq)│  │
│  └─────────────────┘  │
└───────────────────────┘
        │
        ▼
Structured Markdown Response
(Code + Explanations + Dry Run)
```

### Input Handling

| Input Type | How It's Processed |
|---|---|
| LeetCode URL | Problem identified from URL slug; solved from training knowledge or web fetch if available |
| Codeforces URL | Problem identified by contest + problem ID |
| Custom problem | Interpreted directly; assumptions stated upfront if ambiguous |

---

## 💻 Language Output

By default, solutions are provided in **Python** — the most readable language for learning. You can override this:

```
/dsa <problem>               ← defaults to Python
/dsa <problem> in Java
/dsa <problem> in C++
/dsa <problem> all languages ← Python + Java + C++
```

---

## 📂 Project Structure

```
dsa-helper/
├── README.md                    ← You are here
└── dsa-helper-skill-prompt.md   ← Paste this into Claude to activate the skill
```

---

## 🧩 Sample Output Structure

Here's what a `/dsa` response looks like (abbreviated):

```
🔷 Pillar 1 — Problem Understanding
─────────────────────────────────────
Given a list of numbers and a target, find two numbers that add up to the target.
Input: nums (list of ints), target (int)
Output: list — indices of the two numbers
Goal: Return exactly one pair of indices.

🔷 Pillar 2 — Optimized Algorithmic Approach
─────────────────────────────────────────────
Algorithm: HashMap (Single-Pass)
Why optimal: O(n) time vs O(n²) brute force. We store each number's index as we
scan, checking if (target - current) already exists in the map.
Why brute force fails: Nested loops check every pair — O(n²) is too slow for
large inputs (n up to 10⁴).

🔷 Pillar 3 — Clean Code (Python)
───────────────────────────────────
def two_sum(nums: list[int], target: int) -> list[int]:
    num_to_index = {}  # stores number → its index
    for current_idx, current_num in enumerate(nums):
        complement = target - current_num
        if complement in num_to_index:
            return [num_to_index[complement], current_idx]
        num_to_index[current_num] = current_idx
    return []

... (Pillars 4 through 8 follow)
```

---

## 🎓 Design Philosophy

### Why 8 Pillars?

Most DSA resources give you one of two things: a solution, or an explanation. DSA Helper gives you both — plus the *reasoning*, the *verification*, and the *education*.

The 8-Pillar structure mirrors how top engineers think during interviews and whiteboard sessions:

1. **Understand** before you code
2. **Justify** your approach
3. **Write** clean, readable code
4. **Articulate** the logic
5. **Explain** the implementation
6. **Verify** with a dry run
7. **Analyze** complexity
8. **Anticipate** failure cases

This isn't just for getting answers — it's for **building the muscle memory** that makes you a better problem solver.

### Why Descriptive Variable Names?

`left_ptr` tells you more than `i`. `freq_map` tells you more than `m`. Good variable names make code self-documenting — which is exactly what interviewers and code reviewers want to see.

---

## 🛠️ Setup Instructions

### Using in Claude.ai

1. Open Claude.ai and start a new conversation.
2. Copy the entire contents of `dsa-helper-skill-prompt.md`.
3. Paste it as your **first message** (or use it as a system prompt in Projects).
4. From that point forward, prefix any DSA question with `/dsa`.

### Using via Anthropic API

```python
import anthropic

with open("dsa-helper-skill-prompt.md", "r") as f:
    system_prompt = f.read()

client = anthropic.Anthropic()

message = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=4096,
    system=system_prompt,
    messages=[
        {
            "role": "user",
            "content": "/dsa https://leetcode.com/problems/longest-substring-without-repeating-characters/"
        }
    ]
)

print(message.content[0].text)
```

### Using in Claude Projects (Recommended)

1. Create a new Project in Claude.ai.
2. Add the skill prompt as the **Project Instructions**.
3. Every conversation in the project is now DSA Helper-enabled.
4. No need to re-paste the prompt each time.

---

## 📊 Supported Platforms

| Platform | URL Format | Status |
|---|---|---|
| LeetCode | `leetcode.com/problems/<slug>/` | ✅ Supported |
| Codeforces | `codeforces.com/problemset/problem/<id>/<letter>` | ✅ Supported |
| Custom / Raw Text | Paste the problem directly | ✅ Supported |

---

## 🚀 Future Improvements

- [ ] **Difficulty detection** — auto-tag problems as Easy / Medium / Hard and adjust explanation depth
- [ ] **Multi-approach comparison** — show brute force vs optimized side by side
- [ ] **Follow-up mode** — `/dsa followup` to ask questions about the last solution
- [ ] **Hint mode** — `/dsa hint` to get Socratic nudges instead of the full solution
- [ ] **Contest mode** — timed responses with complexity-first output for speed practice
- [ ] **Language extension** — full Python, Go, Rust support

---

## 🤝 Contributing

Have a pillar improvement suggestion? Found a problem type that breaks the format? Open an issue or submit a PR with:
- The problem that caused an issue
- What output was produced
- What output was expected

---

## 📄 License

MIT License. Free to use, modify, and distribute. Attribution appreciated.

---

<div align="center">

**Built with ❤️ for DSA learners, interview preppers, and competitive programmers.**

*Stop just getting answers. Start understanding solutions.*

</div>
