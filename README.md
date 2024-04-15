## VLESS TO SUB
**Built a subscription link with the ability to automatically add CF clean IPs to VLESS configurations.**

[English](README.md)  [فارسی](README-FA.md)


**Instructions:**

1. **Create a Vless Configuration:**
   - Use any desired code to create a Vless configuration file. The only crucial elements are your configuration's UUID and hostname.

2. **Edit the Configuration:**
   - Open the configuration file for editing. with notepad (windows) or MT manager (android) or edit directly at worker code editor place.
   - Replace the placeholder UUID in line 40 with your own UUID.
   - Replace the placeholder hostname in lines 30-32 and 80-82 with your actual hostname.
   - Save the modified configuration file.

3. **Create a  new CloudFlare Worker:**
   - Log in to your CloudFlare account.
   - Navigate to the "Workers and pages" section.
   - Create a new worker from `create application` then `create worker`. rename and deploy worker.
   - click on `edit code`

4. **Deploy the Configuration in CloudFlare Worker:**
   - Delete default codes from here and Copy/Paste the modified script code into the worker.js .
   - click on `Deploy` button at right corner and its done.
   - after deployment you must click on `workers.dev` and you see configuration at base64 format. workers.dev link is yours new subscription link.

6. **Obtain Subscription Link:**
   - Access the worker script's URL. This URL will serve as your subscription link.

7. **Update Subscription:**
   - Click the "Update Subscription" button in v2rayng or nekobox or nekoray or any other clients.
   - This will generate 30 new configurations with clean CloudFlare IPs.
   - you can get new cf ip's with update subscription button every 10 seconds.

**Additional Notes:**

- Ensure proper firewall 
