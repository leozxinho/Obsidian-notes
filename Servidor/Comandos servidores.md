

Deletar arquivos vídeos/imagem do /mnt/vms-storage/alarms

<font color="#00b0f0">find . -type f ! \( -newermt "2025-03-07" ! -newermt "2025-04-08" \) -delete</font>

Visualizar câmeras com maiores retenção no banco de dados

<font color="#00b0f0">source ~/.env && mongo "$DATABASE/connect?authSource=admin" --eval 'db.services.find().sort({retencao: -1})'</font>

Visualizar quantidade de câmeras com o ultrabaixa ativo

<font color="#00b0f0">source ~/.env && mongo --quiet "$DATABASE/connect?authSource=admin" --eval 'db.services.count({baixa_latencia: true})'</font>

Gerar app_token:

<font color="#00b0f0">echo $(openssl rand -hex 25)</font>

Limpar Memoria Ram em Cache (ProxMox)

<font color="#00b0f0">echo 3 > /proc/sys/vm/drop_caches</font>

Formatar as partições de um disk

<font color="#00b0f0">sudo wipefs -af /dev/sdx</font>


