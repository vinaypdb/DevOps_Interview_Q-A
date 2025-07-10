### ✅ Ansible MCQ Answer Key with Explanations

1. C — Ansible is used for configuration management, application deployment, and automation.
2. C — Playbooks in Ansible are written in YAML.
3. B — SSH is the default protocol Ansible uses to connect to remote Linux systems.
4. C — A module in Ansible is a standalone script that performs a specific task.
5. A — The default static inventory file is located at /etc/ansible/hosts.
6. C — A playbook is a YAML file that describes tasks to be run on hosts.
7. B — The `ansible-playbook` command is used to execute playbooks.
8. C — 'bash' is not an Ansible module; 'yum', 'apt', and 'service' are.
9. C — `ansible-vault encrypt` is used to encrypt files with Ansible Vault.
10. C — Handlers are special tasks triggered by the `notify` directive.
11. A — Jinja2 templates use `{{ variable }}` for substitution.
12. B — `gather_facts` collects system info like memory, IP, OS.
13. C — Roles are a structured way of organizing playbooks and tasks.
14. B — `ansible-doc` shows documentation on modules.
15. A — The `yum` module is used for package installation on RHEL-based systems.
16. B — `with_items` is used to loop over a list in a task.
17. B — Templates in Ansible use the `.j2` extension (Jinja2).
18. C — Ansible Galaxy is a repository for community-contributed roles.
19. C — Extra vars have the highest precedence in Ansible variable hierarchy.
20. A — The `service` module is used to manage system services.
21. C — `become: true` runs tasks with elevated privileges (sudo).
22. D — The `file` module is used to create, delete, change permissions of files/dirs.
23. C — Variables are referenced in Jinja2 using `{{ var }}` syntax.
24. B — Comments in YAML start with `#`.
25. C — `ignore_errors: true` allows playbook to continue if the task fails.
26. C — The `git` module is used to clone repositories.
27. B — `defaults/main.yml` defines default values in a role.
28. C — The `--check` flag simulates changes without applying them.
29. C — `environment` is the key used to set environment variables in tasks.
30. A — `stdout_callback` controls the formatting of Ansible output.
31. C — The `default` callback plugin gives human-readable output.
32. C — `serial` limits how many hosts run the playbook in parallel.
33. B — `notify` is used to trigger a handler.
34. A — The `file` module can manage permissions and directories.
35. B — `register` captures a task's output into a variable.
36. A — `wait` and `wait_for` can pause until a port is open.
37. D — Ansible Vault files can use any extension; no restriction.
38. B — `with_dict` is used to loop over key-value pairs.
39. B — Molecule is used for testing Ansible roles with Docker/Vagrant.
40. A — `ansible.cfg` controls core configurations like retries, forks, timeouts.
41. B — `creates` prevents a task from running if the specified file exists.
42. C — Use `ansible --version` to check the Ansible version.
43. C — `file_callback` is a plugin used to log output to a file.
44. A — `block` is used to group multiple related tasks together.
45. B — Dynamic inventory is generated using external APIs or scripts (e.g., AWS EC2).
46. C — Custom facts are stored in `/etc/ansible/facts.d/` as `.fact` files.
47. D — By default, Ansible uses 5 forks for parallel execution.
48. A — `async` module allows running tasks asynchronously.
49. A — `wait_for` waits for conditions like port open or file created.
50. C — `ansible` command is used for ad-hoc commands on remote hosts.
