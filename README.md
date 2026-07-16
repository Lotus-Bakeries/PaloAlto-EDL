# Lotus Bakeries - Palo Alto External Dynamic Lists (EDL)

This repository contains External Dynamic Lists (EDLs) used by the Palo Alto Networks firewalls managed through Panorama.

The lists are automatically downloaded by the firewalls and are used to centralize policy management.

---

## Repository Structure

```
.
├── README.md
├── Decryption-Exceptions.txt
├── AI-Allow

```

---

## Current EDLs

| File | Purpose |
|------|---------|
| Decryption-Exceptions.txt | Domains that should bypass SSL/TLS Decryption |
| AI-Allow | Approved AI services that are allowed |

---

## Using the EDLs

Example RAW URL:

```
https://raw.githubusercontent.com/Lotus-Bakeries/paloalto-edl/main/Decryption-Exceptions.txt
https://raw.githubusercontent.com/Lotus-Bakeries/PaloAlto-EDL/refs/heads/main/AI-AllowList
```

Configure the Palo Alto EDL as:

- Objects
- External Dynamic Lists
- Type: URL List
- Source: RAW GitHub URL

---

## File Format

Each line contains **one domain**.

Example:

```
chatgpt.com
api.openai.com
claude.ai
copilot.microsoft.com
```

Do **not** use:

- commas
- quotes
- spaces
- empty lines between entries

Wildcards are supported where appropriate.

Example:

```
*.teams.microsoft.com
*.office.com
```

---

## Change Management

Any modification to these files immediately affects the corresponding firewall policies after the next EDL refresh.

Please ensure:

- Changes are validated before committing.
- Only approved domains are added.
- Remove obsolete entries when no longer required.
- Document significant changes in the commit message.

---

## Version Control

GitHub keeps a complete history of:

- Who changed the file
- When it was changed
- What was modified

Previous versions can always be restored if necessary.

---

## Maintainers

Network & Security Team

Lotus Bakeries

---

## Related Policies

These EDLs are referenced by:

- SSL Decryption Policy
- AI Allow Policy
- Security Policies
- URL Filtering Policies

---

## Notes

This repository contains only domain names used by firewall policies.

No confidential information, credentials, or internal configuration should ever be stored in this repository.
