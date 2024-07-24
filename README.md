# NOTE

This is a WIP project. The playbook is not yet complete and it will eventually evolve to a CLI tool written in GO to automate the setup of different environments used by me. 

It will (probably) include the following:
- [x] React Native Environment Setup
- [ ] Go Environment Setup
- [ ] KMP Environment Setup
- [ ] Jira Integration
- [ ] Git/Github Integration



# Ansible Playbook

This playbook is used to install and configure the following services:

1. **Update and upgrade packages**
   - Debian-based systems: Uses `ansible.builtin.apt` to update and upgrade apt packages.
   - macOS: Uses `community.general.homebrew` to update and upgrade brew packages.

2. **Install Node.js**
   - Debian-based systems: Uses `ansible.builtin.apt` to install Node.js.
   - macOS: Uses `community.general.homebrew` to install Node.js.

3. **Install npm**
   - Debian-based systems: Uses `ansible.builtin.apt` to install npm.

4. **Install yarn**
   - Uses `ansible.builtin.command` to install yarn globally via npm.

5. **Install Watchman**
   - Debian-based systems: Uses `ansible.builtin.apt` to install Watchman.
   - macOS: Uses `community.general.homebrew` to install Watchman.

6. **Install Java Development Kit (JDK)**
   - Debian-based systems: Uses `ansible.builtin.apt` to install openjdk-8-jdk.
   - macOS: Uses `community.general.homebrew` to install openjdk.

7. **Install Android Studio dependencies**
   - Debian-based systems: Uses `ansible.builtin.apt` to install various i386 libraries required for Android Studio.

8. **Install Gnu-tar**
   - macOS: Uses `community.general.homebrew` to install gnu-tar.

9. **Download and set up Android Studio**
   - Uses `ansible.builtin.get_url` to download Android Studio.
   - Uses `ansible.builtin.unarchive` to extract Android Studio.
   - Uses `ansible.builtin.lineinfile` to set up environment variables for Android Studio.

10. **Install React Native CLI**
    - Uses `community.general.npm` to install React Native CLI globally.

This playbook ensures that all necessary tools and dependencies are installed and configured for both Debian-based systems and macOS.

## How to Run the Playbook

1. Ensure you have Ansible installed on your system. You can install it using pip:
   ```sh
   pip install ansible
   ```

2. Install the required Ansible Galaxy collection:
   ```sh
   ansible-galaxy collection install community.general
   ```

3. Clone the repository containing the playbook:
   ```sh
   git clone <repository_url>
   cd <repository_directory>
   ```

4. Run the playbook using the following command:
   ```sh
   ansible-playbook -i inventory.ini playbook.yaml
   ```

5. The playbook will execute and install/configure the necessary services as described above.
