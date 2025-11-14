# RDAP Lookup

Web-based tool to query domain information using the RDAP (Registration Data Access Protocol) protocol. This application allows users to look up domain registration details, registrar information, nameservers, and other domain metadata directly from the browser.

## Features

- **Domain Lookup**: Query domain information using RDAP protocol
- **TLD → RDAP List**: Browse IANA RDAP bootstrap data to find RDAP servers for different TLDs
- **Detailed Information**: View domain registration dates, expiration dates, registrar details, nameservers, DNSSEC status, and more
- **JSON Response**: View and explore the raw RDAP JSON response
- **Search & Filter**: Search and filter TLDs and RDAP server URLs

## Installation and Usage

1. **Clone or Download** the repository:
   ```bash
   git clone https://github.com/EnesKeremAYDIN/rdap-lookup.git
   cd rdap-lookup
   ```

2. **Run the Application**:
   - Open `index.html` in a web browser to access the RDAP lookup tool.
   - No server or build process required - it's a single HTML file that works offline (after initial bootstrap load).

## Files

- **`index.html`**: Single-file application containing HTML, CSS, and JavaScript for the RDAP lookup tool.

## Requirements

- A web browser with JavaScript enabled
- Internet connection (for fetching RDAP data and IANA bootstrap)

## How It Works

1. **Domain Lookup**:
   - Enter a domain name (e.g., `example.com`)
   - The tool automatically determines the appropriate RDAP server using IANA bootstrap data
   - Queries the RDAP server and displays domain information including:
     - Domain name, handle, and LDH name
     - Registrar information and contact details
     - Abuse contact information
     - Registration, expiration, and last changed dates
     - Nameservers
     - DNSSEC status
     - Domain status codes

2. **TLD → RDAP List**:
   - Browse all TLDs and their corresponding RDAP base URLs from IANA bootstrap data
   - Search and filter by TLD or URL
   - View primary and alternative RDAP server URLs

## Technical Details

- Uses IANA RDAP bootstrap service (`https://data.iana.org/rdap/dns.json`)
- Bootstrap data is cached in browser localStorage for 7 days
- Supports internationalized domain names (IDN)
- Handles CORS limitations (some RDAP servers may block browser requests)