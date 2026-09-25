# DNS troubleshooting in plain English: why your site or email is not resolving

A plain-English guide to the most common DNS problems that stop a website or
email from working. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this fixed for you, see
[linuxstewards.com/services/hosting-devops](https://www.linuxstewards.com/services/hosting-devops).

DNS is the phone book of the internet. When you type a domain, DNS turns it into
the address of the server that serves it. When DNS is wrong, the site or email
"does not exist" even though the server is perfectly healthy.

## The records that matter most

- **A record** — points your domain (example.com) to a server's IP address.
- **CNAME** — points a subdomain (www) to another domain name.
- **MX** — tells mail servers where your domain's email should be delivered.
- **TXT** — holds SPF/DKIM/DMARC and other text-based records (see the separate
  email guide).
- **NS** — which name servers are authoritative for your domain.

## The most common problems, in order

### 1. "Site not found" / NXDOMAIN after a change
You moved a website or changed hosts and the domain no longer resolves. Usually
the A or CNAME record still points at the old server, or the name servers were
changed and have not propagated yet.

### 2. Email stops arriving (MX missing or wrong)
If MX records are missing or point at the old provider, mail silently bounces or
goes nowhere. Fix: point MX at the current mail provider.

### 3. The www version does not work but the bare domain does
Common after a site launch — the `www` CNAME (or A record) is missing, so
`www.example.com` fails while `example.com` works.

### 4. Records "not propagated"
DNS changes can take minutes to hours to reach everywhere because of caching
(TTL). If a change "has not taken effect", it is often just the TTL still being
served by a resolver — not a failure.

## How to check it yourself (free)
- Use a public DNS lookup tool (there are several free ones) and query your
  domain for A, CNAME and MX.
- Compare what is returned with what your host/provider says it should be.
- If a change was made recently, wait for the TTL to pass and re-check — do not
  keep editing records while waiting.

## What to gather before asking for help
- Your domain name.
- Where the domain is registered AND where the website/email is hosted (they are
  often different companies).
- What changed recently (a host move, a domain transfer, a record edit).
- The exact symptom: site down, email down, or both.

## When to get it fixed for you
If the records are unclear or the problem is urgent, Linux Stewards offers domain
and DNS help from £39, delivered remotely. We identify the record that is wrong,
correct it, and confirm the change has propagated and is working before we call
it done.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
