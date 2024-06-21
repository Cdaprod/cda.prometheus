# Use the official Prometheus base image
FROM prom/prometheus:latest

# Add the custom Prometheus configuration file
COPY prometheus.yml /etc/prometheus/prometheus.yml

# Add the entrypoint script
COPY entrypoint.sh /entrypoint.sh

# Make the entrypoint script executable
RUN chmod +x /entrypoint.sh

# Set the entrypoint to the script
ENTRYPOINT ["/entrypoint.sh"]