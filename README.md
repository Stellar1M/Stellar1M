<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,45:1b3a78,75:3382ed,100:ff7ab0&height=230&section=header&text=Stellar1M&fontSize=70&fontColor=ffffff&fontAlignY=38&animation=twinkling&desc=Software%20Engineering%20%C2%B7%20LLM%20and%20Voice%20AI&descSize=22&descAlignY=60&descColor=dfe8ff" alt="Stellar1M: Software Engineering · LLM and Voice AI" width="100%" />

<h1>Hi <img src="https://user-images.githubusercontent.com/18350557/176309783-0785949b-9127-417c-8b55-ab5a4333674e.gif" width="40" alt="waving hand" /> My name is Thinh Nguyen</h1>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&duration=3200&pause=1200&color=3382ED&center=true&vCenter=true&width=640&height=48&lines=Software+Engineering+and+Applied+AI;Python,+JavaScript,+three.js,+LLMs;Student+at+Rutgers+University;Building+Remielle:+real-time+voice+AI" alt="Software engineering and applied AI. Python, JavaScript, three.js, LLMs. Student at Rutgers University. Building Remielle: real-time voice AI" />

<p>
<a href="#project-remielle"><img src="https://img.shields.io/badge/01-Project%20Remielle-3382ed?style=for-the-badge&labelColor=000000" alt="Jump to Project Remielle" /></a>
<a href="#skills"><img src="https://img.shields.io/badge/02-Skills-3382ed?style=for-the-badge&labelColor=000000" alt="Jump to Skills" /></a>
<a href="#github-stats"><img src="https://img.shields.io/badge/03-GitHub%20stats-3382ed?style=for-the-badge&labelColor=000000" alt="Jump to GitHub stats" /></a>
<a href="#socials"><img src="https://img.shields.io/badge/04-Socials-3382ed?style=for-the-badge&labelColor=000000" alt="Jump to Socials" /></a>
</p>

</div>

I'm a student at Rutgers University building real-time AI software. My main project, Remielle, is a voice AI companion: a Python backend that streams LLM replies, listens, speaks and remembers, driving a three.js 3D character in an Electron desktop app over WebSockets, with her animation fitted to timing measured in reference footage.

* 🌍 I'm based in New Jersey
* ✉️ You can contact me at [thinh.nguyen19042803@gmail.com](mailto:thinh.nguyen19042803@gmail.com)
* 🚀 I'm currently working on [Project Remielle](#project-remielle)
* 🧠 I'm learning to make LLM apps reliable: streaming replies, voice barge-in, and regression tests for model behavior
* 💼 Open to software engineering internships: generative AI / LLM apps, full-stack, backend, three.js / WebGL

<p align="center">
<a href="https://www.x.com/stellar1m" target="_blank" rel="noreferrer"><img
src="https://img.shields.io/badge/X-@stellar1m-3382ed?logo=x&logoColor=white&style=for-the-badge&labelColor=000000"
alt="Follow @stellar1m on X" /></a><a href="https://www.twitch.tv/naanosmitee" target="_blank" rel="noreferrer"><img
src="https://img.shields.io/twitch/status/naanosmitee?logo=twitch&style=for-the-badge&color=3382ed&labelColor=000000&label=TWITCH+STATUS"
alt="Twitch status" /></a>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/terminal-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/terminal-light.svg" />
    <img src="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/terminal-dark.svg" alt="Terminal card: real-time LLM, voice AI and 3D developer in New Jersey, student at Rutgers University. Project Remielle, counted from git: 43 commits since 2026-10-10 and 12,449 lines of code, 50% JavaScript, 39% Python, 8% CSS, 3% HTML." width="100%" />
  </picture>
</p>

### Project Remielle

<p align="center">
  <img src="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/remielle-banner.png" alt="Project Remielle: a personal AI companion. A 3D anime character with pink hair and dark wings, next to the title." width="100%" />
