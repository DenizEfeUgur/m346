cloud-init file erklären

``` yaml
#cloud-config
users:
  - name: ubuntu
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: users, admin
    home: /home/ubuntu
    shell: /bin/bash
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC0WGP1EZykEtv5YGC9nMiPFW3U3DmZNzKFO5nEu6uozEHh4jLZzPNHSrfFTuQ2GnRDSt+XbOtTLdcj26+iPNiFoFha42aCIzYjt6V8Z+SQ9pzF4jPPzxwXfDdkEWylgoNnZ+4MG1lNFqa8aO7F62tX0Yj5khjC0Bs7Mb2cHLx1XZaxJV6qSaulDuBbLYe8QUZXkMc7wmob3PM0kflfolR3LE7LResIHWa4j4FL6r5cQmFlDU2BDPpKMFMGUfRSFiUtaWBNXFOWHQBC2+uKmuMPYP4vJC9sBgqMvPN/X2KyemqdMvdKXnCfrzadHuSSJYEzD64Cve5Zl9yVvY4AqyBD aws-key       
ssh_pwauth: false
disable_root: false 
package_update: true
packages:
  - curl 
  - wget 

```

**name: ubuntu:** Der Benutzername ist "ubuntu".
**sudo: ALL=(ALL) NOPASSWD:ALL:** Der Benutzer "ubuntu" kann alle Befehle mit sudo ohne Passwort ausführen. Dies ist eine sudo-Berechtigungsregel.
**groups: users, admin:** Der Benutzer ist Mitglied der Gruppen "users" und "admin".
**home: /home/ubuntu:** Das Heimatverzeichnis des Benutzers ist "/home/ubuntu".
**shell: /bin/bash:** Die Standard-Shell des Benutzers ist "/bin/bash".
**ssh_authorized_keys:** Hier werden die SSH-öffentlichen Schlüssel für den Benutzer "ubuntu" angegeben, die es ihm ermöglichen, sich ohne Passwortanforderung per SSH anzumelden.

``` yaml
ssh_pwauth: false
```
Diese Zeile legt fest, dass die Passwortauthentifizierung für SSH deaktiviert ist. Benutzer müssen sich per SSH mit einem Schlüsselpaar anmelden.

``` yaml
disable_root: false
```
Hier wird festgelegt, dass die Root-Anmeldung nicht deaktiviert ist. Der Root-Benutzer kann sich anmelden.


``` yaml
package_update: true
```
Diese Zeile gibt an, dass ein Paketupdate durchgeführt werden soll. Dies bedeutet, dass das System nach Updates für installierte Pakete suchen und sie aktualisieren wird.


``` yaml
packages:
  - curl
  - wget
```
In diesem Abschnitt werden die Pakete aufgelistet, die installiert werden sollen. Hier werden die Pakete "curl" und "wget" aufgeführt, die installiert werden, wenn das System gestartet wird.