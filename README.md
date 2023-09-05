# How to install Prometheus Client
Important: This is a work in progress.

Login to targer server by SSH:

ssh root@targer_server 

Clone git into the server:

git clone https://github.com/boohere2023/InstallPrometheus.git

This script downloads the files in the current directory. You could change this.

Grant permisstion for scripts files:

sudo chmod 774 /IntstallPrometheus/scripts/install-node-exporter.sh
sudo chmod 774 /IntstallPrometheus/scripts/install-sql-exporter.sh

Run scripts for installation Node_Exporter

scripts/install-node-exporter.sh

Run scripts for installation SQL_Exporter

scripts/install-sql-exporter.sh

type root sql password when the promps require







 Rewrite scripts so one could start it with sudo ./full_installation instead of doing sudo before script
 Write uninstallation scripts (both full uninstall and uninstallation of individual components)
 Add optional installation for mysqld_exporter and postgresql_exporter
Any suggestions and contributions are welcome.

If you're new
I have written few Prometheus instructions that you may or may not find useful:

How to Write Rules for Prometheus
How to Install Alertmanager on Ubuntu 16.04
How to Install MySQL Exporter for Prometheus 2.0 on Ubuntu 16.04
If you find any mistake, or suggestion for enhancement that would be great.

How to Use This?
Whether you are using this to install individual components or the full app, it is best to start scripts from the cloned repository. If you copy scripts anywhere else, the behaviour of the scripts is not guaranteed. Note that these scripts will add Prometheus and other utilities to systemd as services, and enable the by default.

Full Installation
Full installation will install the following:

Prometheus
Alertmanager
Node Exporter
Blackbox Exporter
Grafana
Scripts have many sudos, so before you start the full installation, do:

sudo pwd
just to make sure, sudo in scripts won't interrupt you. After that you can run script as:

./full_installation.sh
Or run script as a root user.

Installation of Individual Components
Same rules apply as for the full installation before you try to execute other scripts:

sudo pwd
just to make sure, sudo in scripts won't interrupt you. And to install individual components, use:

Node Exporter: ./node.sh
SQL Exporter: ./blackbox.sh

