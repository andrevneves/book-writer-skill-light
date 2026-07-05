# Test Plan - Book Writer Light

Objetivo: validar que o `Book Writer Light` funciona fora do repositório da skill, em outra pasta, iniciando um livro do zero.

## 1. Preparar o ambiente

Escolher uma pasta limpa de teste:

```bash
mkdir -p /Users/developer/projects/A.I/writing/test-book-writer-light
cd /Users/developer/projects/A.I/writing/test-book-writer-light
```

Conferir que a pasta está vazia:

```bash
ls -la
```

## 2. Confirmar o plugin instalado

Verificar se o plugin está disponível no Codex:

```bash
codex plugin list
```

Esperado:

```text
book-writer-light@book-writer-light  installed, enabled
```

Se não aparecer, instalar o marketplace local do repo e depois o plugin:

```bash
codex plugin marketplace add /Users/developer/projects/A.I/writing/book-writer-skill-light
codex plugin add book-writer-light@book-writer-light
```

## 3. Abrir um thread novo no Codex

Iniciar o Codex Desktop ou CLI com o diretório apontando para a pasta de teste:

```text
/Users/developer/projects/A.I/writing/test-book-writer-light
```

Usar uma conversa nova para garantir que a skill carregue do zero.

## 4. Invocar a skill explicitamente

Prompt inicial:

```text
Use $book-writer-light to start a new book project.
```

Esperado:

- Codex reconhece `$book-writer-light`
- Lê o `SKILL.md` da skill
- Inicia o fluxo de onboarding
- Faz perguntas uma por vez
- Evita carregar contexto em excesso

## 5. Responder com um livro simples

Usar respostas curtas para testar o fluxo:

```text
No existing material.
Author: Test Author.
Working title: The Glass Orchard.
Genre: Literary mystery.
Premise: A botanist returns to her abandoned hometown after receiving a seed that should not exist.
POV: close third person.
Tense: present.
Language: English.
Length: short novel, around 8 chapters.
Style: lyrical but restrained.
Initialize now.
```

## 6. Verificar arquivos criados

Conferir os arquivos gerados:

```bash
find . -maxdepth 4 -type f | sort
```

Esperado, no mínimo:

```text
README.md
book-memory-bank/Core/activeContext.md
book-memory-bank/Core/context_index.yml
book-memory-bank/Core/projectbrief.md
book-memory-bank/Core/progress.md
book-memory-bank/Core/story_structure.md
book-memory-bank/Core/world_and_characters.md
book-memory-bank/Style/style_guide.md
```

## 7. Validar o índice de contexto

```bash
ruby -e 'require "yaml"; YAML.load_file("book-memory-bank/Core/context_index.yml"); puts "context_index yaml ok"'
```

Esperado:

```text
context_index yaml ok
```

## 8. Testar a primeira tarefa real

Prompt:

```text
Use $book-writer-light to outline chapter 1.
```

Esperado:

- Codex lê primeiro `book-memory-bank/Core/context_index.yml`
- Usa contexto mínimo
- Cria outline em `Outlines/Chapter_Outlines/` ou estrutura equivalente
- Não abre todos os arquivos sem necessidade

## 9. Testar continuidade básica

Prompt:

```text
Use $book-writer-light to write the opening scene from chapter 1.
```

Esperado:

- Cria arquivo em `Chapters/` ou equivalente
- Atualiza `activeContext.md`
- Atualiza `context_index.yml`, especialmente `previous_context`
- Registra os arquivos alterados

## 10. Critérios de aprovação

A skill passa no teste se:

- `$book-writer-light` é reconhecido em uma pasta externa
- Um projeto novo é inicializado sem depender do repo da skill
- O memory bank é criado corretamente
- `context_index.yml` é YAML válido
- O fluxo usa contexto compacto
- Uma tarefa posterior, como outline ou cena inicial, funciona e atualiza memória

## 11. Critérios de falha

Investigar se ocorrer:

- `$book-writer-light` não aparece
- Codex não encontra assets ou templates
- Caminhos internos apontam para o repo antigo
- `context_index.yml` não é criado ou é inválido
- A skill carrega arquivos demais
- O script `build_context_pack.py` não está disponível no plugin instalado
