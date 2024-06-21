# Use the official Prometheus base image
FROM prom/prometheus:latest

# Switch to root to change file permissions
USER root

# Add the custom Prometheus configuration file
COPY prometheus.yml /etc/prometheus/prometheus.yml

# Add the entrypoint script and set the appropriate permissions
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

# Switch back to the default Prometheus user (nobody)
USER nobody

# Set the entrypoint to the script
ENTRYPOINT ["/entrypoint.sh"]