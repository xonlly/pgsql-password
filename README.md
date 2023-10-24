# PGSql password encoder

Vous pouvez parser votre mot de passe pgsql simplement avec le bash suivant.

```bash
#!/bin/bash

read -p "Entrez le mot de passe: " pwd

pwd=$(echo $pwd | sed -e 's/@/%40/g;s/\//%2F/g;s/&/%26/g;s/?/%3F/g;s/!/%21/g;s/#/%23/g;s/\$/%24/g;s/%/%25/g;s/^/%5E/g;s/*/\\*/g;s/(/%28/g;s/)/%29/g;s/-/%2D/g;s/_/%5F/g;s/\\+/%2B/g;s/=/%3D/g;s/{/%7B/g;s/}/%7D/g;s/|/%7C/g;s/:/%3A/g;s/;/%3B/g;s/,/%2C/g;s/\\./%2E/g;s/</%3C/g;s/>/%3E/g;s/~/%7E/g')

echo "Le mot de passe converti est: $pwd"
```
