**Ansible Playbook README**

**Description:**

This Ansible playbook automates the creation of a bash script designed to execute specific actions when an instance undergoes reboot, power-off, or termination. Additionally, it integrates with Telegram to send notifications about these events. The playbook is divided into several roles to streamline the process: pre-check, install jq, install script, and install service.

**Roles:**

1. **Pre-Check:**

   - This role verifies prerequisites and ensures the system meets the necessary requirements before proceeding with the installation.

2. **Install jq:**

   - Installs the jq tool, a lightweight and flexible command-line JSON processor, which is used for parsing JSON data within the playbook.

3. **Install Script:**

   - Creates and configures the bash script responsible for executing actions during instance events (reboot, power-off, termination). It integrates with jq for JSON parsing and constructs appropriate commands to handle each event.

4. **Install Service:**
   - Sets up the service responsible for executing the bash script during instance events. It configures the service to run automatically upon system startup and monitors the specified events to trigger the corresponding actions.

**Usage:**

1. Ensure Ansible is installed on the control node.
2. Update the inventory file with the details of target hosts.
3. Customize playbook variables such as Telegram API token, chat ID, and any other configuration options as needed.
4. Run the playbook using the command: `ansible-playbook playbook.yml`.

**Customization:**

- Modify playbook variables (`vars` section) in `playbook.yml` to match your environment and preferences.
- Adjust the content and behavior of the bash script (`template/script.sh.j2`) to suit your requirements.
- Update Telegram API token and chat ID in the script to enable notifications to the desired recipient.

**Note:**

- Ensure proper permissions and security measures are in place for handling sensitive information such as API tokens.
- Test the playbook thoroughly in a controlled environment before deploying to production to avoid unexpected behavior.
- Regularly review and update the playbook to incorporate any changes or improvements in your environment or requirements.

**Author:**

[Your Name/Team/Organization]

**Contact:**

[Your Contact Information]

**License:**

[Specify the license under which this playbook is distributed, e.g., MIT License, GNU General Public License, etc.]
