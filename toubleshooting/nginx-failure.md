Nginx Service Failure Troubleshooting

Problem

The portfolio website became unavailable because the Nginx service was stopped.

Investigation

1. Check Nginx status

sudo systemctl status nginx

Result: Nginx was inactive.

2. Check port 80

sudo ss -tulnp | grep :80

Result: Nginx was not listening on port 80.

3. Inspect service logs

sudo journalctl -u nginx -n 20

Root Cause

The Nginx service had been deliberately stopped as part of a troubleshooting exercise.

Resolution

Restarted Nginx:

sudo systemctl start nginx

Verified service:

sudo systemctl status nginx

Final Verification

Confirmed that Nginx was active and the portfolio website was accessible again.

Learning Outcomes

- Linux service management
- Port and network troubleshooting
- Log investigation
- Website availability verification
