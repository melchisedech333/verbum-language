### :arrow_right: Descrição geral da interface de controle da VM/interpretador Verbum.

#### Conectividade.
- Verificar conectividade com node / disponibilidade de conexão.
- Autenticar no node / conecta no mesmo passando pelo handshake e autenticação (caso necessário).


#### Recursos gerais.
- Enviar código Verbum para ser executado no interpretador.
- Enviar AST para ser executada no interpretador.


#### Hot code reloading e meta-programação.

<b>Funcionalidades:</b>
```
    Insert, Update, Delete:
        Importações (arquivos de cabeçalho / inclusões).
        Pacote / space / namespace.
        Arquivo.
        Classe.
        Método.
        Linha A.
        Linha A à Z (Update, Delete).
```

<b>Controles relacionados à execução (usado em conjunto):</b>
```
    Aguardar finalização da execução atual.
    Finalizar abrutamente todas execuções em aberto.
```


#### Informações de uso e disponibilidade de recursos do node.

<b>Informações gerais:</b>
```
    Informações do node (tipo, conexão, configurações, etc).
    OS, Kernel, distribuição, memória, disco, IP local/externo, usuário, etc.
```


#### Gestão dos nodes.

- Compartilhamento do Node Mapper.
- Rede de nodes em execução (informações atualizadas em tempo de execução).


