Victor Hugo

- 👨‍💻  Systems Analyst /
- 📘™ Student in Computer Engineering /<br>
<div style="display: inline_block"><br>
<img align="center" alt="Victor-Windows Server" height="30" width="40" src="https://icongr.am/fontawesome/address-card.svg?size=128&color=currentColor">
<img align="center" alt="Victor-Windows Server" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/windows8/windows8-original.svg">
<img align="center" alt="Victor-Linux" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg">
<img align="center" alt="Victor-Wordpress" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/wordpress/wordpress-plain.svg">
<img align="center" alt="Victor-Woocomerce" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/woocommerce/woocommerce-original.svg">
<img align="center" alt="Victor-Visual Studio" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg">
<img align="center" alt="Victor-PostgreSql" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg">
<img align="center" alt="Victor-SSMS" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/microsoftsqlserver/microsoftsqlserver-plain.svg">
<img align="center" alt="Victor-MySQL" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg">
<img align="center" alt="Victor-Java" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg">
<img align="center" alt="Victor-Js" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg">
<img align="center" alt="Victor-Python" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg">
<img align="center" alt="Victor-HTML5" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg">
<img align="center" alt="Victor-C#" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg">
<br>
<img align="center" alt="Victor-C" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg">
<img align="center" alt="Victor-PHP" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg">
<img align="center" alt="Victor-Azure" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg">
<img align="center" alt="Victor-Arduino" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/arduino/arduino-original.svg">
<img align="center" alt="Victor-Apache" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/apache/apache-original.svg">
<img align="center" alt="Victor-AndroidStudio" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/androidstudio/androidstudio-original.svg">
<img align="center" alt="Victor-CSS3" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg">
<img align="center" alt="Victor-Docker" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg">
<img align="center" alt="Victor-Git" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg">
<img align="center" alt="Victor-Git-Hub" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg">
<img align="center" alt="Victor-Google" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/google/google-original.svg">
<img align="center" alt="Victor-Google-Cloud" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/googlecloud/googlecloud-original.svg">
<img align="center" alt="Victor-Google-Cloud" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/grafana/grafana-original.svg">
</div>
<br>
<a href = "mailto:inoocrycsgo@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
<a href="https://www.instagram.com/manasczek" target="_blank"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"></a>
 <a href="https://www.facebook.com/Victor.iNooCry" target="_blank"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white"></a>
 
 
 
 
# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"

# This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Generates the snake  
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: Manasczek
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

     # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
