# Using a Custom Domain (nicoglp.com) with GitHub Pages

This guide explains how to purchase and configure a custom domain (nicoglp.com) for use with your GitHub Pages site.

## 1. Purchase the Domain

*   Choose a domain registrar (e.g., GoDaddy, Namecheap, Google Domains).
*   Search for `nicoglp.com` (or your desired domain) and purchase it.

## 2. Configure DNS Settings

*   Log in to your domain registrar's control panel.
*   Find the DNS settings for your domain.
*   Add the following records. Replace `@` with your domain name if required by your registrar.

    *   **A records:** Point your domain to GitHub Pages' servers.  Use the following IP addresses:

        ```
        185.199.108.153
        185.199.109.153
        185.199.110.153
        185.199.111.153
        ```

        Create four A records, each pointing to one of these IP addresses.  Set the "Host" or "Name" field to `@` or leave it blank (depending on your registrar's requirements).

    *   **CNAME record:** Point `www.nicoglp.com` to your GitHub Pages subdomain.

        *   Type: `CNAME`
        *   Name/Host: `www`
        *   Value: `nicoglp.github.io.` (Note the trailing dot.)

## 3. Configure GitHub Pages

*   Go to your GitHub repository (`nicoglp/nicoglp.github.io`).
*   Navigate to **Settings** -> **Pages**.
*   In the "Custom domain" section, enter `nicoglp.com` and click **Save**.
*   If you want to enforce HTTPS, check the "Enforce HTTPS" box after GitHub Pages confirms your domain is properly configured.  This may take some time.

## 4. Wait for Propagation

*   DNS changes can take up to 24-48 hours to propagate across the internet.  Your site may not be immediately accessible at your custom domain.

## Troubleshooting

*   **DNS Propagation:**  Use a DNS lookup tool (e.g., `https://www.whatsmydns.net/`) to check if your DNS records have propagated.
*   **GitHub Pages Configuration:** Double-check that you've entered your custom domain correctly in your repository's settings.
*   **CNAME File:** Ensure that you have a `CNAME` file in the root of your repository containing your custom domain (e.g., `nicoglp.com`). GitHub Pages usually creates this automatically, but it's good to verify. Do *not* include `www.` in the CNAME file.