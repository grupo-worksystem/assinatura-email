# Gerador de Assinatura — WorkSystem

Ferramenta local (`index.html`), sem backend, para gerar a assinatura de e-mail padrão da WorkSystem. Preencha os campos, veja o preview em tempo real e exporte o resultado para usar no Outlook.

## Como usar o gerador

1. Abra o arquivo `index.html` no navegador (duplo clique nele).
2. Preencha nome, cargo, unidade e demais campos do formulário à esquerda.
3. Opcionalmente, envie uma foto — ela é recortada em círculo e embutida em base64, junto com a logo, no HTML final (não depende de link externo).
4. No card de preview, escolha uma das opções:
   - **Copiar HTML** — copia o código para a área de transferência, para colar direto no editor de assinaturas do Outlook.
   - **↓ HTML** — baixa um arquivo `assinatura_<nome>.html` já pronto.
   - **↓ JPEG** — baixa uma imagem da assinatura (útil para outros usos, não recomendado para o Outlook).

## Instalando a assinatura no Outlook

### Opção 1 — Colar direto (mais simples)

1. Clique em **Copiar HTML**.
2. No Outlook: **Arquivo → Opções → E-mail → Assinaturas...**
3. Crie uma nova assinatura (ou edite uma existente).
4. Clique no botão de código-fonte/HTML do editor e cole o conteúdo copiado.
5. Salve e defina como assinatura padrão para novas mensagens/respostas.

### Opção 2 — Colocar o arquivo direto na pasta do Outlook

Use esse caminho quando o editor de assinaturas do Outlook "quebrar" a formatação ao colar o HTML.

1. Clique em **↓ HTML** para baixar o arquivo (`assinatura_<nome>.html`).
2. Renomeie o arquivo para o nome que você quer que apareça na lista de assinaturas do Outlook (ex.: `Assinatura.htm`). Recomenda-se manter a extensão `.htm`.
3. Copie esse arquivo para a pasta de assinaturas do Windows:

   ```
   C:\Users\<SEU_USUARIO>\AppData\Roaming\Microsoft\Signatures
   ```

   Substitua `<SEU_USUARIO>` pelo seu usuário do Windows. Você pode colar esse caminho direto na barra de endereços do Explorer (trocando `<SEU_USUARIO>`), ou digitar `%AppData%\Microsoft\Signatures` que o Windows resolve o caminho completo automaticamente.

4. Feche e reabra o Outlook (ou reabra a tela **Arquivo → Opções → E-mail → Assinaturas...**) para que ele detecte o novo arquivo.
5. Selecione a assinatura na lista e defina como padrão para novas mensagens e respostas/encaminhamentos.

> A logo e a foto já vêm embutidas em base64 dentro do próprio HTML gerado, então não é necessário copiar nenhuma pasta `_files` junto — um único arquivo `.htm` é suficiente.

## Estrutura do projeto

- `index.html` — aplicação completa (formulário, preview e geração do HTML/JPEG).
- `images/logo-work.jpeg` — logo usada como fallback/local antes de ser embutida em base64 no HTML gerado.
