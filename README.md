# GH-300 practice room

A free practice app for the **GitHub Copilot certification (exam GH-300)**. I built it for my own exam preparation and share it so colleagues can practise too.

- **Exam simulations:** 65 questions in 100 minutes, drawn by the official domain weights, with flag-for-review and no feedback until you submit.
- **Practice by domain:** untimed, with the answer, an explanation and a source link after every question.
- **Scenario questions:** dropdowns, yes/no statements and drag-to-order steps, including command-level admin tasks.
- **A results breakdown:** your score per domain, your strengths and focus areas, and a list of your most-missed questions to retry.

290 questions in total.

## How to use it

The whole app is one file: [`public/index.html`](public/index.html). It needs no installation, account or internet connection.

1. Download the repository: click the green **Code** button, then **Download ZIP**, and unzip it.
2. Open `public/index.html` in your browser (Chrome, Edge, Firefox or Safari).

That's all. Your progress is saved in that browser on that device.

## How the questions were made

- **Sources:** written from public sources only. That's the official [GH-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300) (skills measured as of 7 August 2026), GitHub Docs, the GitHub Copilot Trust Center, the GitHub Blog and the Microsoft Learn training modules for GitHub Copilot.
- **Process:** drafted with the help of an AI assistant (Claude, by Anthropic) and checked against the documentation they cite. Every explanation links to its source, so you can verify the answer yourself.
- **Formats:** single and multiple choice, dropdowns, yes/no statements and ordering steps follow the item types Microsoft shows publicly in its [exam sandbox](https://aka.ms/examdemo).

## What this is not

- It contains no questions copied or reconstructed from the live exam, and no material from exam dumps. Using real exam content would break the exam agreement every candidate accepts.
- It isn't official, and scores here don't predict your real score. The question count, the timer and the 70% pass line are estimates; the real exam uses a scaled pass mark of 700 out of 1000.
- It may contain mistakes, and Copilot changes quickly. If an answer disagrees with the current documentation, the documentation is right.

Not affiliated with, endorsed by or connected to GitHub, Microsoft, Pearson VUE or any employer. GitHub, Copilot and Microsoft are trademarks of their owners.

## Privacy

- No account, cookies, analytics, tracking or ads.
- The app makes no network requests. A Content Security Policy in the file blocks every outside connection, which you can check in the source or in your browser's developer tools.
- Your attempts and most-missed questions are stored only in your browser's local storage. They're never sent anywhere. You can delete them from the app's About page.

The code is all in one readable file, so you can check all of this yourself.

## Feedback

I'm Eugen Gavriluta, an external colleague at ING. If you find a wrong or outdated answer or have an idea, open an issue in this repository or reach out at eugen.gavriluta@ing.com or on [LinkedIn](https://www.linkedin.com/in/egavriluta/). And if it helped you pass and you'd like to thank me with a coffee, you're very welcome to reach out too.

## For maintainers

- Questions live in the `BANK` arrays inside `public/index.html`. Each question needs a domain (`d`), the question, the answer, an explanation (`e`) and a source key (`s`) that exists in `SRC`.
- Security headers for hosting are in `public/_headers`, and Cloudflare Workers configuration is in `wrangler.jsonc`. Deploy with `npx wrangler deploy`.
