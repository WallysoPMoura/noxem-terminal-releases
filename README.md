# Noxem Terminal — releases

Canal público de versões do **Noxem Terminal**, um cliente SSH para Android e iPhone para cuidar
das próprias VPS pelo celular (terminal com tmux, contêineres Docker e apps do Coolify). O app é
instalado por sideload: SideStore no iPhone, `.apk` no Android.

Este repositório tem só o que é publicado. O código-fonte fica num repositório privado. Tudo aqui
é gerado automaticamente a cada versão estável:

- `source.json`: a fonte (source) do SideStore/AltStore;
- `latest.json`: lido pelo app para avisar quando sai uma versão nova;
- `icon.png`: o ícone mostrado na fonte;
- [Releases](https://github.com/WallysoPMoura/noxem-terminal-releases/releases): cada versão
  `vX.Y.Z` com `NoxemTerminal-X.Y.Z.ipa` (iPhone) e `NoxemTerminal-X.Y.Z.apk` (Android) e as notas.

Só entram versões **estáveis** (`vX.Y.Z`). Pré-releases de teste não são publicadas aqui.

## iPhone (SideStore)

Requisitos: SideStore já instalado e configurado com o seu Apple ID
([docs.sidestore.io](https://docs.sidestore.io)) e iOS 16.4 ou mais novo.

1. No SideStore, abra **Sources**, toque em **+** e cole a URL:
   ```
   https://raw.githubusercontent.com/WallysoPMoura/noxem-terminal-releases/main/source.json
   ```
2. Abra a fonte **Noxem Terminal** e instale o app. Se ele já estiver instalado (por um `.ipa`
   avulso), instale pela fonte **por cima**, sem desinstalar: com o mesmo Apple ID, os dados
   ficam.
3. Daí em diante, quando sair uma versão nova, o app avisa e o SideStore mostra **Atualizar**
   no Noxem Terminal.

O SideStore assina o app com o seu Apple ID; com Apple ID gratuito, a assinatura vale 7 dias e o
SideStore a renova no próprio iPhone.

## Android

1. Na página do Release mais recente, baixe o `NoxemTerminal-X.Y.Z.apk`.
2. Abra o arquivo no aparelho (permita "instalar apps desconhecidos" para o navegador ou o
   gerenciador de arquivos usado).
3. Para atualizar, faça o mesmo com o `.apk` novo: ele instala **por cima** do atual e mantém os
   dados, porque todas as versões são assinadas com a mesma chave. Não desinstale antes:
   desinstalar apaga as VPS, chaves e senhas do aparelho.

## O aviso no app

Em Ajustes, "Procurar atualizações" (ligado por padrão) faz o app ler o `latest.json` deste
repositório no máximo uma vez por dia. Quando há versão nova, ele mostra um aviso com as notas e
o caminho para atualizar. O app nunca baixa nem instala nada sozinho; desligada a opção, ele não
faz nenhuma requisição ao GitHub.
