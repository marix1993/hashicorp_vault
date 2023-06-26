# HashiCorp Vault.

https://developer.hashicorp.com/vault/docs/what-is-vault

### The key features of Vault are:

#### Secure Secret Storage: 
Arbitrary key/value secrets can be stored in Vault. Vault encrypts these secrets prior to writing them to persistent storage, so gaining access to the raw storage isn't enough to access your secrets. Vault can write to disk, Consul, and more.

#### Dynamic Secrets: 
Vault can generate secrets on-demand for some systems, such as AWS or SQL databases. For example, when an application needs to access an S3 bucket, it asks Vault for credentials, and Vault will generate an AWS keypair with valid permissions on demand. After creating these dynamic secrets, Vault will also automatically revoke them after the lease is up.

#### Data Encryption: 
Vault can encrypt and decrypt data without storing it. This allows security teams to define encryption parameters and developers to store encrypted data in a location such as a SQL database without having to design their own encryption methods.

#### Leasing and Renewal: 
All secrets in Vault have a lease associated with them. At the end of the lease, Vault will automatically revoke that secret. Clients are able to renew leases via built-in renew APIs.

#### Revocation: 
Vault has built-in support for secret revocation. Vault can revoke not only single secrets, but a tree of secrets, for example all secrets read by a specific user, or all secrets of a particular type. Revocation assists in key rolling as well as locking down systems in the case of an intrusion.

## HashiCorp Vault installation.

1. First run Windows PowerShell as an administrator.
2. Run: `choco install vault`
3. Check if installed by using: `vault --version`.

## Starting the server.

1. Run: `vault server -dev`  (do not run in production).
2. Copy ip address : `http://127.0.0.1:8200` and paste into browser.

![url.png](files%2Furl.png)

3. Copy Root Token from your terminal:

![root_token.png](files%2Froot_token.png)

4. Paste it and login.

![logged_in.png](files%2Flogged_in.png)

5. Now open a new terminal and run:
`export VAULT_ADDR=http://localhost:8200` & `export VAULT_TOKEN=<your_token_here>`

6. Now to check if everything is running properly use: `vault status`

![running.png](files%2Frunning.png)

7. Now we can start storing files/passwords in Vault.