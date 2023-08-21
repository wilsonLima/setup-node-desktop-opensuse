setup-node-desktop-opensuse
=========

Role do Ansible com passos para a instalação de pacotes de Desenvolvimento NodeJS em Desktop Linux Opensuse.

Distribuições Suportadas pela Role
------------

- openSUSE Leap 15.4 ou superior
- openSUSE Tumbleweed


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
  
- nodejs: Instala os componentes do Nodejs.
- eslint: Instala o componentes eslint via NPM.
- gitignore: Instala o componentes gitignore via NPM.


Exemplo de Inventario
----------------

Exemplo de arquivo de hosts: pasta_invetario/hosts

    [NOME]
    IP ansible_connection=ssh ansible_ssh_user=USUARIO ansible_ssh_pass=SENHA_URUARIO ansible_become_pass=SENHA_ROOT


Especificar interpretador python 3: pasta_invetario/group_vars/all

    ansible_python_interpreter: "/usr/bin/python3"


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - setup-node-desktop-opensuse



Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "eslint" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, eslint"


License
-------

MIT