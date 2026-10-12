# AzerothCore Game Master Commands Reference

Este guia contém uma lista selecionada de comandos essenciais de Game Master (GM) para o emulador AzerothCore, baseada na documentação oficial.

> 💡 **Dica:** Ao digitar os comandos na janela de chat do jogo, comece com um ponto (ex: `.gm on`). Se for executar os comandos diretamente na janela do console do servidor (`worldserver`), omita o ponto (ex: `gm on`).

---

## 1. Gerenciamento de Contas e Segurança
Comandos utilizados para gerenciar contas de usuários, níveis de segurança e permissões de acesso.

| Comando | Segurança | Sintaxe | Descrição |
| :--- | :---: | :--- | :--- |
| **Account Addon** | 1 | `.account addon #addon` | Defina o nível de expansões permitido. Valores das expansões: 0 - normal, 1 - TBC, 2 - WotLK. |
| **Account 2FA** | 0 | `.account 2fa <setup/remove>` | Digite `.account 2fa` para ver a lista de possíveis subcomandos ou `.help account 2fa $subcomando` para ver informações sobre os subcomandos. |
| **Account Create** | 4 | `.account create <nome> <senha>` | Cria uma nova conta de usuário no servidor com o nome e senha especificados. |
| **Account Set GMLevel** | 4 | `.account set gmlevel <nome> <nivel> <realmid>` | Define o nível de segurança de uma conta (0 = Jogador, 1 = GM, 2 = Desenvolvedor, 3 = Admin). |
| **Account Set Password** | 4 | `.account set password <nome> <senha> <senha>` | Altera a senha de uma conta específica de forma manual. |
| **Ban Account** | 3 | `.ban account <nome> <duracao> <motivo>` | Bane uma conta específica por um tempo determinado (ex: "1d", "1w") ou permanentemente. |
| **Unban Account** | 3 | `.unban account <nome>` | Remove o banimento de uma conta que estava restrita anteriormente. |

---

## 2. Gerenciamento de Personagens
Comandos para modificar, customizar ou controlar os personagens dos jogadores em tempo real.

| Comando | Segurança | Sintaxe | Descrição |
| :--- | :---: | :--- | :--- |
| **GM Modo** | 1 | `.gm on` / `.gm off` | Alterna o modo de visibilidade do GM (Invisibilidade e invulnerabilidade ativadas). |
| **GM Fly** | 1 | `.gm fly on` / `.gm fly off` | Habilita ou desabilita a capacidade de voar livremente pelo mapa sem o uso de montarias. |
| **Character Level** | 3 | `.character level <nome> <quantidade>` | Altera o nível do personagem selecionado ou do nome especificado na sintaxe. |
| **Character Customize** | 2 | `.character customize <nome>` | Força o jogador a customizar a aparência visual do seu personagem no próximo login. |
| **Character ChangeFaction**| 2 | `.character changefaction <nome>` | Força uma alteração de facção (Aliança <-> Horda) no próximo login do jogador. |
| **Revive** | 1 | `.revive` | Ressuscita instantaneamente o personagem morto selecionado como alvo. |

---

## 3. Teleporte e Navegação
Comandos para se movimentar rapidamente pelo mundo do jogo ou gerenciar a localização de outros jogadores.

| Comando | Segurança | Sintaxe | Descrição |
| :--- | :---: | :--- | :--- |
| **GPS** | 1 | `.gps` | Mostra os detalhes exatos do mapa, coordenadas (X, Y, Z, O) e a ID da Zona da sua posição atual. |
| **Go XYZ** | 1 | `.go xyz <x> <y> <z> <mapid>` | Teleporta o seu personagem para as coordenadas cartesianas exatas especificadas. |
| **Tele** | 1 | `.tele <local>` | Teleporta você para um local predefinido no banco de dados (ex: `.tele stormwind` ou `.tele orgrimmar`). |
| **Summon** | 1 | `.summon <nome>` | Invoca e teleporta um jogador específico diretamente para a sua localização atual. |
| **Appear** | 1 | `.appear <nome>` | Teleporta você diretamente para a localização atual do jogador especificado. |

---

## 4. Itens e Magias
Comandos para manipular o inventário dos personagens, equipamentos e habilidades aprendidas.

| Comando | Segurança | Sintaxe | Descrição |
| :--- | :---: | :--- | :--- |
| **Add Item** | 3 | `.additem <itemid> <quantidade>` | Adiciona um item específico ao seu inventário utilizando a ID correspondente do banco de dados. |
| **Learn** | 3 | `.learn <spellid>` | Ensina uma magia, habilidade ou talento específico para o personagem selecionado. |
| **Unlearn** | 3 | `.unlearn <spellid>` | Remove uma magia ou habilidade específica que o personagem selecionado possui. |
| **Lookup Item** | 1 | `.lookup item <nome>` | Procura no banco de dados a ID de um item que coincida com o nome fornecido. |
| **Lookup Spell** | 1 | `.lookup spell <nome>` | Procura no banco de dados a ID de uma magia que coincida com o nome fornecido. |

---

## 5. Manutenção de Servidor e NPCs
Comandos utilizados pelos administradores para gerenciar entidades do mundo e estados da aplicação.

| Comando | Segurança | Sintaxe | Descrição |
| :--- | :---: | :--- | :--- |
| **NPC Add** | 2 | `.npc add <creatureid>` | Cria e spawna um NPC ou monstro permanentemente na sua localização atual. |
| **NPC Delete** | 2 | `.npc delete` | Exclui do banco de dados do mundo o NPC gerado que estiver selecionado como alvo. |
| **Server Info** | 0 | `.server info` | Exibe o tempo de atividade (uptime) do servidor, contagem de jogadores online e ticks de hardware. |
| **Server Restart** | 4 | `.server restart <tempo>` | Agenda uma reinicialização segura do servidor com o tempo regressivo em segundos (ex: `.server restart 60`). |
| **Server Shutdown** | 4 | `.server shutdown <tempo>` | Agenda um desligamento completo e seguro do servidor com o tempo regressivo em segundos. |

---

## 🔍 Dica de Banco de Dados
Se você utiliza módulos customizados, a lista completa e 100% atualizada com base nas suas permissões locais pode ser extraída diretamente da sua database MySQL executando a seguinte query no seu gerenciador (como Keira3 ou HeidiSQL):

```sql
SELECT * FROM `acore_world`.`command`;
```
