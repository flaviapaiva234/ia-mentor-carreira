<!--START_SECTION:header-->
<div align="center">
  <p align="center">
    <img src="./assets/aperto-mao-robotica.png" alt="IA Mentor de Carreira" width="270px" />
    <h1>IA Mentor de Carreira</h1>
  </p>
</div>
<!--END_SECTION:header-->

<p align="center">
  <a href="NIVEL">
    <img src="https://img.shields.io/static/v1?label=Nivel&message=Basico&color=484888&labelColor=202024" alt="Nivel" style="margin: 0 10px;">
  </a>
  <img src="https://img.shields.io/static/v1?label=Status&message=Concluido&color=28a745&labelColor=202024" alt="Status" style="margin: 0 10px;" />
</p>

<br/>

<table align="center" style="border-collapse: collapse; width: 80%;">
  <tr>
    <td align="center" style="padding: 20px;">
      <a href="https://github.com/flaviapaiva234">
        <img src="https://avatars.githubusercontent.com/flaviapaiva234" width="140px;" alt="Flávia Paiva" style="border-radius: 50%;"/>
        <br/>
        <span style="font-size: 1.6em; font-weight: bold;">Flávia Paiva</span>
      </a>
    </td>
    <td style="padding: 20px; vertical-align: top;">
      <p style="margin: 8px 0; line-height: 1.8;">
        🎯 <strong>Analista de QA Júnior</strong>
      </p>
      <p style="margin: 8px 0; line-height: 1.8;">
        🌟 Criadora do projeto IA Mentor de Carreira
      </p>
      <p style="margin: 8px 0; line-height: 1.8;">
        👩‍💻 Habilidades: Engenharia de Prompt, HTML, CSS, JavaScript, Lógica de Programação
      </p>
      <p style="margin: 8px 0;">
        <a href="https://www.linkedin.com/in/flaviapaiva234/">
          <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
        </a>
        &nbsp;&nbsp;
        <a href="https://github.com/flaviapaiva234">
          <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
        </a>
      </p>
    </td>
  </tr>
</table>

<br/>

## 💻 Sobre o Projeto

**IA Mentor de Carreira** é um sistema composto por dois agentes de IA conversacionais que simulam uma mentoria personalizada para quem deseja ingressar ou evoluir na área de tecnologia.

- **Agente 1 – Entrevistador de Carreira**: realiza 7 perguntas para entender interesses, experiência prévia, disponibilidade de estudo, preferências (pessoas/dados/código), objetivos e interesses técnicos.
- **Agente 2 – Planejador de Carreira**: com base nas respostas, gera um plano de estudos de 90 dias, incluindo visão do dia a dia, mapa de habilidades, projeto de portfólio, roteiro de entrevistas e trilha DIO recomendada.

O projeto demonstra o uso de **engenharia de prompts** para estruturar agentes eficazes, além de técnicas de curadoria de fontes e documentação de aprendizado.

## 📚 Curadoria de Fontes

Para embasar as perguntas e o plano de estudos, utilizei as seguintes fontes abertas:

