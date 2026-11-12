# E4Temas 1.1.1

Gerenciador de temas para o menu nativo do Nintendo 3DS com Luma 13.4 ou superior.

## Downloads

- [CIA para instalar pelo FBI](dist/e4temas-v1.1.1.cia?raw=true)
- [3DSX para Homebrew Launcher](dist/e4temas-v1.1.1.3dsx?raw=true)
- [Pacote completo](dist/E4Temas-v1.1.1-experimental.zip?raw=true)
- [Código-fonte](dist/E4Temas-v1.1.1-codigo-fonte.zip?raw=true)
- [SHA-256](dist/SHA256SUMS.txt)

Esta revisão mantém a versão **1.1.1** no FBI e no aplicativo. Atualiza o logo
do HOME Menu e os logos da interface; a animação de areia de entrada foi
preservada byte a byte. A edição anterior 1.1.1 foi confirmada pelo usuário no
console. A revisão visual passou nos testes locais, mas aguarda teste em hardware.

## Recursos

Catálogo cumulativo no seletor Trocar tema; dois temas visuais; seleção de CIAs
em lote; exclusão opcional dos arquivos após sucesso; otimizações para New 3DS
com compatibilidade Old; barra de progresso, contagem e filtro de CIAs incompatíveis.
A CIA de entrada não é executada nem instalada: somente os dados válidos de tema
são importados no catálogo gerado. Limite de 100 temas.

## Controles

- SELECT: aparência; A salva.
- A: abrir pasta ou escolher CIA; X: marcar/desmarcar; Y: revisar fila.
- Na revisão, X alterna apagar as CIAs; L + R + A confirma a instalação.
- B: voltar; R: ferramentas; L: reparar catálogo; START: sair.

Processa um tema por vez. A barra acompanha etapas e bytes gravados, não tempo
restante. A exclusão só ocorre após sucesso de toda a fila e conferência dos
arquivos. Falhas preservam as CIAs de entrada. A fila não é atômica: temas já
concluídos permanecem instalados.

Preserve `/3ds/scl-temas/`, que contém catálogo, backups e recuperação. Essa pasta
é compartilhada com SCL Temas. Ao concluir, reinicie e selecione o tema em
Trocar tema. Uma coleção já funcional não precisa de reparo novamente.

## Compilação

DevkitARM/libctru, makerom e bannertool são necessários. Dentro do ZIP de código-fonte, os scripts de `tools/`
aceitam caminhos de ferramentas; consulte seus argumentos `--help`. Os logos
fornecidos estão em `assets/new-logo/`; `compile_branding.py` converte-os para os
formatos do aplicativo sem modificar `assets/intro.e4a`. A geração de glifos usa
as fontes Consolas e Segoe UI do Windows. Não são incluídas ferramentas ou fontes.

## Validação e licença

Interface renderizada pelo código C nas duas paletas; banner RGBA4444 conferido;
CIA/3DSX, versão, recursos e hashes verificados com ctrtool. O núcleo funcional
permanece igual à edição 1.1.1 anterior. Nenhum benchmark comparativo é prometido.

Consulte [LICENSE](LICENSE) e as licenças em `vendor/` dentro do ZIP de código-fonte.
