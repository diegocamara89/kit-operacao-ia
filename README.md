# Kit Operação IA

Ferramentas e skills para usar IA no trabalho com método e segurança, montadas para os alunos do curso de IA da Senasp
(operacaoia.pages.dev). Cada item tem um vídeo curto no material do curso, na aba Ferramentas.

> **Regra que vale para tudo:** dado de caso, dado pessoal, senha e documento sigiloso não entram em ferramenta na nuvem.
> Para isso existe a IA local (item 13).

## Três jeitos de usar

| Nível | Para quem | O que fazer |
|---|---|---|
| 1 | Qualquer IA (ChatGPT, Gemini, Copilot) | Copie o [modelo de instruções](CLAUDE-modelo.md) para as instruções personalizadas da sua IA. |
| 2 | Claude.ai (site ou app) | Ligue as skills oficiais em Configurações › Capacidades (item 14). |
| 3 | Claude Code (no computador) | Cole o prompt abaixo no Claude Code: ele lê esta página e instala só o que você escolher. |

## Prompt de instalação (nível 3)

```
Quero instalar o Kit Operação IA. Leia https://github.com/diegocamara89/kit-operacao-ia (o README).
1. Me mostre, em português, a lista do Kit com uma linha sobre cada item, e pergunte quais eu quero.
2. Espere a minha resposta.
3. Instale só os que eu escolher, do jeito que o README manda para cada um. Programa que se baixa
   (Ollama, LM Studio): me dê o link oficial e o passo, sem baixar nada sozinho.
4. No fim, teste cada um com o exemplo do README e me diga o que funcionou e o que falhou.
Não instale nada que eu não escolhi.
```

## O Kit

Skill = arquivo de instruções que o Claude usa quando o pedido combina. Mod = gancho que roda sozinho no Claude Code.
Instalar skill de repositório: `git clone <repositório> ~/.claude/skills/<nome>` (para atualizar: `git -C ~/.claude/skills/<nome> pull`).

| # | Item | O que faz | Como instalar | Teste |
|---|---|---|---|---|
| 1 | llm-council | Uma decisão difícil analisada por vários modelos, cada um com um papel; o Claude confere no fim | skill: `git clone https://github.com/diegocamara89/llm-council ~/.claude/skills/llm-council` (sem o agy: peça o "modo sigiloso", que usa só o Claude) | "roda o council sobre esta decisão: …" |
| 2 | call-agy | Passa lote grande de leitura ou segunda opinião ao agy (terminal de IA do Google) | skill: `git clone https://github.com/diegocamara89/call-agy ~/.claude/skills/call-agy`; precisa do agy instalado e logado com conta Google | "pede ao agy para resumir estes documentos públicos" |
| 3 | transcrever-video | Baixa e transcreve vídeo no próprio computador, com marcas de tempo | skill: `git clone https://github.com/diegocamara89/claude-skill-transcrever-video ~/.claude/skills/transcrever-video`; precisa de Python, yt-dlp e faster-whisper | "transcreve este vídeo e resume os pontos principais" |
| 4 | avaliar-ferramenta | Antes de instalar algo, diz se vale, talvez ou é lixo, e por quê | skill: `git clone https://github.com/diegocamara89/avaliar-ferramenta ~/.claude/skills/avaliar-ferramenta` | "avalia esta ferramenta antes de eu instalar" |
| 5 | organizar | Arruma a pasta de um projeto: guia de orientação + limpeza reversível | em preparação | — |
| 6 | handoff | Passa uma conversa longa para uma sessão nova sem perder decisões | em preparação | — |
| 7 | ponytail | Faz o Claude escrever o código mais simples que funciona | plugin (https://github.com/DietrichGebert/ponytail): `claude plugin marketplace add DietrichGebert/ponytail` e `claude plugin install ponytail@ponytail` | "faz isso no modo ponytail: …" |
| 8 | superpowers | Método de trabalho: perguntas antes, plano em tarefas pequenas, teste antes do código | plugin oficial: `claude plugin install superpowers@claude-plugins-official` (ou `/plugin` dentro do Claude Code) | "vamos planejar isso com o Superpowers: …" |
| 9 | hyperframes | Vídeo a partir de uma página da internet (foi assim que os vídeos do Kit foram feitos) | https://github.com/heygen-com/hyperframes · precisa de Node.js; no terminal: `npx hyperframes skills` | "faz um vídeo vertical explicando esta ferramenta" |
| 10 | notebooklm | Perguntas respondidas só com base nos documentos que você sobe (leis, normas) | `pip install "notebooklm-py[browser]"`; guia: https://github.com/teng-lin/notebooklm-py | "cria um caderno com estas normas e pergunta qual é o prazo" |
| 11 | lixeira (mod) | Troca o apagar de vez pela Lixeira e barra comando sem volta | `claude plugin marketplace add diegocamara89/claude-mods` e `claude plugin install lixeira@claude-mods-diego` | "apaga a pasta de rascunhos antiga" (deve ir para a Lixeira) |
| 12 | varredura-push (mod) | Antes de publicar código, procura senha, chave e token e barra o envio | mesmo marketplace: `claude plugin install varredura-push@claude-mods-diego` | "sobe o código para o repositório" |
| 13 | revisor-com-prova (mod) | Achado de revisor de IA só vale com prova; o Claude confere antes de corrigir | mesmo marketplace: `claude plugin install revisor-com-prova@claude-mods-diego` | "revisa este código com o Codex" |
| 14 | CLAUDE.md | Instruções que o Claude lê em toda conversa | copie o [modelo](CLAUDE-modelo.md) para `~/.claude/CLAUDE.md` (vale para tudo) ou para a pasta do projeto | "cria um CLAUDE.md com estas regras" |
| 15 | IA local | IA e transcrição no seu computador, sem internet: o dado não sai da máquina | Ollama: https://ollama.com · LM Studio: https://lmstudio.ai · transcrição: item 3. Modelo maior pede computador mais forte | "transcreve este áudio no meu computador, sem internet" |
| 16 | skills oficiais | Word, PDF, PowerPoint e Excel, e o skill-creator para criar skill nova | Claude.ai: Configurações › Capacidades; Claude Code: https://github.com/anthropics/skills | "cria uma planilha de Excel com as horas de plantão da equipe" |

## Antes de usar no trabalho

- Confira a regra do seu órgão para uso de IA.
- A IA erra com confiança: quem assina o documento confere e responde por ele.
- Ferramenta de terceiro: rode o item 4 antes de instalar.

Autor: Professor Diego Camara · https://github.com/diegocamara89 · Licença MIT (cada repositório citado tem a sua).