</p>

A personal AI companion modeled on **Remielle Dan** from *Zenless Zone Zero*. I'm building it step by step, wiring the models together myself, to learn how AI apps really work: a language model for a brain, a synthesized voice, speech recognition, long-term memory, and a 3D body that moves and reacts.

<p align="center">
  <img src="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/remielle-1.png" alt="Remielle in her black outfit, standing with her dark wings open, rendered live in the app at golden hour" width="300" />
  &nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/remielle-2.png" alt="Remielle in her white outfit, standing with her pale wings open, rendered live in the app at golden hour" width="300" />
</p>
<p align="center"><sub>Two of her outfits, straight from the app's 3D view (three.js + three-vrm).</sub></p>

**What she can do today**

* 🧠 **Brain**: a large language model through OpenRouter. Replies stream in, so she starts talking a couple of seconds after I stop.
* 🗣️ **Voice**: Fish Audio text-to-speech. Her pace and the little sounds before she speaks follow her mood.
* 👂 **Ears**: microphone, Silero voice detection and Fish speech-to-text. I can talk over her, and she reacts while I talk with small sounds and nods.
* 💾 **Memory**: she remembers what we talked about across days, and the memory stays on my own PC.
* 💬 **Speaks first**: she greets me, checks in after a quiet while, and notices when I'm away or back.
* 👀 **Eyes**: she can look at a window or screen I share, and reacts to the games I play.
* 🪟 **Desktop window**: an Electron window that is transparent, always on top and click-through, in the corner of my screen.
* 🧍 **3D body**: a VRM model in three.js with lip sync, blinking, eye contact, moods, and little moments of her own (a wing stretch, a hum, a look around).

<details>
<summary><b>How it fits together</b></summary>

```mermaid
flowchart LR
    subgraph backend["Python backend"]
        mic["Microphone"] --> vad["Silero VAD"] --> stt["Fish speech-to-text"] --> brain["LLM via OpenRouter"]
        brain <--> memory[("Long-term memory")]
        brain --> tts["Fish Audio voice"]
    end
    subgraph window["Electron desktop window"]
        body["3D body: three.js + three-vrm"]
    end
    brain -->|"text and mood, over WebSocket"| body
    tts -->|"audio, for lip sync"| body
```

</details>

**What I'm working on now**

Making her acting match the game. I measure how her face, head and timing move in Zenless Zone Zero footage, then fit her animation to those numbers. The first version is done, and a second round of fixes (sad, happy, surprise and fluster, eye blinks, a new face on every line) is under way. Next up: hand poses that touch her face and chest, solved in Blender; outfit physics (skirt springs, sleeve cuffs); a wing mesh fix; her idle stance; and switching outfits while she runs.

