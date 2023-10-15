# grafana

Here's how to use Grafana as a browser-based GUI for InfluxDB:

Install InfluxDB: Make sure you have InfluxDB installed and running. You've mentioned earlier that you have InfluxDB up and running.

Install Grafana: Install Grafana on your Ubuntu system. You can do this by adding the Grafana APT repository and installing the Grafana package:

bash
Copy code
sudo apt-get install -y software-properties-common
sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
sudo apt-get update
sudo apt-get install grafana
Start and Enable Grafana Service:
Once installed, start the Grafana service and enable it to start at boot:

bash
Copy code
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
Access Grafana Web Interface:
Open a web browser and access the Grafana web interface by entering the following URL:

arduino
Copy code
http://localhost:3000
Grafana runs by default on port 3000. You should see the Grafana login page.

Log In to Grafana:
Log in with the default credentials:

Username: admin
Password: admin
You will be prompted to change the password upon your first login.

Configure InfluxDB Data Source:
After logging in, you need to configure InfluxDB as a data source in Grafana. Follow these steps:

Click on the gear icon (⚙️) in the left sidebar to open the "Configuration" menu.
Select "Data Sources."
Click the "Add data source" button.
Choose "InfluxDB" as the data source type.
Fill in the necessary connection details for your InfluxDB server (host, port, and credentials).
Click "Save & Test" to ensure the connection is successful.
Create Dashboards:
Once you've configured InfluxDB as a data source, you can start creating dashboards in Grafana to visualize and explore your InfluxDB data.
