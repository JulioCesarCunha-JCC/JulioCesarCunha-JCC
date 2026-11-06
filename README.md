##############################################
# ARQUIVO 1: README.md  (na raiz do repositório)
##############################################

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=Júlio%20Cunha&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Dev%20%7C%20Segurança%20%7C%20Open%20Source&descSize=20&descAlignY=60" width="100%" alt="header" />

  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&pause=1000&color=58A6FF&center=true&vCenter=true&width=500&lines=Go+%7C+C%2B%2B+%7C+MySQL;Linux+%26+Fedora;Cibersegurança+no+TryHackMe" alt="typing" />
</div>

<br>

<div align="center">
  <a href="https://www.linkedin.com/in/julio-c%C3%A9sar-acacio-cunha-b371b03b4/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="mailto:julio.cunha@gmail.com"><img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://tryhackme.com/p/julio.cunha"><img src="https://img.shields.io/badge/TryHackMe-212C42?style=for-the-badge&logo=tryhackme&logoColor=white" /></a>
</div>

## 🚀 Sobre mim
- 🔭 Estudando segurança ofensiva e desenvolvimento em Go
- 🛠️ Gosto de Linux, hardware (Arduino) e automação
- 📫 Fale comigo pelo LinkedIn ou e-mail

## 🧰 Tecnologias
<div align="center">
  <img src="https://skillicons.dev/icons?i=go,cpp,linux,fedora,mysql,androidstudio,arduino,git&theme=dark" />
</div>

## 📊 Estatísticas
<div align="center">
  <img height="170" src="https://github-readme-stats.vercel.app/api?username=SEU_USUARIO&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117" />
  <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USUARIO&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117" />
  <br>
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=SEU_USUARIO&theme=tokyonight&hide_border=true&background=0d1117" />
</div>

## 📈 Atividade
<div align="center">
  <img src="https://raw.githubusercontent.com/SEU_USUARIO/SEU_USUARIO/activity-graph-output/activity-graph.svg" width="100%" alt="activity graph" />
</div>

## 🐍 Contribuições
<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SEU_USUARIO/SEU_USUARIO/pacman-output/pacman-contribution-graph-dark.svg">
    <img alt="pacman" src="https://raw.githubusercontent.com/SEU_USUARIO/SEU_USUARIO/pacman-output/pacman-contribution-graph.svg">
  </picture>
</div>

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,100:0f2027&height=100&section=footer" width="100%" />
  <img src="https://visitor-badge.laobi.icu/badge?page_id=SEU_USUARIO.SEU_USUARIO" />
</div>


##############################################
# ARQUIVO 2: .github/workflows/activity-graph.yml
##############################################

name: Update Activity Graph

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  build:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Generate activity graph
        uses: maurodesouza/github-readme-activity-graph-action@v1
        with:
          username: ${{ github.repository_owner }}
          options: radius=16&theme=react&area=true
          output_path: dist/activity-graph.svg
          token: ${{ secrets.GITHUB_TOKEN }}

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: activity-graph-output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


##############################################
# ARQUIVO 3: .github/workflows/pacman.yml
##############################################

name: Generate Pacman Graph

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: pacman-output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
