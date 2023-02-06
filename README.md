# start_environment_pattern_linux
Desafio DIO Linux-do-zero: crie um script shell para criar usuários, grupos, permissões e deletar usuários anteriores, grupos e diretórios.

## Mapa: 
![image](https://user-images.githubusercontent.com/33848415/217080927-3104ee8d-a709-4f1e-9a52-6af8a356b272.png)

## Definições:
- Excluir diretórios, arquivos, grupos e usuários criados anteriormente;
- Todo provisionamento deve ser feito em um arquivo do tipo Bash Script;
- O dono de todos os diretórios criados será o usuário root;
- Todos os usuários terão permissão total dentro do diretório publico;
- Os usuários de cada grupo terão permissão total dentro de seu respectivo diretório;
- Os usuários não poderão ter permissão de leitura, escrita e execução em diretórios de departamentos que eles não pertencem;
- Subir arquivo de script criado para a sua conta no GitHub.

## Definições pré-respondidas:

- Todo provisionamento deve ser feito em um arquivo do tipo Bash Script;
    - `nano start_environment_pattern.sh`
- Excluir diretórios, grupos e usuários criados anteriormente:
    - `rm -Rf /adm`
    - `groupdel GRP_ADM`
    - `userdel -r maisa`
- Criar usuários e atribuí-los aos grupos
    - `useradd carlos -m -g GRP_ADM -p $ (openssl passwd -crypt Senha123)`
    `passwd carlos -e`
- Os usuários de cada grupo terão permissão total dentro de seu respectivo diretório;
- Os usuários não poderão ter permissão de leitura, escrita e execução em diretórios de departamentos que eles não pertencem;
- Criar as pastas e definir as permissões (root 7, grupo 7, outros 0)
    - `mkdir /adm -m 770`
    - `mkdir /ven -m 770`
    - `mkdir /sec -m 770`
    - `mkdir /public -m 777`
- Cria os grupos
    - `groupadd GRP_ADM`
    - `groupadd GRP_VEN`
    - `groupadd GRP_SEC`
- O dono de todos os diretórios criados será o usuário root;
    - `chown root:GRP_ADM /adm`
    - `chown root:GRP_ADM /ven`
    - `chown root:GRP_ADM /sec`
- Todos os usuários terão permissão total dentro do diretório publico;
    - `chmod 777 /publico`
- Subir arquivo de script criado para a sua conta no GitHub.

## Executar o arquivo
- `chmod +x  start_environment_pattern.sh`concede a permissão de execução do arquivo
- `./start_environment_pattern.sh` executa o arquivo desejado
