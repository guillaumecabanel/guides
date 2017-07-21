# Config https on CleverCloud with Let's Encrypt

Assuming you already have an application running on Clever Cloud.

1. Install the gem **letsencrypt_http_challenge**:

  ```ruby
  # Gemfile
  gem 'letsencrypt_http_challenge', git: 'https://github.com/guillaumecabanel/letsencrypt_http_challenge.git'
  ```

2. Follow [the instructions](https://github.com/guillaumecabanel/letsencrypt_http_challenge) from the gem's author.

3. Send the certificate bundle `.letsencrypt/bundle.pem` to Clevercloud at this [endpoint](https://api.clever-cloud.com/v2/certificates/new).

4. Grab a cup of coffee or tea 🍵

5. Test the https connection. 

6. Force https connection from Rails by uncommenting `# config.force_ssl = true` in *config/environments/production.rb*:

   ```ruby
   # Force all access to the app over SSL, use Strict-Transport-Security, and use secure cookies.
   config.force_ssl = true
   ```

   ​
7. Commit and deploy 🚀