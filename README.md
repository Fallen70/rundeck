# Premiére installation

Mettre a jour l'inventory avec le nom de la machine qui va héberger rundeck sous `[rundeck_servers]`.

Dans le dossier files renommer le dossier rundeck pour correspondre au nom de la machine  qui héberge rundeck.

## FIchier dans files a modifier

 * etc/rundeck/realm.properties

Positionner les mots de passe admin et ansible
Les instructions pour créer un mot de passe sont décrites dans le fichier


 * etc/pki/tls/certs

Déposer le fichier .crt pour le certificat tls

 * etc/pki/tls/private

Déposer le fichier .key pour le certificat tls

 * ssh_pub/

il faut créer la clef ssh permettant a rundeck de ce connecter aux différents noeud
### Création de la clef (sans passphrase)
```shell
cd ansible
[user@localhost ansible]$ ssh-keygen                                                                                                                                                          
Generating public/private rsa key pair.                                                                                                                                                       
Enter file in which to save the key (/home/user/.ssh/id_rsa): files/**rundeck**/ssh_pub/id_rsa                                                                                              
Enter passphrase (empty for no passphrase):                                                                                                                                                   
Enter same passphrase again:                                                                                                                                                                  
Your identification has been saved in roles/rundeck/files/ssh_pub/id_rsa.                                                                                                                     
Your public key has been saved in roles/rundeck/files/ssh_pub/id_rsa.pub.                             
```

La clef privée est a conserver pour plus tard

 * var/rundeck/projects/mon-projet/etc/project.properties

Pour modifier le nom du projet il faut modifier le paramétre `project.name`


#TODO

revoir partie ansible galaxy
