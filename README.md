# ansible_role_ensure_traefik_basic_auth_middleware

[![Validate infrastructure as code](https://github.com/garliclabs/ansible_role_ensure_traefik_basic_auth_middleware/actions/workflows/validation.yml/badge.svg)](https://github.com/garliclabs/ansible_role_ensure_traefik_basic_auth_middleware/actions/workflows/validation.yml)

This role creates basic auth middleware for traefik on a given kubernetes.  

## Requirements

kubectl, kubernetes

## Role Variables

**traefik_basic_auth_kubeconfig:** Path to the kubeconf of the kubernetes you want to configure

```yml
traefik_basic_auth_items: []
  # - secretName: nginx-basic-auth-secret
  #   namespace: default
  #   middlewareName: nginx-basic-auth
  #   state: "present"
  #   username: 
  #   password: 
  #   hostname: "nginx.example.com"
  #   serviceName: nginx
  #   servicePort: 80
```

## Development

### Linting & static security analyser

Both the linter and the static security analyser are running on each push on the github actions pipeline.  

* As linter [ansible-lint](https://ansible.readthedocs.io/projects/lint/) is used. For installation documentation see [ansible lint installing](https://ansible.readthedocs.io/projects/lint/)
  * Just run `ansible-lint`

* To check if there are any passwords, tokens... hardcoded, [kics](https://kics.io/index.html) is used to ensure a secure IaC repository.  
  * Run it locally `docker run -t -v $PWD:/path checkmarx/kics:latest scan -p /path -o "/path/"`

## Dependencies

* The server this role is executed need to have kubectl with a connection to the kubernetes you want to configure

## License

GNU General Public License version 3
