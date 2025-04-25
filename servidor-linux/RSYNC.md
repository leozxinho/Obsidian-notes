CRIAR A KEY NO SERVIDOR DE ANTIGO/PROD:  
ssh-keygen -t rsa -b 4096

COLETAR A CHAVE PÚBLICA DO SERVIDOR ANTIGO/PROD:  
cat ~/.ssh/id_rsa.pub

E ADICIONAR NO SERVIDOR BACKGROUND:  
sudo nano ~/.ssh/authorized_keys


LIBERAR O IP DO SERVIDOR ANTIGO/PROD NO SERVIDOR DE BACKGROUND:  
sudo ufw allow from 177.38.8.220  to any

REALIZAR O RSYNC NO SERVIDOR ANTIGO/PROD:
rsync -Pavr /mnt/vms-storage/diretorio/* connect@connect-307.servicestream.io:/mnt/vms-storage/diretorio/