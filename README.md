# ivasheg_infra
ivasheg Infra repository
#
Основное задание -
Cпособ подключения к someinternalhost в одну
команду из вашего рабочего устройства:

ssh -J appuser@62.84.117.105 appuser@10.128.0.34
#
Дополнительное задание-
вариант решения для подключения из консоли при помощи
команды вида ssh someinternalhost из локальной консоли рабочего
устройства:

nano /.ssh/config

### The Bastion Host
Host bastion
  Hostname 62.84.117.105
  User appuser
### The Remote Host
Host someinternalhost
  Hostname 10.128.0.34
  ProxyJump appuser@62.84.117.105
  User appuser
#

ssh someinternalhost

# cloud-bastion-vpn
bastion_IP = 62.84.117.105
someinternalhost_IP = 10.128.0.34
