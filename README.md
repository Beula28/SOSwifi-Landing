# SOS WiFi — Captive Portal & Payment Integration

A Wi-Fi captive portal landing page that enables users to select an internet access package and proceed to secure online payment.

**Live Website:** https://www.soswifi.uk  
**Original Repository:** https://github.com/StevieHazo/SOSwifi-Landing

## Project Overview

SOS WiFi integrates a web-based landing page with a Wi-Fi access and payment workflow. The project connects the user-facing portal with backend payment processing and network-side client authorization.

The implementation combines frontend web development, serverless APIs, payment processing, and captive portal networking.

## Key Features

- **Captive Portal Landing Page** — User-facing pages for Wi-Fi access and package selection.
- **Paid Wi-Fi Access** — Integration with Stripe Checkout for secure payment processing.
- **Backend API Integration** — Serverless endpoints for creating checkout sessions and handling payment-related events.
- **Payment State Management** — Redis-backed state management for coordinating payment status with client authorization.
- **Network Authentication Workflow** — Integration with OpenWrt and openNDS captive portal infrastructure.
- **Responsive Web Interface** — HTML-based pages designed for users accessing the portal from different devices.
- **Supporting Web Pages** — Payment, privacy, terms, offline, and success-related pages.

## Technology Stack

| Component | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Backend | Node.js serverless API |
| Payment processing | Stripe Checkout |
| State management | Upstash Redis |
| Hosting / deployment | Vercel |
| Captive portal infrastructure | OpenWrt, openNDS |
| Version control | Git, GitHub |

## Architecture Overview

The solution connects the user-facing portal, payment backend, and network authorization workflow.

1. **Wi-Fi connection:** A client connects to the guest Wi-Fi network and is directed to the captive portal.
2. **Package selection:** The user selects an available internet access package.
3. **Checkout creation:** The frontend requests a checkout session from the backend API.
4. **Payment:** The user completes payment through Stripe Checkout.
5. **Payment verification:** The backend processes payment events and updates the relevant payment state.
6. **Network authorization:** The authorization workflow checks the payment status and coordinates internet access for the client.

Payment verification and network authorization must be validated on the backend; a browser redirect alone should not be treated as proof of payment.

## Project Structure

```text
SOSwifi-Landing/
├── api/                    # Backend API endpoints
├── android/                # Android-related project files
├── ios/                    # iOS-related project files
├── windows/                # Windows-related project files
├── lib/                    # Supporting application code
├── Screenshots/            # Project screenshots
├── index.html              # Main landing page
├── pay.html                # Payment initiation page
├── privacy.html            # Privacy information
├── terms.html              # Terms and conditions
├── offline.html            # Offline page
├── service-worker.js       # Service worker
├── manifest.json           # Web app manifest
└── package.json            # Backend dependencies
```

## My Contributions

As a contributor to this project, my work focused on the integration of the Wi-Fi captive portal, payment workflow, and backend services.

- Integrated Stripe Checkout into the Wi-Fi package selection and payment flow.
- Worked on serverless API integration for checkout session creation.
- Implemented payment-state coordination using Redis-backed storage.
- Worked on the connection between payment verification and captive portal client authorization.
- Troubleshot captive portal and payment redirection issues across mobile devices and laptops.
- Worked with OpenWrt and openNDS as part of the wider Wi-Fi access solution.

## Security Considerations

- Store Stripe secret keys and other credentials in server-side environment variables.
- Verify payment events using Stripe webhook signature validation.
- Validate payment status on the backend before granting network access.
- Avoid exposing credentials, customer information, or production configuration in public repositories.

## Project Context

This repository represents the landing-page and related application components of a broader Wi-Fi captive portal solution. Network configuration, backend deployment, payment processing, and client authorization may require separate configuration outside this repository.

**Note:** This is a portfolio description of the implementation. Deployment instructions, environment variables, and production configuration should be documented separately before attempting to reproduce the complete system.
