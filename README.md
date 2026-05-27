# API Security Assessment of crAPI Using OWASP ZAP

## Overview

This project demonstrates a practical API security assessment performed against the intentionally vulnerable OWASP crAPI application using OWASP ZAP on Kali Linux.

The objective of this project is to understand and test common API vulnerabilities listed in the OWASP API Top 10 through:

* API reconnaissance
* JWT analysis
* Manual authorization testing
* Active and passive scanning
* BOLA/IDOR testing
* Fuzzing and payload testing
* Vulnerability validation and reporting

---

## Project Objectives

* Learn practical API penetration testing
* Understand OWASP API Top 10 vulnerabilities
* Perform authenticated API testing
* Analyze JWT-based authentication
* Identify Broken Object Level Authorization (BOLA)
* Validate automated scan findings manually
* Generate security assessment reports using OWASP ZAP

---

## Technologies & Tools Used

* Kali Linux
* OWASP ZAP
* Docker
* crAPI (Completely Ridiculous API)
* Firefox Browser
* JWT Authentication
* REST APIs

### Official Resources

* OWASP ZAP: https://www.zaproxy.org/
* crAPI: https://owasp.org/www-project-crapi/
* Docker: https://www.docker.com/
* Kali Linux: https://www.kali.org/

---

## Environment Setup

### Clone crAPI

```bash
git clone https://github.com/OWASP/crAPI.git
```

### Start crAPI

```bash
cd crAPI/deploy/docker
docker compose up -d
```

### Access Applications

| Service   | URL                   |
| --------- | --------------------- |
| crAPI Web | http://localhost:8888 |
| MailHog   | http://localhost:8025 |
| OWASP ZAP | http://127.0.0.1:8080 |

---

## Project Workflow

### 1. Proxy Configuration

* Configured Firefox browser to use OWASP ZAP proxy
* Imported ZAP Root CA Certificate

### 2. Reconnaissance

* Intercepted HTTP requests
* Captured API endpoints
* Analyzed JavaScript files for hidden APIs

### 3. Authentication Analysis

* Captured JWT tokens
* Tested token validation
* Performed token swapping

### 4. Automated Scanning

* Passive Scanning
* Spider Scan
* AJAX Spider
* Active Scan

### 5. Manual API Testing

* Authorization testing
* ID manipulation
* BOLA/IDOR testing
* Parameter tampering
* Method manipulation (GET/PUT/DELETE)

### 6. Fuzzing

* Input fuzzing
* Payload testing
* Endpoint enumeration

### 7. Reporting

* Generated ZAP reports
* Documented vulnerabilities
* Added remediation recommendations

---

## Vulnerabilities Tested

| Vulnerability                              | Status |
| ------------------------------------------ | ------ |
| Broken Object Level Authorization (BOLA)   | Tested |
| Broken Function Level Authorization (BFLA) | Tested |
| Excessive Data Exposure                    | Tested |
| JWT Authentication Weaknesses              | Tested |
| Information Disclosure                     | Tested |
| Rate Limiting Issues                       | Tested |
| Input Validation Issues                    | Tested |

---

## Sample Findings

### 1. Information Disclosure

**Issue**
Server version information was exposed in HTTP response headers.

**Evidence**

```http
Server: openresty/1.27.1.2
```

**Severity**
Low

---

## Learning Outcomes

Through this project, I gained hands-on experience in:

* API penetration testing
* OWASP ZAP usage
* JWT authentication analysis
* API authorization testing
* Manual vulnerability validation
* Security report generation
* OWASP API Top 10 concepts

---

## Disclaimer

This project was conducted only within a controlled local lab environment using the intentionally vulnerable OWASP crAPI application for educational and research purposes.

Do not perform unauthorized security testing on systems you do not own or have permission to assess.

---

