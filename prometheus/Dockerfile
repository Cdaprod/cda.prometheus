# Use the official Prometheus base image
FROM prom/prometheus:latest

# Switch to root to change file permissions
USER root

# Add the custom Prometheus configuration file
COPY prometheus.yml /etc/prometheus/prometheus.yml

# Add the entrypoint script and set the appropriate permissions
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

# Create the cda user and set ownership if it doesn't already exist
RUN id -u cda &>/dev/null || useradd -m cda
RUN chown -R cda:cda /entrypoint.sh /etc/prometheus

# Switch to the cda user
USER cda

# Set the entrypoint to the script
ENTRYPOINT ["/entrypoint.sh"]