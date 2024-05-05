# ansible-studies

Ansible studies. Just for fun.

```bash
# Create docker environment
docker-compose up --build -d
docker-compose logs -f # Wait for message "Host XXX is ready" for all containers

# Access bash of management host (the unique host that has ansible installed)
docker-compose exec management_host bash
  > ssh-keygen # (Press 'Enter' for all prompts)
  > ssh-copy-id -o StrictHostKeyChecking=no root@host001 # (Enter 'verysecurepassword' for password prompt)
  > ssh-copy-id -o StrictHostKeyChecking=no root@host002 # (Enter 'verysecurepassword' for password prompt)
  > ssh-copy-id -o StrictHostKeyChecking=no root@host003 # (Enter 'verysecurepassword' for password prompt)
  > ansible-playbook -i inventary_hosts.txt playbook.yaml

# Access the apps in each host
curl http://localhost:3001 # nginx
curl http://localhost:3002 # apache2
curl http://localhost:3003 # apache2
```
