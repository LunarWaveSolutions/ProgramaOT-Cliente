# Programa OT — Cliente (ProgramaOT-Cliente)

Este repositório contém o cliente oficial de acesso ao nosso servidor de Tibia Programa OT. Ele inclui o executável, bibliotecas necessárias (Qt 6), recursos e arquivos auxiliares para rodar o cliente de forma imediata no Windows.

Além do uso direto, este repositório é a fonte utilizada pelo nosso Canary Launcher para baixar e atualizar automaticamente o cliente por meio das Releases do GitHub.

## Como obter e executar

Opção recomendada (automática):
- Use o Canary Launcher do Programa OT. Ele detecta a versão mais recente publicada nas Releases deste repositório, baixa o pacote do cliente e oferece um único botão que alterna entre "Download", "Update" e "Play".

Opção manual:
1. Acesse a aba Releases deste repositório.
2. Baixe o pacote do cliente (ex.: `client-to-update.zip`).
3. Extraia o conteúdo localmente.
4. Abra `ProgramaOT/bin/` e execute `client.exe`.

Observações:
- Os arquivos `Tibia.dat` e `Tibia.spr` já acompanham o projeto.
- Dependências do Qt 6 necessárias à execução estão incluídas em `ProgramaOT/bin/`.
- Logs e dados gerados em tempo de execução ficam em pastas como `ProgramaOT/log/`, `ProgramaOT/minimap/`, `ProgramaOT/characterdata/` e `ProgramaOT/cache/`.

## Estrutura (resumo)

- `ProgramaOT/bin/`: executável (`client.exe`), DLLs do Qt6, recursos `.rcc` e traduções `.qm`.
- `ProgramaOT/assets/`, `ProgramaOT/sounds/`, `ProgramaOT/storeimages/`: catálogos e mídias usadas pelo cliente.
- `ProgramaOT/conf/`: opções do cliente e configurações de GPU.
- `ProgramaOT/minimap/`, `ProgramaOT/characterdata/`, `ProgramaOT/cache/`, `ProgramaOT/log/`: dados locais gerados pelo uso.
- `ProgramaOT/3rdpartylicences/`: textos das licenças de terceiros.

## Releases e integração com o Launcher

- Publicamos versões do cliente via Releases do GitHub. O Canary Launcher usa o `tag_name` da Release para identificar se há atualização.
- O pacote do cliente é disponibilizado como artefato (ex.: `client-to-update.zip`), contendo o diretório `ProgramaOT/` pronto para ser usado.
- Veja também: `README-WORKFLOW.md` e `README-WORKFLOW-SHORT.md` para detalhes do processo de release.

## Suporte e comunidade

- Dúvidas, novidades e comunicados: nosso Discord — https://discord.gg/KUR3GAKE

## Licenças

Consulte `ProgramaOT/3rdpartylicences/` para informações sobre as licenças de componentes de terceiros (Qt, Battleye, EasyLogging, Google Protobuf, SFML, etc.).

## Arquivos grandes (Git LFS)

Este repositório inclui binários e mídias volumosas (DLLs, EXEs, PNGs, DAT/SPR). Para facilitar versionamento e push/pull confiáveis, recomendamos Git LFS.

Passos sugeridos:
1. Instale o Git LFS: https://git-lfs.com/
2. Rode `git lfs install` no seu ambiente.
3. O arquivo `.gitattributes` já inclui padrões para rastrear formatos grandes via LFS.
4. Faça commit e push normalmente — o LFS cuidará do armazenamento dos binários.
