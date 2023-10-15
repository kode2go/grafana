# grafana

Here's how to use Grafana as a browser-based GUI for InfluxDB:

Install InfluxDB: Make sure you have InfluxDB installed and running. You've mentioned earlier that you have InfluxDB up and running.

Install Grafana: Install Grafana on your Ubuntu system. You can do this by adding the Grafana APT repository and installing the Grafana package:

bash
Copy code
```
sudo apt-get install -y software-properties-common
sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
sudo apt-get update
sudo apt-get install grafana
```

Start and Enable Grafana Service:
Once installed, start the Grafana service and enable it to start at boot:

bash
Copy code
```
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

Access Grafana Web Interface:
Open a web browser and access the Grafana web interface by entering the following URL:

arduino
Copy code
```
http://localhost:3000
```
Grafana runs by default on port 3000. You should see the Grafana login page.

Log In to Grafana:
Log in with the default credentials:

```
Username: admin
Password: admin
```

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

```
sudo service grafana-server start
```

```
http://172.18.0.2:3000
```

# Setup

To configure InfluxDB as a data source in Grafana and connect it to your InfluxDB database (created with Python), you can use the following settings. The specific values you need to replace are noted in the comments:

In Grafana:

Click on the gear icon (⚙️) in the left sidebar to open the "Configuration" menu.
Select "Data Sources."
Click the "Add data source" button.
Configure the InfluxDB Data Source:

Choose "InfluxDB" as the data source type.
Fill in the necessary connection details:

Name: This can be any name you choose, e.g., "My InfluxDB."
Default: Check this option to set this data source as the default.
In the "HTTP" section:

URL: Enter the URL to your InfluxDB server. If you are running Grafana and InfluxDB on the same WSL instance, you can use the IP address you found earlier and port 8086. For example: http://localhost:8086
In the "Authentication" section:

Access: Choose the appropriate access method based on your InfluxDB setup.
Token: If your InfluxDB uses tokens for authentication, provide your token here.
In the "InfluxDB Details" section:

Database: Use the database name you created with Python, which in your case is 'esp02'.
User: If you have set up a user with specific permissions for this database, enter the username here.
Password: If you are using a username and password for authentication, enter the password here.
Click "Save & Test" to ensure the connection is successful.
