# Setup Avahi Daemon on Linux
1. Install avahi daemon
    ```
    apt-get install -y avahi-daemon
    ```
2. Create service file <your_service>.service inside ```/etc/avahi/services``` with the following configuration
    ```
    <?xml version="1.0" standalone='no'?><!--*-nxml-*-->
    <!DOCTYPE service-group SYSTEM "avahi-service.dtd">

    <service-group>

      <name replace-wildcards="yes">HTTP Server %h</name>

      <service>
        <type>_http._tcp</type>
        <port>8000</port>
      </service>

    </service-group>
    ```
3. Restart the daemon to publish the service
    ```
    systemctl restart avahi-daemon
    ```
