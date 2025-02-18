-[[LOCALHOST]]
- **Web Services Overview**
    
    - Enables communication between browsers and web servers.
    - Apache acts as the "engine" and "foundation" for websites.
- **Apache Web Server**
    
    - **Modularity:**
        - Extendable with modules like:
            - **mod_ssl:** Encrypts communication.
            - **mod_proxy:** Directs traffic.
            - **mod_headers & mod_rewrite:** Modify HTTP headers and URLs.
    - **Dynamic Content:**
        - Supports server-side scripting (PHP, Perl, Ruby, Python, etc.).
    - **Installation:**
        - `sudo apt install apache2 -y`
    - **Starting Apache:**
        - `sudo systemctl start apache2`
    - **Default Port:**
        - Serves on HTTP port 80.
    - **Changing Port (e.g., to 8080):**
        - Edit `/etc/apache2/ports.conf` to include:
            
            ```
            Listen 8080
            ```
            
        - Restart Apache and verify with:
            - `curl -I http://localhost:8080`
- **Command-Line Tools for Web Interaction**
    
    - **cURL:**
        - Fetch webpage content:
            - `curl http://localhost`
    - **wget:**
        - Download webpage and save locally:
            - `wget http://localhost`
- **Python Web Server**
    
    - **Starting the Server:**
        - `python3 -m http.server`
    - **Example Output:**
        - Logs showing HTTP GET requests (e.g., for `readme.html`).
- **Additional HTTP Server Commands**
    
    - **Using npm:**
        - Start server on port 8080:
            - `http-server -p 8080`
    - **Using PHP:**
        - Start server on localhost at port 8080:
            - `php -S 127.0.0.1:8080`
            - 
            - 
NPM
Nodejs package manager