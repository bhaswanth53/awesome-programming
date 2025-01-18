# How to create Virtual domain in XAMPP server

## Windows :

Here’s the process to set up a virtual domain in XAMPP on Windows:

---

### Step 1: Edit the Apache Configuration File
1. Navigate to the Apache configuration file for virtual hosts:
   ```
   C:\xampp\apache\conf\extra\httpd-vhosts.conf
   ```
2. Open the file in a text editor and add the following entry at the end:
   ```apache
   <VirtualHost *:80>
       DocumentRoot "C:/xampp/htdocs/your-project-folder"
       ServerName your-custom-domain.test
       <Directory "C:/xampp/htdocs/your-project-folder">
           AllowOverride All
           Require all granted
       </Directory>
   </VirtualHost>
   ```
   Replace `your-project-folder` with the folder name of your project in the `htdocs` directory. Replace `your-custom-domain.test` with the custom domain you want to use.

---

### Step 2: Edit the `hosts` File
1. Open the `hosts` file located at:
   ```
   C:\Windows\System32\drivers\etc\hosts
   ```
2. Add the following line at the end of the file:
   ```
   127.0.0.1   your-custom-domain.test
   ```
3. Save the file. *(You may need administrator privileges to save it.)*

---

### Step 3: Restart Apache
1. Open the XAMPP Control Panel.
2. Stop the Apache server.
3. Start the Apache server again.

---

### Step 4: Test the Virtual Host
1. Open your web browser.
2. Enter your custom domain in the address bar:
   ```
   http://your-custom-domain.test
   ```
3. Your project should load if everything is set up correctly.

---

### Additional Notes:
- Use a reserved TLD like `.test` or `.local` for local development to avoid conflicts with real domains.
- If SSL is needed, configure the `httpd-ssl.conf` file in XAMPP and generate a self-signed certificate.