<!-- Once the GitHub Projects board exists, link it here: **Roadmap:** [Project Remielle board](https://github.com/users/Stellar1M/projects/N) -->

<details>
<summary><b>What I've learned so far</b></summary>

* Measure before you believe. I compared Fish's emotion tags against no tag over several takes each, and found no steady difference beyond the normal take-to-take variation. What really changes her delivery is speaking speed and sound tags like a sigh or a chuckle.
* Pausing her on every sound I made felt like buffering. Now she whispers (gets quieter) when I talk over her, and only stops when I say real words.
* At this size, putting every remembered fact in the prompt works better than retrieval.

</details>

**Built with** Python, JavaScript, three.js and three-vrm, Electron, Node.js, WebSockets and Git, plus OpenRouter, Fish Audio and Silero VAD.

<sub>A fan project, not affiliated with HoYoverse. Zenless Zone Zero and Remielle Dan belong to HoYoverse. The 3D model is a fan edit of the official model by 杏子酱Kyouko, used locally and never redistributed, so only screenshots appear here. The source code is in a private repository for now.</sub>

### Skills

<p align="center">
<a href="https://www.oracle.com/java/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/java-colored.svg" width="36" height="36" alt="Java" /></a><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/javascript-colored.svg" width="36" height="36" alt="JavaScript" /></a><a href="https://www.python.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/python-colored.svg" width="36" height="36" alt="Python" /></a><a href="https://code.visualstudio.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/visualstudiocode.svg" width="36" height="36" alt="VS Code" /></a><a href="https://developer.mozilla.org/en-US/docs/Glossary/HTML5" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/html5-colored.svg" width="36" height="36" alt="HTML5" /></a><a href="https://www.w3.org/TR/CSS/#css" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/css3-colored.svg" width="36" height="36" alt="CSS3" /></a><a href="https://www.adobe.com/uk/products/illustrator.html" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/illustrator-colored.svg" width="36" height="36" alt="Illustrator" /></a><a href="https://nodejs.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/nodejs-colored.svg" width="36" height="36" alt="Node.js" /></a><a href="https://git-scm.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/git-colored.svg" width="36" height="36" alt="Git" /></a><a href="https://www.electronjs.org/" target="_blank" rel="noreferrer"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/electron/electron-original.svg" width="36" height="36" alt="Electron" /></a><a href="https://threejs.org/" target="_blank" rel="noreferrer"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/skills/threejs-dark.svg" /><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/skills/threejs.svg" /><img src="https://raw.githubusercontent.com/Stellar1M/Stellar1M/main/assets/skills/threejs.svg" width="36" height="36" alt="three.js" /></picture></a>
</p>

### GitHub stats

<p align="center">
  <a href="https://github.com/Stellar1M"><img src="https://streak-stats.demolab.com/?user=Stellar1M&stroke=1e2638&background=000000&ring=3382ed&fire=ff7ab0&currStreakNum=ffffff&currStreakLabel=3382ed&sideNums=ffffff&sideLabels=ffffff&dates=9aa4b2&border=1e2638&border_radius=10" alt="Stellar1M GitHub streak" width="49%" /></a>
  <a href="https://github.com/Stellar1M"><img src="https://github-readme-stats.vercel.app/api?username=Stellar1M&show_icons=true&title_color=3382ed&text_color=ffffff&icon_color=ff7ab0&bg_color=000000&border_color=1e2638&border_radius=10&rank_icon=github" alt="Stellar1M GitHub stats" width="49%" /></a>
</p>

<!-- These two cards only count public activity. Project Remielle is a private repo, so they stay small until
"Include private contributions on my profile" is switched on (GitHub settings, Public profile). Top languages card
removed: it showed "No languages data." because my public repos have no code yet. Add it back once one does:
<a href="https://github.com/Stellar1M"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Stellar1M&layout=compact&langs_count=10&title_color=3382ed&text_color=ffffff&icon_color=3382ed&bg_color=000000&border_color=1e2638&border_radius=10&custom_title=Top%20Languages" alt="Top Languages" /></a>
-->

### Socials

<p align="center"> <a href="https://www.github.com/Stellar1M" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" width="32" height="32" /> </picture> </a> <a href="http://www.instagram.com/stellar1m/" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/instagram-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/instagram.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/instagram.svg" width="32" height="32" /> </picture> </a> <a href="https://www.linkedin.com/in/thinh-nguyen-4a13082b3/" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin.svg" width="32" height="32" /> </picture> </a> <a href="http://www.medium.com/@thinh.nguyen19042803" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/medium-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/medium.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/medium.svg" width="32" height="32" /> </picture> </a> <a href="https://www.x.com/stellar1m" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/twitter-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/twitter.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/twitter.svg" width="32" height="32" /> </picture> </a> <a href="https://www.twitch.tv/naanosmitee" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/twitch-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/twitch.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/twitch.svg" width="32" height="32" /> </picture> </a></p>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,45:1b3a78,75:3382ed,100:ff7ab0&height=140&section=footer&reversal=true&animation=twinkling" alt="" width="100%" />
</div>
