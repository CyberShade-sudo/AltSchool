# AltSchool Practical — Cybersecurity Project

**Author:** Folasade Nasir
**Scope:** PKI and Certificate Setup · Secure Configuration & Hardening · Traffic Capture & Analysis · Controlled Weakness & Mitigation

## Executive summary
I built and tested a small lab environment to exercise real-world cybersecurity tasks: creating a PKI (Root + Intermediate), issuing server and client certificates, deploying and hardening services, capturing and analyzing TLS traffic, and intentionally creating then mitigating a controlled weakness. The project emphasizes hands-on troubleshooting and building reproducible evidence.

## Repo structure
- `Phase_1/` — PKI artifacts (public certs), public SSH keys, `commands.txt`
- `Phase_2/` — screenshots and redacted configs for service hardening
- `Phase_3/` — `capture.pcap`, Wireshark evidence, analysis notes
- `Phase_4/` — controlled weakness evidence (`server_key_hash.txt`, tiny wordlist check)
- `docs/` — consolidated master report and additional notes

## What I included (evidence)
- Public root and intermediate certificates (PEM)
- Public SSH keys (`id_rsa.pub`, `id_ed25519.pub`)
- Screenshots proving TLS handshake, mTLS, GPG sign/decrypt steps, and SSH attempts
- `server_key_hash.txt` showing pem2john output
- `tiny_wordlist_check.txt` demonstrating post-mitigation testing

## Important: security & exclusions
This repository does **not** include any private keys or plaintext passphrases. I intentionally excluded:
- Private key files (e.g., `*.key`, private `.pem`)
- The strong passphrase file and any secrets
- Any system credentials or tokens

If you need to reproduce the lab, see `commands.txt` for the steps and follow the redactions to generate your own private artifacts.

## How to reproduce (summary)
1. Follow `Phase_1/commands.txt` to generate a Root CA, Intermediate CA, server and client certs.
2. Redact any passphrases — never store them in plain text.
3. Use the provided public certs and screenshots to validate results without exposing private keys.
