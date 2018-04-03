# Vagrant Redash
> run
  ```shell
  vagrant provision
  vagrant up
  ```

## Errors
  Vagrant doesn't include ifupdown anymore so you need to fix it with:

  ```shell
    Vagrant ssh
    # Inside vagrant do
    sudo apt-get update
    sudo apt-get install -y ifupdown
    # Exit and do
    Vagrant reload.
  ```
