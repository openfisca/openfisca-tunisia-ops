# openfisca-tunisia-ops
Scripts et fichiers de configuration d'OpenFisca-Tunisia sur le serveur.

## Build

### Legislation Explorer

```
npm run clean
npm run build:tunisia
```

## Services systemd

Gestion des fichiers `.service`.  
Répertoire des services systemd : `/etc/systemd/system`  
> Répertoire type : `production-configs`


### Création d'un service

Création d'un lien symbolique vers un service : 
```
cd /etc/systemd/system
ln -s PATH_SERVICE NOM_SERVICE
```

Activer un service : `systemctl enable NOM_SERVICE`  
Démarrer un service : `systemctl start NOM_SERVICE`  
Re-démarrer un service : `systemctl restart NOM_SERVICE`  

Si un fichier de configuration a été modifié sur le disque : `systemctl daemon-reload`

### Statuer sur l'état des services

Lister les services :  
    Par fichier de service : `systemctl list-unit-files`   
    Avec plus d'information : `systemctl list-units`  

Voir l'état d'un service :  
`systemctl status NOM_SERVICE`  

Lire les traces d'un service :  
`journalctl -f -u NOM_SERVICE`  

## Configuration nginx

Gestion des fichiers `.conf`.  
Répertoire des fichiers de configuration : `/etc/nginx`

### Ré-exécution 

Relance de nginx même : `service nginx reload`
