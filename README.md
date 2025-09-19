# 👋 Hi, I’m Murilo Rodrigues

🎓 Student of Systems Development at [ETEC Prof. Camargo Aranha]

💻 Training as a Back-End Developer at SENAI

☕ Passionate about Java, OOP, and SQL, currently exploring Spring Boot and REST APIs

🚀 Looking for opportunities as a Back-End Development Intern / Junior Developer


###

🔧 Tech Stack & Tools

Languages: Java, SQL, PHP, TypeScript, JavaScript, CSS

Frameworks: Spring Boot (learning)

Databases: MySQL

Tools: Git, GitHub, VS Code, Eclipse



---

📂 Featured Projects

DevBack-End_SENAI → Java exercises and backend concepts

MyProjects → Personal projects in different languages



---

📫 How to reach me

✉️ Email: muriloveroneze0987@gmail.com

📱 WhatsApp: +55 (11) 96144-0243

🌐 LinkedIn: www.linkedin.com/in/murilo-rodrigues-viegas-883628311

🖥️ GitHub: MuriloRVv2



###

<div align="left">
  
  <img src="https://cdn4.iconfinder.com/data/icons/logos-and-brands/512/181_Java_logo_logos-512.png" height="40" alt="Java logo"  />
  <img width="12" />
  <img src="https://download.logo.wine/logo/Eclipse_(software)/Eclipse_(software)-Logo.wine.png" height="40" alt="Eclipse logo"  />
  <img width="12" />
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Visual_Studio_Code_1.35_icon.svg/512px-Visual_Studio_Code_1.35_icon.svg.png?20210804221519" height="40" alt="VSCode logo"  />
  <img width="12" />
  

</div>

###

name: Generate Pac-Man Game

on:
  schedule: # Run automatically every 24 hours
    - cron: "0 */24 * * *"
  workflow_dispatch: # Allows manual triggering
  push: # Runs on every push to the main branch
    branches:
      - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

   steps:
      - name: Generate pacman-contribution-graph.svg
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}

  # Push the generated SVG to the output branch
  - name: Push pacman-contribution-graph.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

