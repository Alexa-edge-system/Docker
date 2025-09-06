Here’s a clean **README.md** you can use to document your Ubuntu Docker setup script:

````markdown
# Docker Setup on Ubuntu

This guide provides steps to install and configure **Docker** on an Ubuntu server.

## Prerequisites
- Ubuntu 20.04/22.04 or later  
- A user with **sudo privileges** (default user: `ubuntu`)

---

## Installation Steps

### 1. Update System Packages
```bash
sudo apt update -y
````

### 2. Set Hostname (optional)

```bash
sudo hostnamectl set-hostname docker
```

### 3. Install Docker

```bash
sudo apt install docker.io -y
```

### 4. Start Docker Service

```bash
sudo service docker start
```

### 5. Verify Docker Installation

```bash
sudo docker info
```

### 6. Add User to Docker Group

This allows running Docker without `sudo`.

```bash
sudo usermod -aG docker ubuntu
```

### 7. Switch to `ubuntu` User

```bash
sudo su - ubuntu
```

### 8. Verify Docker is Working

```bash
docker ps
```

---

## Notes

* After adding a user to the **docker group**, you may need to log out and log back in for changes to take effect.
* You can check Docker status anytime with:

```bash
systemctl status docker
```

* To enable Docker to start on boot:

```bash
sudo systemctl enable docker
```

---

## Example

```bash
docker run hello-world
```

This will confirm that Docker is installed and running properly.

---

## Troubleshooting

* If you get a **permission denied** error when running Docker as a non-root user, make sure you have logged out and back in after adding the user to the Docker group.
* Ensure the Docker service is running:

```bash
sudo systemctl restart docker
```

---

✅ Now your Ubuntu server is ready to use Docker!

```

Would you like me to also **convert your bash script into a single one-liner installation script** (so you can just copy-paste and run it), or keep it as step-by-step commands?
```
