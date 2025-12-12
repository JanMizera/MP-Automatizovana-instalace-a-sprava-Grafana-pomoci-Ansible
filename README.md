# MP-Automatizovana-instalace-a-sprava-Grafana-pomoci-Ansible
Některé části mi byly poskytnuty a všechny převzaté části budou zmíněny v textu práce

##Předpoklady a řešení problémů s boxem

Tento projekt používá operační systém **bento/ubuntu-24.04**. Kvůli známému problému s metadaty boxu na Vagrant Cloudu (spojenému s VirtualBoxem) **standardní `vagrant up` nemusí fungovat**, pokud box není předem nainstalován lokálně.

### 1. Ruční stažení Vagrant Boxu

1.  **Stáhněte** box `bento/ubuntu-24.04` (verze pro `amd64` / VirtualBox). Box najdete na oficiálním Vagrant Cloud repozitáři.
2.  **Přejmenujte** stažený soubor na přesný název, který potřebujeme: `bento-ubuntu-24.04-virtualbox.box`.
3.  Přesuňte tento soubor do kořenového adresáře tohoto projektu (`MP`).

### 2. Import Boxu do Vagrantu

Následně musíte box přidat do lokální Vagrant cache. Spusťte tento příkaz z kořenového adresáře projektu, kam jste soubor uložil:

```bash
vagrant box add bento/ubuntu-24.04 bento-ubuntu-24.04-virtualbox.box --provider virtualbox  