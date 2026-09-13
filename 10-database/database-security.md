# Database Security

## AS2C Database Security Group

A dedicated security group was created for the private database layer.

### Inbound Rule

| Protocol | Port | Source |
|---|---:|---|
| MySQL/Aurora | 3306 | AS2C-Web-SG |

Database access is restricted to the web server security group rather than allowing direct Internet access.

## Security Principle

The database is designed as a private resource. Only the application/web server is permitted to initiate database connections.

This reduces the database attack surface and follows the principle of restricting access to trusted application resources.
