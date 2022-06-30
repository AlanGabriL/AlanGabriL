<h1 align="left">Hey 👋 Broo?</h1>

###

<p align="left">My name is Alan Gabriel Makus and I'm a Brasilian.<br>I work in DigitalDoc 🟢🔵<br>and I am Front-end developer</p>

###

<h2 align="left">About me</h2>

###

<p align="left">✨ Programming since 2021<br>📚 I'm learning... TypeScript, JavaScript and Figma<br>🎯 Goals: Create my company<br>🎲 I like Games and Movies...</p>

###

<h2 align="center">I code with</h2>

###

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" height="40" width="58" alt="vscode logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" width="58" alt="javascript logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" width="58" alt="html5 logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" width="58" alt="css3 logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="40" width="58" alt="python logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="40" width="58" alt="git logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" height="40" width="58" alt="vuejs logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/google/google-original.svg" height="40" width="58" alt="google logo"  />
</div>

###

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=react&locale=en&hide_border=true&username=Alan" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?locale=en&hide_title=false&layout=compact&card_width=320&langs_count=3&theme=react&hide_border=true&username=Alan" height="150" alt="languages graph"  />
</div>

###

<h2 align="center">Redes Sociais !!</h2>

###

<div align="center">
  <a href="https://twitter.com/ProgramadorAlan" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/twitter/default.svg" width="65" height="40" alt="twitter logo"  />
  </a>
  <a href="https://www.instagram.com/alanga_briel/" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/instagram/default.svg" width="65" height="40" alt="instagram logo"  />
  </a>
</div>

###

<img href="https://raw.githubusercontent.com/Alan/Alan/blob/output/snake.svg" alt="Snake animation" />

###

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
