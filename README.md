# projeto-1
/scripts# nano criacao.sh

#!/bin/bash

acho "criando diretorios"

-mkdir /publico
mkdir /adm
mkdir /ven 
mkdir /sec

echo "criando grupo de usuarios"

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo"criando usuarios"

useradd carlos -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_ADM
useradd maria -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_ADM
useradd joao -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_ADM

useradd debora -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_VEN
useradd daniel -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_VEN
useradd luana -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_VEN

useradd cleane -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_SEC
useradd jessica -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_SEC
useradd marcia -m -s /bin/bash -p $(openssl poasswd -crypt senha123) -G GRP_SEC

echo "permissoes dos diretorios"

chown root:GRP_ADM /adm
chown root:GRP_ADM /ven
chown root:GRP_ADM /sec

chmod 770 /adm
chmod 770 /ven 
chmod 770 /sec 
chmod 777 /publico

echo "fim"

