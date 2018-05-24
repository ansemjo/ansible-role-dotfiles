# Ansible role: ansemjo.dotfiles

Applies dotfiles in [`https://github.com/ansmejo/dotfiles`](https://github.com/ansemjo/dotfiles)
as an Ansible role. Use with a simple playbook like:

```
#!/usr/bin/env ansible-playbook
---
- name: configure dotfiles
  hosts: all
  become: true
  roles:
    - ansemjo.dotfiles
```

## Configuration

- `dotfiles_remote` is the remote repository containing (a fork of) the dotfiles
- `dotfiles_local` is the directory in the filesystem where they are checked out
- `dotfiles_links` is an array of symbolic links to create in the filesystem, where:
  - `file` is a relative link within the repository
  - `link` is the path of a symbolic link to that file
  - `debian` is an additional symbolic link for Debian-based systems

By default, the [repository](https://github.com/ansemjo/dotfiles) on GitHub is used
and the files are checked out in `/usr/local/etc/dotfiles`. Symbolic links are created
for the `bashrc`, `vimrc` and `gitconfig`.
