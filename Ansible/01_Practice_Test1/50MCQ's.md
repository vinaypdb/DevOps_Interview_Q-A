### 🧠 Ansible Multiple Choice Questions (MCQs)

1. What is Ansible primarily used for?

* A. Data analytics
* B. Web development
* C. Configuration management and automation
* D. Video editing

2. Which language does Ansible use for playbooks?

* A. JSON
* B. XML
* C. YAML
* D. INI

3. What protocol does Ansible use to communicate with Linux hosts?

* A. RDP
* B. SSH
* C. FTP
* D. HTTP

4. What is a module in Ansible?

* A. A container image
* B. A package installer
* C. A unit of work that performs tasks
* D. A user interface component

5. What is the default inventory file location in Ansible?

* A. /etc/ansible/hosts
* B. /usr/local/ansible/inventory
* C. \~/.ansible/hosts
* D. /opt/ansible/inventory

6. What is a playbook in Ansible?

* A. A shell script
* B. A JSON API
* C. A YAML file with automation steps
* D. A database dump

7. Which command runs an Ansible playbook?

* A. ansible
* B. ansible-playbook
* C. run-playbook
* D. execute-ansible

8. Which of the following is NOT an Ansible module type?

* A. yum
* B. apt
* C. bash
* D. service

9. Which command encrypts files using Ansible Vault?

* A. ansible encrypt
* B. vault encrypt
* C. ansible-vault encrypt
* D. ansible-safe encrypt

10. What is an Ansible handler?

* A. A variable file
* B. A background service
* C. A task triggered by notify
* D. A plugin

11. Which Jinja2 structure is used for variable substitution?

* A. {{ variable }}
* B. (( variable ))
* C. << variable >>
* D. $variable$

12. What does `gather_facts` do?

* A. Gathers logs
* B. Collects system information
* C. Installs packages
* D. Verifies checksums

13. What is a role in Ansible?

* A. A job title
* B. A task dependency
* C. A structured collection of playbook content
* D. An environment

14. Which command shows module documentation?

* A. ansible-module --help
* B. ansible-doc
* C. ansible --manual
* D. ansible-help

15. Which module installs packages using `yum`?

* A. yum
* B. apt
* C. pip
* D. install

16. What is `with_items` used for?

* A. Conditional branching
* B. Looping through a list
* C. Template generation
* D. File creation

17. What type of file is used for templating in Ansible?

* A. .conf
* B. .j2
* C. .tpl
* D. .tmpl

18. What is Ansible Galaxy?

* A. A cloud provider
* B. A CLI debugger
* C. A public role repository
* D. A YAML linter

19. Which variable precedence is highest?

* A. Inventory file
* B. Playbook vars
* C. Extra vars
* D. Defaults

20. Which module manages services like nginx or httpd?

* A. service
* B. systemd
* C. daemon
* D. supervisor

21. What is the use of `become: true`?

* A. Switches host
* B. Enables SSH
* C. Runs as root or sudo
* D. Starts background task

22. Which module is used for file manipulation?

* A. copy
* B. template
* C. fetch
* D. file

23. How are variables accessed in a Jinja2 template?

* A. \$var
* B. \[\[ var ]]
* C. {{ var }}
* D. <% var %>

24. How do you comment in a YAML file?

* A. //
* B. #
* C. <!-- -->
* D. --

25. What happens if a task fails and `ignore_errors` is set to true?

* A. Task retries
* B. Playbook stops
* C. Error is ignored and playbook continues
* D. Host reboots

26. Which module is used to clone Git repositories?

* A. vcs
* B. version
* C. git
* D. scm

27. What file defines default values in a role?

* A. vars/main.yml
* B. defaults/main.yml
* C. env.yml
* D. playbook.yml

28. What does `ansible-playbook --check` do?

* A. Executes the playbook
* B. Syntax checks only
* C. Simulates changes without applying
* D. Reboots system

29. How do you set environment variables in a playbook?

* A. env\_vars
* B. set\_env
* C. environment
* D. export

30. What plugin handles output formatting?

* A. stdout\_callback
* B. log\_filter
* C. print\_output
* D. ui\_formatter

31. What is the default callback plugin for human-readable output?

* A. json
* B. minimal
* C. default
* D. yaml

32. What does `serial` in a playbook control?

* A. Timeout
* B. Number of retries
* C. Number of hosts to run in parallel
* D. Execution order of tasks

33. What is `notify` used for in Ansible?

* A. Send alerts
* B. Call handlers
* C. Start services
* D. Register variables

34. Which module creates directories or changes permissions?

* A. file
* B. copy
* C. blockinfile
* D. stat

35. What is the purpose of `register` in a task?

* A. Defines a hostname
* B. Stores task output in a variable
* C. Starts another task
* D. Triggers debug

36. Which module waits for a port to be open?

* A. wait
* B. check\_port
* C. socket
* D. netstat

37. What is the extension of Ansible Vault-encrypted files?

* A. .yaml
* B. .enc
* C. .vault
* D. Any extension

38. How do you loop over key-value pairs?

* A. with\_items
* B. with\_dict
* C. with\_pairs
* D. loop\_dict

39. What tool tests roles locally with Docker or Vagrant?

* A. Testinfra
* B. Molecule
* C. Kitchen
* D. CI Runner

40. Which Ansible file manages configuration like forks and retry behavior?

* A. ansible.cfg
* B. config.yml
* C. settings.yaml
* D. inventory.ini

41. Which parameter prevents a task from being executed again?

* A. when
* B. creates
* C. only\_if
* D. block

42. How can you check the version of Ansible?

* A. ansible -version
* B. ansible -v
* C. ansible --version
* D. ansible version

43. Which plugin helps write logs to a file?

* A. stdout
* B. logging
* C. file\_callback
* D. log\_aggregator

44. What is the use of `block` in playbooks?

* A. Group multiple tasks
* B. Register handlers
* C. Import roles
* D. Apply filters

45. What is dynamic inventory in Ansible?

* A. Hand-written IP list
* B. Auto-generated host list from APIs
* C. Host variables only
* D. Static inventory with tags

46. Which file defines custom facts?

* A. facts.yml
* B. inventory.ini
* C. /etc/ansible/facts.d/\*.fact
* D. vars/main.yml

47. What is the default number of forks in Ansible?

* A. 1
* B. 2
* C. 5
* D. 10

48. What plugin runs tasks concurrently?

* A. async
* B. fork
* C. parallel
* D. batch

49. Which module waits until a condition is met?

* A. wait\_for
* B. poll
* C. test
* D. delay

50. Which command executes an ad-hoc task on one host?

* A. ansible-run
* B. ansible-host
* C. ansible
* D. play-task
