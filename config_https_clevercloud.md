# Config https on CleverCloud with Let's Encrypt

Assuming you already have an application running on Clever Cloud.

1. Install **Certbot**

  ```sh
  sudo apt-get update
  sudo apt-get install software-properties-common
  sudo add-apt-repository ppa:certbot/certbot
  sudo apt-get update
  sudo apt-get install certbot
  ```

1.  Ask for DNS challenge for your website url:
    ```sh
    sudo certbot -d www.example.com --manual --preferred-challenges dns certonly
    ```

1.  Go to your DNS configuration (on Gandhi, OVH, etc.) and add a TXT record:
    - name: `_acme-challenge.www`
    - value: `value from certbot output`

1.  Grab a cup of coffee or tea 🍵 while your DNS record is propagating.

1.  Get certificate private key:
    ```sh
    sudo cat /etc/letsencrypt/live/www.example.com/privkey.pem
    ```

1.  Get certificate full chaine:
    ```sh
    sudo cat /etc/letsencrypt/live/www.example.com/fullchain.pem
    ```

1.  Send the certificate bundle (privkey + full chain) to Clevercloud at this [endpoint](https://api.clever-cloud.com/v2/certificates/new).

1.  You're done! Certificate should be active in a few minutes.

### [Recommended]

1.  Force https connection from Rails by uncommenting `# config.force_ssl = true` in *config/environments/production.rb*:
   ```ruby
   # Force all access to the app over SSL, use Strict-Transport-Security, and use secure cookies.
   config.force_ssl = true
   ```
   
