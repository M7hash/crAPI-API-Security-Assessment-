# Findings Summary

## Project

API Security Assessment of crAPI Using OWASP ZAP

---

# High Severity Findings

## 1. Broken Object Level Authorization (BOLA)

### Endpoint

`/identity/api/v2/user/{id}`

### Description

Authenticated users could access other users' profile data by modifying object identifiers.

### Impact

* Unauthorized data access
* Exposure of personally identifiable information (PII)

### Recommendation

Implement strict server-side authorization validation.

---

# Medium Severity Findings

## 2. Missing Content Security Policy (CSP)

### Description

The application did not implement a Content Security Policy header.

### Impact

Increased risk of client-side attacks such as XSS.

### Recommendation

Implement an appropriate CSP policy.

---

# Low Severity Findings

## 3. Information Disclosure

### Description

The server disclosed backend technology information.

### Evidence

`Server: openresty/1.27.1.2`

### Recommendation

Hide or generalize server banner information.

---

# Informational Findings

## 4. JWT Authentication Identified

### Description

The application uses JWT Bearer authentication for API authorization.

### Notes

JWT tokens were analyzed during the assessment to test authorization behavior.

---

# Overall Risk Summary

| Severity      | Count |
| ------------- | ----- |
| High          | 1     |
| Medium        | 1     |
| Low           | 1     |
| Informational | 1     |

---

# Conclusion

The assessment identified several API security weaknesses related to authorization controls and information disclosure. Manual testing successfully demonstrated object-level authorization issues within the intentionally vulnerable crAPI environment.
