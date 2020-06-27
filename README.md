# hcloud_kube

A simple collection of scripts for bootstrapping a simply k8s cluster on
[Hetzner Cloud](https://www.hetzner.com/cloud).

## Dependencies

You'll need:

- [hcloud](https://github.com/hetznercloud/cli)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- Other pretty standard linux utils (Bash, SSH, etc)

## Usage

1. Create a new project
2. Create a new API token in the project
3. Create a local environment variable `HCLOUD_TOKEN` with the value of the token.

   ```bash
   $ export HCLOUD_TOKEN=<api token>
   ```

4. Run the hcloud script

   ```bash
   $ ./hcloud_kube
   ```

5. You can then copy the kube admin config

   ```bash
   $ cp /tmp/hcloud_kube/admin.conf ~/.kube/config
   ```

6. You probably also want to save the generated ssh keys (in case you want to
   ssh in later)

   ```bash
   $ cp /tmp/hcloud_kube/provision_key* ~
   ```

## Configuration

Command line options

- `-t TYPE` (default: `cx21`)

  The hetzner instance type for each node.

- `-n COUNT` (default: `1`)

  The number of hetzner workers to provision.

For additional configuration, dive in, and edit the script - it's meant to be
built upon.

## References

https://community.hetzner.com/tutorials/install-kubernetes-cluster

## License

Because this tool is short and sweet, it is hereby released into the public
domain. Do whatever you want.
