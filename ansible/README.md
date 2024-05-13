# Ansible Controller Scaffolding

Ansible Controller Scaffolding" is a project aimed at streamlining the setup and
configuration process for Ansible controllers. The project focuses on providing
a structured framework or scaffolding that accelerates the deployment of Ansible
controllers, allowing for rapid implementation and scaling of automation tasks
across diverse infrastructure environments. This scaffolding encompasses best
practices, pre-configured templates, and automation scripts to ensure
consistency, efficiency, and reliability in Ansible controller deployments.

## Requirements

1. Install NPM:

```bash
sudo apt update
sudo apt install npm
```

2. Install Python3 required components:

```bash
sudo apt install python3-full
sudo apt install pip
```

## Installation

Follow these steps to install and setup the project:

1. Clone the repository to your local machine:

```bash
git clone git@github.com:ravigehlot/ansible-scaffolding.git
```

2. Navigate to the project directory:

```bash
cd ansible-scaffolding
```

3. Set up a Python virtual environment named `.venv`:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

4. Install pip-tools:

```bash
pip3 install pip-tools
```

5. Compile requirements:

```bash
pip-compile requirements.in
```

6. Install the required Python packages:

```bash
pip3 install -r requirements.txt
```

After following these steps, you should have a fully set up project ready for
development.

## Usage

1. Install VSCode:

```powershell
winget install Microsoft.VisualStudioCode
```

2. Change paths on ansible.code-workspace
   
Visual Studio Code predefined variables do not work here.
Change paths to match your environment.

3. Open VSCode Workspace:

File -> Open Workspace from File...
Open ansible.code-workspace
Click "install" on the Recommendations popup to get those VSCode extensions installed.

## Contributing

Contributions are what make the open-source community such an amazing place to
learn, inspire, and create. Any contributions you make are **greatly
appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License. See the `LICENSE` file for more
details.
