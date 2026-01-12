# Olá, eu sou o João Victor Mian Valdomiro! 👋🤖

Sou apaixonado por **Mecatrônica e Desenvolvimento de Software**. Gosto de conectar código com o mundo físico!

### 🔧 Tech Stack & Ferramentas
<div align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=c,cpp,python,arduino,raspberrypi,ros,matlab,linux,git,vscode,idea&theme=dark" />
  </a>
</div>

<br/>

### 🧠 Sobre Mim
```json
{
  "area": "Engenharia Mecatrônica",
  "foco_atual": ["Sistemas Embarcados", "Automação", "IoT"],
  "linguagens": ["C++", "Python", "Ladder"],
  "hobbies": ["Robótica", "Impressão 3D", "Café"]
}
📊 Minhas Estatísticas
<div align="center"> <img height="180em" src="https://www.google.com/search?q=https://github-readme-stats.vercel.app/api%3Fusername%3DSEU_USUARIO%26show_icons%3Dtrue%26theme%3Dtokyonight%26include_all_commits%3Dtrue%26count_private%3Dtrue"/> <img height="180em" src="https://www.google.com/search?q=https://github-readme-stats.vercel.app/api/top-langs/%3Fusername%3DSEU_USUARIO%26layout%3Dcompact%26theme%3Dtokyonight"/> </div>

🐍 Contribuições (Snake Game)
<div align="center"> <img src="https://www.google.com/search?q=https://github.com/SEU_USUARIO/SEU_USUARIO/blob/output/github-contribution-grid-snake.svg" alt="snake" /> </div>


-----

### Passo 3: Ativando a "Cobrinha" (O Pulo do Gato)

A animação da cobrinha (Snake) não funciona sozinha. Você precisa criar um robô (GitHub Action) para gerá-la.

1.  No seu repositório, clique na aba **Actions** (lá em cima).
2.  Clique em **New workflow** (ou "set up a workflow yourself").
3.  O GitHub vai pedir para criar um arquivo. Nomeie ele como: `snake.yml`.
4.  Cole este código dentro dele:

<!-- end list -->

```yaml
name: Generate Snake

on:
  schedule:
    # Roda a cada 6 horas
    - cron: "0 */6 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - uses: Platane/snk@v2
        with:
          # Seu nome de usuário aqui é automático, não precisa mudar
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            
      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
