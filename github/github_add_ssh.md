1. генерируем ключ
```
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```
* -C comment
* -T output_file
* источник https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
* копируем в буфер обмена
    * windows 
    ```
    cat ~/.ssh/id_rsa.pub > /dev/clipboard
    ```
    * linux:
    ```
    cat ~/.ssh/id_rsa.pub | pbcopy
    ```
