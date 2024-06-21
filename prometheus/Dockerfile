# Use the official Prometheus base image
FROM prom/prometheus:latest

# Switch to root to change file permissions
USER root

# Add the custom Prometheus configuration file
COPY prometheus.yml /etc/prometheus/prometheus.yml

# Add the entrypoint script and set the appropriate permissions
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

# Ensure the files have the right ownership
RUN chown nobody:nogroup /entrypoint.sh /etc/prometheus/prometheus.yml

# Switch to the nobody user
USER nobody

# Set the entrypoint to the script
ENTRYPOINT ["/entrypoint.sh"]