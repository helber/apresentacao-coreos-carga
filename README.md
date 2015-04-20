Apresentação - Cluster com CoreOs e Docker
==========================================

# Este é uma apresentação feita para o solisc 9

O roteiro seguido para preparar a apresentação foi:

- Capa
- Agenda
- História
    - De onde veio a necessidade
    - TV funcionando (vídeo)
    - Servidores e serviços (cadeia de requests)
    - Como escala (árvore)
    - Problemas
        - Too Many Open Sockets
        - Too Many Open Files
        - Conexões persistentes
        - Carga de arquivos estáticos
        - Carga e consumo de banco
        - Limites nas aplicações
    - Testes de carga
        - vários testes de carga com requests - FAIL
        - Baseados em **logs** - FAIL
        - Direto no javascript (Simulando digitação - controle remoto) - SUCCESS
- Caminho seguido
    - Problemas:
        - Abrir multiplas instcancias de browser
        - Passar parametros
        - Não isolamento entre as instâncias do chrome
    - Resolver isolamento (Docker)
        - Linux containers
        - chroot com steroides
    - Passagem de parametros
        - Exemplos de código
    - Muitas instancias do browser (muitos containers docker)
        - Servidores?
        - Agentes que lançam os dockers?
    - CoreOS
        - 140 Mb comprimido
        - Não roda Python, Perl, Ruby, Javascript, ...
        - Sem gerenciamento de pacotes
        - Sem compilador
        - Orquestração de serviços
        - Se um servidor cair os serviços são iniciados automaticamente nos outros
        - Resolve conflitos entre instancias de containers
        - Ex.:
            - rode o X no mesmo servidor de Y
            - Não deixe o X rodar no mesmo servidor de Y
            - Somente uma instancia do Z pode estar rodando
            - Roda somente no servidor X
- Como funciona tudo?
    - DHCP:
        - Código
    - CoreOS inicia:
        - Carrega o arquivo de spec de inicialização (cloud-configs)
            - Código
        - libvirt
            - Código
    - Etcd
        - Banco de dados chave valor
        >etcdctl ls --recursive /_coreos.com
    - Fleet
        - Interface de cluster para o systemd
        - Consulta o etcd
            - Exemplo de código
    - Serviços
        - Exemplo de código
    - Exemplos de execução
- Agradescimentos

Autor Helber Maciel Guerra
e-mails: helber@cianet.ind.br / helbermg@gmail.com

