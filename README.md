## VLESS TO SUB

[فارسی](README-FA.md)   [English](README.md)


**Instructions:**

1. **Create a Vless Configuration:**
   - Use any desired code to create a Vless configuration file. The only crucial elements are your configuration's UUID and hostname.

2. **Edit the Configuration:**
   - Open the configuration file for editing.
   - Replace the placeholder UUID in line 40 with your actual UUID.
   - Replace the placeholder hostname in lines 30-32 and 80-82 with your actual hostname.
   - Save the modified configuration file.

3. **Create a CloudFlare Worker:**
   - Log in to your CloudFlare account.
   - Navigate to the "Workers" section.
   - Create a new worker script.

4. **Deploy the Configuration in CloudFlare Worker:**
   - Paste the modified Vless configuration code into the CloudFlare worker script.
   - Save the worker script.

5. **Obtain Subscription Link:**
   - Access the worker script's URL. This URL will serve as your subscription link.

6. **Update Subscription:**
   - Click the "Update Subscription" button.
   - This will generate 30 new configurations with clean CloudFlare IPs.

7. **Automatic Updates (Optional):**
   - To enable automatic updates every 10 seconds, set up a cron job or similar automation mechanism to periodically trigger the "Update Subscription" action.

**Additional Notes:**

- Ensure proper firewall configurations to allow incoming connections to the CloudFlare worker script's URL.
- Consider using a secure method, such as encrypted file transfer, to share the Vless configuration file with clients.

**Disclaimer:**
