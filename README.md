# Programa OT — Cliente (ProgramaOT-Cliente)

Este repositório contém o cliente oficial de acesso ao nosso servidor de Tibia Programa OT. Ele inclui o executável, bibliotecas necessárias (Qt 6), recursos e arquivos auxiliares para rodar o cliente de forma imediata no Windows.

Além do uso direto, este repositório é a fonte utilizada pelo nosso ProgramaOT-Launcher para baixar e atualizar automaticamente o cliente por meio das Releases do GitHub.

## Como obter e executar

Opção recomendada (automática):
- Use o ProgramaOT-Launcher. Ele detecta a versão mais recente publicada nas Releases deste repositório, baixa o pacote do cliente e oferece um único botão que alterna entre "Download", "Update" e "Play".

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

## Releases e integração com o ProgramaOT-Launcher

- Publicamos versões do cliente via Releases do GitHub. O ProgramaOT-Launcher utiliza as informações configuradas no `launcher_config.json` para descobrir a versão e baixar o pacote correspondente.
- O pacote do cliente deve ser disponibilizado como artefato (ex.: `client-to-update.zip`), contendo o diretório `ProgramaOT/` pronto para ser usado.
- Veja também: `README-WORKFLOW.md` e `README-WORKFLOW-SHORT.md` para detalhes do processo de release.

### Como preparar uma Release para o Launcher

1. Gere/atualize os binários do cliente em `ProgramaOT/bin/` (inclua todas as DLLs necessárias, `client.exe`, `qt.conf`, traduções `.qm` e recursos `.rcc`).
2. Atualize os catálogos e arquivos de mídia conforme necessário em `ProgramaOT/assets/`, `ProgramaOT/sounds/`, `ProgramaOT/storeimages/`.
3. Se utilizar arquivos de verificação como `assets.json` e `assets.json.sha256`, atualize-os quando houver mudanças nos recursos.
4. Empacote o diretório `ProgramaOT/` inteiro em um arquivo `.zip` (ex.: `client-to-update.zip`).
5. Publique uma Release no GitHub e anexe o `.zip` gerado como artefato.
6. Ajuste o `launcher_config.json` no repositório do ProgramaOT-Launcher para apontar para a Release/artefato e (se aplicável) para a fonte de versão. Use os campos definidos no `launcher_config.json` do launcher (ex.: URLs de pacote e versão conforme schema lá documentado).

Observação:
- Por padrão, o ProgramaOT-Launcher é instalado no diretório de dados do usuário (`%AppData%\\ProgramaOT`) pelo instalador (InstallSimple PRO). O local de download/instalação do cliente pode seguir o padrão do launcher ou ser ajustado via configuração no `launcher_config.json` (conforme o schema definido no projeto do launcher).

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
