### Auftrag B

#### Zuerst habe ich die YAML-file angepast
 yamlfile:
``` yaml
#cloud-config
users:
  - name: IhrBenutzername
    sudo: yes
    groups: ugur
    home: /home/ugur
    shell: /bin/bash
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCnfG9V8k3OmKr7v10/mrjJ+rjbRBYJkXXDvmkjPqaNPQDjB1uCkt7ylY0W0UUEPLy2kbcT2pUgm4iy+FbS5U2y5wi32x9GaTJ76fQqtcbcrlBqnmfUNfR1mFio32OU8YagfCJSPEQ48Krws6TneSKa8+BYKACZ/L+Xb3Udn3wGk9maQyW7jxmtHG5wHcZXGagG9+isrkS8Yy9/FwxY/KyEytvTnFlAxMYsXXF6/njuVT5CXv85B0JT7Cuc6uZY5mpTdeyp6dKHYi0rs4wQnBrnGZLeFP9C+kVoe1ZvfSa+468dsW7Kk3besU6kkzso53jP3cNVQaB+I8ikicUqQKB
disable_root: false
package_update: true  
packages:
  - apache2
  - mysql-server
  - php
  - openssh-server
  - curl

write_files:
  - content: |
      <?php phpinfo(); ?>
    path: /var/www/html/info.php
    permissions: '0644'
  - content: |
      <?php
      $ihrname = "ugur";
      ?>

      <html>
      <head>
      <title><?php echo $ihrname; ?></title>
      </head>
      <body>
      <h1>A Picture of me :)</h1>
      <br />
      <img src="https://kn04bucket.s3.amazonaws.com/WIN_20221205_16_20_50_Pro.jpg" alt="Bild aus S3-Bucket">
      </body>
      </html>
    path: /var/www/html/test.php
    permissions: '0644'
runcmd:
  - sudo systemctl start apache2  
  - sudo systemctl enable apache2
```

#### Dann habe ich eine EC2 Instance aufgesetzt, mit der Cloud-init file
![Alt text](image-4.png)

#### Und hier ist das Ergebnis 💥
![Alt text](image-3.png)

### Quelle
- [gitlab](https://gitlab.com/ser-cal/m346/-/blob/main/KN04/KN04.md)
- [chatGPT](https://chat.openai.com/)
  