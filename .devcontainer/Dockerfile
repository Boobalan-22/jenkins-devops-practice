# Use Ubuntu as base
FROM ubuntu:22.04

# Install necessary tools
RUN apt-get update && apt-get install -y \
    openjdk-17-jdk \
    curl \
    gnupg2 \
    lsb-release \
    sudo

# Add Jenkins key and repo
RUN curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null && \
    echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null

# Install Jenkins
RUN apt-get update && apt-get install -y jenkins

# Expose Jenkins port
EXPOSE 8080

# Default command to run Jenkins
CMD ["bash"]
