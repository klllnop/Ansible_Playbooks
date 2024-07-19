**Ansible Playbook: Check Gateway IP for Docker Containers**

This Ansible playbook is designed to check the gateway IP for Docker containers running on specified hosts. It inspects each Docker container and logs the IP addresses of hosts where the gateway IP matches a specific pattern (172.17.0.1).

**_NOTE: YOU CAN CHANGE THE IP ADDRESS TO LOOKUP INSIDE THE PLAYBOOK FILE_**

**Prerequisites:**

- Ansible 2.9+ installed on the control machine

- Docker installed on target hosts

- SSH access to target hosts with appropriate permissions

**Playbook Details**

**Tasks:**

- Get Docker Container IDs

- Inspect Each Docker Container:

- Check for Gateway IP in Output:

- Writes the IP addresses of the hosts to a file on the Ansible control machine if the gateway IP matches the specified pattern.

**Variables:**

- ansible_host: The IP address or hostname of the target host.

- docker_containers.stdout_lines: List of Docker container IDs.

- inspect_output.results: Result of the Docker container inspection.

- matching_hosts_fact.results: List of hosts with matching gateway IP.

**Usage**

1- Clone the repository and enter on his folder

2- Update the copy task in the playbook with the desired file path:

copy:

  content: "{{ host_ip }}"

  dest: /path/to/your/directory/extracao_docker.txt
  
3- Run the playbook with the command -> ansible-playbook -i your_hosts_inventory_file check_docker_networks.yml

**_AUTHOR: MARCO SIMÕES_**
