### Installation von zwei EC2-Instanzen mit unterschiedlichen Security Groups

#### Hier sind beide Instanzen die ich erstellt habe
![Alt text](image-13.png)

#### Hier ist meine Private Instanz
![Alt text](image-14.png)

#### Hier ist mein Webserver
![Alt text](image-15.png)

#### Die Verbindung mit dem Webserver funktioniert
![Alt text](image-16.png)

#### Ich habe mich nun über Instance connect verbunden
![Alt text](image-17.png)

#### Ich konnte meine Private Instanz pingen🤯
![Alt text](image-19.png)

### Erklären Sie in eigenen Worten, wie Sie die zweite Security Group (M346-UGU-Priv-Only) ergänzt haben und wer welchen Zugriff auf die darin liegenden Instanzen hat.

Ich haben die inbound rule "All ICMP - IPv4" hinzugefügt, welche hier ist, um Instanzen pingen zu können

Eine Instanz, mit der Security group M346-UGU-Priv-Only kann von einer Instanz in dem gleichen subnetz gepingt werden.

### Quelle
- [chatGPT](https://chat.openai.com/)
- [AWS documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html)
- [Gitlab](https://gitlab.com/ser-cal/m346/-/blob/main/KN05/KN05.md)