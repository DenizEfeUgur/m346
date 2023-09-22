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
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCv0e6xuTLm5z6OqUL1E1z9fLc1ii6XZ1MAbKf1jthumJtA+MfTAAkXTxjNCwlBw9uvC8OExImH+WiNp1j/WI1eMVIn9Ee9cTVlQMKQucBRJQimcWR+rRICvzDobYv+y3En546xbWeVvbC0JbmLpB9UE/tGJ2KljTSCBp0k+Ki3xcDmkVA0nLz+oYFEtH6WDpJRHr8gJlwesf0Tf6iUGVpJzUIIyWlV1yBrRWVT4+Zao3bqmRVhgNOaBjuP1mzL1pwn1ZvLwD0bMEPMjQG9ynClygYrSXlWUQOdmO/oGlQx9nMdN5e24bQu/COLNvufVHBGhBnHJs48+BehwSjxDtEh imported-openssh-key
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