| Fonte | Tipo | Por que usei? |
|-------|------|----------------|
| [Roadmap.sh](https://roadmap.sh/) | Site de referência | Mapeamento de habilidades por área (front-end, back-end, dados, QA). |
| [DIO – Formação QA](https://www.dio.me/) | Plataforma de cursos | Base para entender trilhas de aprendizado em QA e tecnologia. |
| [Brasscom – Demanda de TI 2025](https://brasscom.org.br/) | Estudo de mercado | Dados sobre áreas com maior empregabilidade e tendências. |
| [GitHub Copilot Docs – Engenharia de Prompt](https://docs.github.com/en/copilot/using-github-copilot/prompt-engineering-for-github-copilot) | Documentação oficial | Aprender a refinar prompts para obter respostas mais estruturadas. |

## ⚙️ Engenharia de Prompts e "Cicatrizes"

### Agente 1 – Entrevistador de Carreira

**Prompt final (versão refinada):**  
(arquivo [`prompts/agente-entrevistador.md`](./prompts/agente-entrevistador.md))

**Cicatrizes registradas:**
- Inicialmente, o agente fazia várias perguntas de uma vez, confundindo o usuário. Foi adicionada a regra **"Faça APENAS 1 pergunta por vez"**.
- O agente pulava para a análise antes de receber as 7 respostas. Incluí a condição **"Após 7 perguntas, PARE de perguntar e faça a análise"**.
- A matriz de decisão interna (afinidade, demanda, ramp-up, aproveitamento) precisou ser explicitada para que o ranqueamento das carreiras ficasse coerente.

### Agente 2 – Planejador de Carreira

**Prompt final (versão refinada):**  
(arquivo [`prompts/agente-planejador.md`](./prompts/agente-planejador.md))

**Cicatrizes registradas:**
- O primeiro plano de estudos ignorava a disponibilidade de horas. Adicionei regras de personalização (menos de 5h, 5-10h, mais de 15h).
- O agente não considerava níveis de experiência (zero, iniciante, alguma). Incluí adaptações de ritmo e conteúdo conforme a experiência.
- A seção "Projeto de Portfólio" era genérica; refinei para exigir entregáveis e critérios de aceitação concretos.

### Exemplos de interação

Os exemplos de saída dos agentes estão em arquivos separados:

- [Resposta do Agente 1 (entrevistador) para um perfil de QA iniciante](./exemplos/resposta-agente1-entrevistador.md)
- [Resposta do Agente 2 (planejador) gerando plano de 90 dias para QA](./exemplos/resposta-agente2-planejador.md)

## 📘 Miniguia de Estudo

### Resumo do Assunto

Aprendi a criar agentes de IA conversacionais usando **engenharia de prompts estruturada**. Os principais conceitos envolvem:

- **Agentes autônomos**: sistemas que seguem um fluxo de trabalho definido, tomando decisões com base em entradas do usuário.
- **Orquestração**: coordenar dois ou mais agentes (entrevistador → planejador) para cumprir um objetivo maior.
- **Matriz de decisão**: método interno para ranquear opções (carreiras) baseado em critérios ponderados (afinidade, demanda, ramp-up, aproveitamento de experiência).
- **Handoff**: transferência de informações entre agentes – essencial para que o segundo agente comece com os dados corretos.

### Glossário

| Termo | Definição |
|-------|------------|
| **Agente** | Programa ou prompt estruturado que executa tarefas específicas de forma (semi)autônoma. |
| **Engenharia de Prompt** | Disciplina de criar instruções precisas para IA, incluindo contexto, regras e formatação. |
| **Cicatriz (scars)** | Erros ou dificuldades encontradas durante o desenvolvimento e as soluções aplicadas. |
| **Handoff** | Transferência de dados entre agentes (ex: do entrevistador para o planejador). |
| **Roadmap de 90 dias** | Plano de estudos dividido em semanas, adaptado à disponibilidade do usuário. |
| **Matriz de decisão** | Conjunto de critérios (ex: afinidade, demanda de mercado) usados para ranquear opções. |

### Prompts Reutilizáveis

- **Para criar um agente de entrevista estruturada:**  
  > "Você é um entrevistador especializado em [área]. Faça exatamente 5 perguntas, uma por vez, sobre [tópicos]. Após todas as respostas, apresente um resumo com [critérios]."

- **Para gerar plano de estudos personalizado:**  
  > "Com base nas seguintes informações: [carreira, horas/semana, experiência], crie um roadmap de 90 dias com semanas divididas em fundamentos, prática e portfólio. Inclua também um projeto prático e dicas de entrevista."

- **Para simular handoff entre agentes:**  
  > "Você receberá os dados do agente anterior. Use-os para gerar um plano completo e responda apenas com o plano, sem fazer perguntas adicionais."

- **Para refinar um prompt muito vago:**  
  > "Reescreva o prompt a seguir adicionando: regras de comportamento (uma pergunta por vez), formato de saída (tabela ou lista), critérios de decisão (matriz de pontuação) e restrições (não citar salários)."

## 🎯 Objetivos e Resultados Esperados

Após a conclusão deste projeto, o estudante será capaz de:

- Criar agentes de IA conversacionais para resolver problemas reais (ex: orientação de carreira, triagem de currículos, suporte ao cliente).
- Aplicar técnicas de engenharia de prompts, incluindo restrições, formatação de saída e handoff entre agentes.
- Documentar o processo de desenvolvimento, registrando cicatrizes e aprendizados.
- Utilizar o GitHub Copilot ou ferramentas similares para refinar prompts e gerar conteúdo estruturado.

---

## 👩‍💻 Autora

Flávia Paiva

🔎 Analista de QA Júnior  
🐞 Testes Manuais | Casos de Teste | Identificação de Bugs
