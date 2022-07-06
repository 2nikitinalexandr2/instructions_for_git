for user in ansible root
> do
>  for os in ubuntu centos
>  do
>    for instace in 1 2 3
>    do
>      sshpass -f password.txt ssh-copy-id -o StrictHostKeyChecking=no ${user}@${os}${instace}
>    done
>  done 
> done

```
for user in ansible root; do for os in ubuntu centos; do  for instace in 1 2 3; do sshpass -f password.txt ssh-copy-id -o StrictHostKeyChecking=no ${user}@${os}${instace}; done; done; done
```