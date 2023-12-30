# Commands

## Secret

Create a secret using specified subcommand.

Available Commands:
  docker-registry   Create a secret for use with a Docker registry
  generic           Create a secret from a local file, directory, or literal value
  tls               Create a TLS secret

### Encoding text
values should be encoded. To encode a text using unix command
```
echo -n 'my-text' | base64
```

to display secret value, it should be decoded using
```
echo -n 'encoded-text' | base64 --decode
```

### Usage:
```
kubectl create secret [flags] [options]
```

## secret generic
Create a secret based on a file, directory, or specified literal value.
A single secret may package one or more key/value pairs.

### Examples:

Create a new secret named my-secret with keys for each file in folder bar
```
kubectl create secret generic my-secret --from-file=path/to/bar
```

Create a new secret named my-secret with specified keys instead of names on disk
```
kubectl create secret generic my-secret --from-file=ssh-privatekey=path/to/id_rsa
--from-file=ssh-publickey=path/to/id_rsa.pub
```

Create a new secret named my-secret with key1=supersecret and key2=topsecret
```
kubectl create secret generic my-secret --from-literal=key1=supersecret --from-literal=key2=topsecret
```

Create a new secret named my-secret using a combination of a file and a literal
```
kubectl create secret generic my-secret --from-file=ssh-privatekey=path/to/id_rs --from-literal=passphrase=topsecret
```

Create a new secret named my-secret from env files
```
kubectl create secret generic my-secret --from-env-file=path/to/foo.env --from-env-file=path/to/bar.env
```

