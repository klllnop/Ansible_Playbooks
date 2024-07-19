**Ansible Playbook: Check Gateway IP for Docker Containers**

This Ansible playbook is designed to check the gateway IP for Docker containers running on specified hosts. It inspects each Docker container and logs the IP addresses of hosts where the gateway IP matches a specific pattern (172.17.0.1).

**Prerequisites:**

Ansible 2.9+ installed on the control machine

Docker installed on target hosts

SSH access to target hosts with appropriate permissions

**Playbook Details**

**Tasks:**

Get Docker Container IDs:

Retrieves the IDs of all running Docker containers on the target hosts.
Inspect Each Docker Container:

Inspects each Docker container to gather detailed information.
Check for Gateway IP in Output:

Checks if the gateway IP (172.17.0.1) is present in the inspected output.

Write IPs to File on Ansible Control Machine:

Writes the IP addresses of the hosts to a file on the Ansible control machine if the gateway IP matches the specified pattern.

**Variables:**

ansible_host: The IP address or hostname of the target host.

docker_containers.stdout_lines: List of Docker container IDs.

inspect_output.results: Result of the Docker container inspection.

matching_hosts_fact.results: List of hosts with matching gateway IP.
