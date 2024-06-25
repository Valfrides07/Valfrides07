<h1 align="center">Olá, prazer em recebe-lo(a) aqui!!</h1>

###

<h2 align="left">Sou estudante de Sistemas de Informação, com desejo em aprimorar minhas habilidades. Tenho focado os meus estudos em Python, C#, MySqL com interesse nas áreas de Dados e Backend. Estou em busca das mais recentes tecnologias e práticas de desenvolvimento. Durante meu curso, tenho a oportunidade de aprofundar conhecimentos e aplicar as melhores práticas em projetos práticos. Procuro oportunidades para expandir minhas habilidades técnicas, contribuir para projetos inovadores e crescer profissionalmente em um ambiente dinâmico.</h2>

###

<p align="center">✨ Creating bugs since 2023<br>📚 I'm currently learning Python e MySql<br>🎯 Goals: A minha primeira vaga de estágio</p>

###

<h2 align="left">Atualmente tenho conhecimento em:</h2>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original-wordmark.svg" height="40" alt="python logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-plain-wordmark.svg" height="40" alt="html5 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-plain-wordmark.svg" height="40" alt="css3 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" height="40" alt="mysql logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" height="40" alt="csharp logo"  />
</div>

###

<img src="https://raw.githubusercontent.com/Valfrides07/Valfrides07/output/snake.svg" alt="Snake animation" />

###

<div align="center">
  <a href="linkedin.com/in/valfrides-fernandes-279596236" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="41" alt="linkedin logo"  />
  </a>
  <a href="https://www.instagram.com/_01freitass/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="41" alt="instagram logo"  />
  </a>
  <a href="432512646164774912" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=7289DA&logoColor=white&labelColor=&style=for-the-badge" height="41" alt="discord logo"  />
  </a>
  <a href="valfridesfreitas29@gmail.com" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="41" alt="gmail logo"  />
  </a>
</div>

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
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
