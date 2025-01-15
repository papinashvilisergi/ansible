# Ansible Automation for Monitoring Stack

ეს რეპოზიტორია შეიცავს ანსიბლის ფლეიბუქებს და როლებს, რომლის მეშვეობითაც შესაძლებელია მონიტორინგის სტეკის აწევა, რომელიც მოიცავს პრომეთეუსს, ალერტმენეჯერს, გრაფანას, ნოუდ ექსპორტერს და nginx ექსპორტერს, ორ ვირტუალურ მანქანას შორის

## პროექტის მიმოხილვა

1. **VM1 (172.31.100.48)**:
   - Prometheus
   - Alertmanager
   - Node Exporter
   - Nginx Exporter

2. **VM2 (172.31.100.49)**:
   - Grafana
   - Node Exporter
   - Nginx Exporter

### Key Features
- Prometheus scrapes metrics from Node Exporter and Nginx Exporter.
- Alertmanager sends alerts to a Slack channel.
- Grafana visualizes Prometheus data and includes a pre-configured Node Exporter dashboard and a custom dashboard for alerts.
- Nginx is set up as a reverse proxy for Prometheus, Alertmanager, and Grafana.
- All configurations are managed through Ansible roles.

---

## Repository Structure

```bash
ansible/
├── group_vars/
│   └── all.yml        # Global variables
├── inventory.yml      # Ansible inventory file
├── roles/
│   ├── alertmanager/
│   ├── grafana/
│   ├── nginx_exporter/
│   ├── node_exporter/
│   └── prometheus/
├── site.yml           # Playbook to run all roles
└── README.md          # This documentation
