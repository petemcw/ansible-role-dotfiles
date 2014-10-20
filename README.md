# Dotfiles Role for Ansible

This role installs an opinionated version of [dotfiles](http://dotfiles.github.io/)
that we use on our servers.

## Requirements

This role requires [Ansible](http://www.ansibleworks.com/) version 1.4 or higher
and the Debian/Ubuntu platform.

## Role Variables

The variables that can be passed to this role and a brief description about
them are as follows:

```yaml
# The name of the user to configure
dotfiles_user: 'admin'

# The user's preferred home directory
dotfiles_home_dir: '/home/admin'

# The user's preferred shell
dotfiles_shell: '/bin/zsh'
```

## Examples

1. Install dotfiles for "admin" user with default shell

    ```yaml
    ---
    # This playbook installs dotfiles

    - name: Apply dotfiles to all nodes
      hosts: all
      roles:
        - { role: dotfiles,
            dotfiles_user: 'admin',
            dotfiles_home_dir: '/home/admin'
          }
    ```

## Dependencies

The following packages may be required for Debian derivatives:

- `git-core`

## License

MIT.
