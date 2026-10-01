---
title: Hakoniwa
summary: Process isolation for Linux using namespaces, resource limits, cgroups, landlock and seccomp.
date: 2025-06-20
repo: https://github.com/souk4711/hakoniwa
featured: true
draft: false
---

Process isolation for Linux using namespaces, resource limits, cgroups, landlock and seccomp.
It works by creating a new, completely empty, mount namespace where the root is
on a tmpdir, and will be automatically cleaned up when the last process exits.

It uses the following techniques:

- **Linux namespaces:** Create an isolated environment for the process.
- **MNT namespace + pivot_root:** Create a new root file system for the process.
- **NETWORK namespace + pasta**: Create a new user-mode networking stack for the process.
- **setrlimit:** Limit the amount of resources that can be used by the process.
- **cgroups + systemd:** Limit process resources using cgroup v2.
- **landlock:** Restrict ambient rights (e.g. global filesystem access) for the process.
- **seccomp:** Restrict the system calls that the process can make.

It can help you with:

- Compile source code in a restricted sandbox.
- Run browsers, or proprietary softwares in an isolated environment.
- Chroot into rootfs, install GUI apps, and launch them.
