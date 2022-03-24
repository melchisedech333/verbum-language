### :arrow_right: Descrição geral da interface de controle da VM/interpretador Verbum.

#### Funcionalidades:

- Verificar conectividade com node / disponibilidade de conexão.
- Autenticar no node / conecta no mesmo passando pelo handshake e autenticação (caso necessário).

- Conecta (e mantem conectado) nos nodes-filhos persistentes:
-    Apenas do escopo do node em questão.
-    De todos os nodes do sistema / código em questão.

- Enviar código Verbum para ser executado.
- Enviar AST para ser executada.

- Hot code reloading e meta-programação:
-     Insert, Update, Delete:
-         Importações (arquivos de cabeçalho / inclusões).
-         Pacote / space / namespace.
-         Arquivo.
-         Classe.
-         Método.
-         Linha A.
-         Linha A à Z (Update, Delete).

-     Controles relacionados à execução (usado em conjunto):
-         Aguardar finalização da execução atual.
-         Finalizar abrutamente todas execuções em aberto.
        
- Informações de uso e disponibilidade de recursos do node:
-     Informações do node (tipo, conexão, configurações, etc).
-     OS, Kernel, distro, memória, espaço em disco, IP local, IP externo, Nome de usuário, etc.
-     Nodes filhos em execução (com seus respectivos recursos).


