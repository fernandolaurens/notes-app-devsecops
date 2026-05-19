# Notes App DevSecOps Pipeline

Project ini merupakan implementasi DevSecOps CI/CD Pipeline menggunakan aplikasi FastAPI Notes App.

## Repository

### GitHub
https://github.com/fernandolaurens/notes-app-devsecops

### Docker Hub
https://hub.docker.com/r/fernandopsrb/notes-app

---

# Tech Stack

- FastAPI
- Pytest
- Bandit
- pip-audit
- Gitleaks
- Docker
- Trivy
- GitHub Actions

---

# CI/CD Pipeline

Pipeline GitHub Actions terdiri dari beberapa job:

1. Unit Test (pytest)
2. SAST Scan (Bandit)
3. SCA Scan (pip-audit)
4. Secret Scan (Gitleaks)
5. Build & Push Docker Image
6. Image Scan (Trivy)

Workflow akan menjalankan proses build hanya jika seluruh security job berhasil.

---

# Security Checks

## Unit Testing
Menggunakan pytest untuk memastikan fungsi API berjalan dengan baik.

## SAST
Menggunakan Bandit untuk mendeteksi insecure coding pada source code Python.

## SCA
Menggunakan pip-audit untuk mendeteksi dependency vulnerability.

## Secret Scanning
Menggunakan Gitleaks untuk mendeteksi hardcoded secrets.

## Container Scanning
Menggunakan Trivy untuk melakukan vulnerability scanning pada Docker image.

---

# Docker Image

Pull image:

```bash
docker pull fernandopsrb/notes-app:latest
```

Run container:

```bash
docker run -d -p 8000:8000 fernandopsrb/notes-app:latest
```

Access Swagger UI:

```text
http://localhost:8000/docs
```

---

# GitHub Actions Workflow

Workflow file:

```text
.github/workflows/ci.yml
```

---

# Hasil Pipeline

Semua pipeline berhasil dijalankan:

- Test PASS
- SAST PASS
- SCA PASS
- Secret Scan PASS
- Docker Build PASS
- Docker Push PASS
- Trivy Scan PASS

---

# Insight

Beberapa hal yang dipelajari selama project:

- Implementasi DevSecOps pada CI/CD pipeline
- Integrasi security scanning dalam GitHub Actions
- Dependency vulnerability management
- Docker image hardening
- Otomatisasi build dan deployment container

---

# Author

Laurens Fernando
