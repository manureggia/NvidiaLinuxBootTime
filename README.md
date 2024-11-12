# Installazione

Installato e fleshato attraverso l'SDK manager tutto il necessario, SDK 5.1.4 ubuntu 18

### Modifiche dei BOOTARGS

- Rimozione di una delle due console di stampa `console=ttyS0`
- Aggiunta ai bootargs `quiet`


### Modifiche SYSTEMD

- abilitazione della modalità più potente (8) tramite nvpmodel:
	- ho modificato il file in `/etc/nvpmodel.conf`, cambiando il default (a fine file) da 5 a 8
	- ho modificato l'attuale con `nvpmodel -m 8` e verificato con `nvpmodel -q` che fosse quello giusto
- Posticipazione dopo login di [[Guida disabilitazione servizi#**`nvphs.service`**|nvphs]]
	- `sudo systemctl edit nvphs.service`
   
- Disabilitazione di `alsa-restore.service` e di `sound.target`
	- `systemclt mask sound.target`
- Disabilitazione sistemi USB
	- Disabilitazione del service + `dev-ttyGS0.device` che impediva il boot
  
