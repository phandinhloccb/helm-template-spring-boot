# Helm Template for Fast Application Deployment

This repository provides a reusable Helm chart template designed to help you deploy your applications quickly and with standardized configuration on Kubernetes.

## Features
- **Quick Start:** Easily deploy your application with minimal configuration.
- **Standardized Format:** Ensures your application deployments follow best practices and a consistent structure.
- **Configurable:** Supports environment variables, ConfigMaps, Secrets, volume mounts, autoscaling, and more.

## Usage
1. **Clone or copy this chart into your project:**
   ```sh
   git clone <this-repo-url>
   # or copy the app-helm-template directory into your project
   ```
2. **Customize `values.yaml`:**
   - Set your application name, image, ports, environment variables, etc.
3. **Package the chart (optional):**
   ```sh
   helm package app-helm-template
   ```
4. **Deploy to your Kubernetes cluster:**
   ```sh
   helm install <release-name> ./app-helm-template -f app-helm-template/values.yaml
   ```

## Example `values.yaml` Format
```yaml
name: my-app
image:
  repository: myrepo/my-app
  tag: latest
  containerPort: 8080
service:
  type: ClusterIP
  port: 80
configmap:
  enabled: true
secret:
  enabled: true
autoscaling:
  enabled: false
volumes:
  configmap:
    enabled: false
    appended: []
  secret:
    enabled: false
    path: ""
```

## Notes
- This template is intended as a starting point. You can extend or modify it to fit your application's needs.
- For more advanced configuration, refer to the comments in `values.yaml` and the templates in the `templates/` directory.

---
Feel free to contribute or suggest improvements! 