# Web Dashboard

## Web Dashboard

### Overview

The PlasmaBot Web Dashboard provides a comprehensive web interface for managing your Discord server. It includes user authentication via Discord OAuth, ticket transcript viewing, and a full admin panel for managing various bot features.

### Features

* **Discord OAuth Authentication**: Secure login using Discord accounts
* **Ticket Transcripts**: View and access ticket conversation history
* **Admin Dashboard**: Manage custom commands, tickets, giveaways, and reaction roles
* **User Management**: Role-based access control
* **Server Statistics**: Real-time server and bot statistics

### Initial Setup

#### 1. Basic Configuration

Navigate to your `settings.yml` file and locate the `webserver` section:

```yaml
webserver:
  enabled: true
  port: 8080
  base_url: "http://your-domain.com"
  api_key: "your-secret-api-key"
  
  # Discord OAuth2 settings
  oauth:
    client_id: "your-discord-client-id"
    client_secret: "your-discord-client-secret"
    redirect_uri: "http://your-domain.com/oauth/callback"
  
  # Security settings
  security:
    access_level: "creator_only"
    retention_days: 30
```

#### 2. Discord Application Setup

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a new application or select an existing one
3. Navigate to the "OAuth2" section
4. Copy your **Client ID** and **Client Secret**
5. Add your redirect URI: `http://your-domain.com/oauth/callback`
6. Under "OAuth2 URL Generator":
   * Select scope: `identify`
   * Copy the generated URL for testing

#### 3. Configuration Parameters

| Parameter        | Description                       | Required |
| ---------------- | --------------------------------- | -------- |
| `enabled`        | Enable/disable the web dashboard  | Yes      |
| `port`           | Port number for the web server    | Yes      |
| `base_url`       | Your domain or server URL         | Yes      |
| `api_key`        | Secret key for API authentication | Yes      |
| `client_id`      | Discord application client ID     | Yes      |
| `client_secret`  | Discord application client secret | Yes      |
| `redirect_uri`   | OAuth callback URL                | Yes      |
| `access_level`   | Who can access transcripts        | No       |
| `retention_days` | Transcript retention period       | No       |

### Dashboard Features

#### User Features

**Home Page**

* Server overview and statistics
* Quick access to features
* User authentication status

**My Tickets**

* View personal ticket history
* Access ticket transcripts
* Filter by server and date

**Ticket Transcripts**

* Full conversation history
* Formatted Discord-style interface
* Secure access controls

#### Admin Features

**Custom Commands Management**

* Create, edit, and delete custom commands
* View command usage statistics
* Support for embed formatting
* Dynamic placeholders

**Ticket System Configuration**

* Configure ticket categories and channels
* Manage support roles
* Create custom ticket types
* Set welcome messages and naming patterns

**Giveaway Management**

* Create timed giveaways
* Manage active giveaways
* End giveaways early
* View participant statistics

**Reaction Roles Management**

* Create reaction role messages
* Add/remove emoji-role pairs
* Configure exclusive roles
* Manage multiple role messages

### Access Levels

#### User Access

Any authenticated Discord user can:

* View their own ticket transcripts
* Access the home dashboard
* See basic server information

#### Admin Access

Users with admin roles can:

* Access the full admin dashboard
* Manage server configurations
* View all tickets and transcripts
* Create and manage giveaways
* Configure reaction roles

### URL Structure

| Path                    | Description                 | Access Level      |
| ----------------------- | --------------------------- | ----------------- |
| `/`                     | Home dashboard              | All users         |
| `/login`                | Discord OAuth login         | Public            |
| `/logout`               | User logout                 | Authenticated     |
| `/my-tickets`           | Personal ticket history     | Authenticated     |
| `/transcripts/{id}`     | Individual transcript view  | Transcript access |
| `/admin`                | Admin dashboard             | Admin only        |
| `/admin/commands`       | Custom commands management  | Admin only        |
| `/admin/tickets`        | Ticket system configuration | Admin only        |
| `/admin/giveaways`      | Giveaway management         | Admin only        |
| `/admin/reaction-roles` | Reaction roles management   | Admin only        |

### Security Features

#### Authentication

* Discord OAuth2 integration
* Session-based authentication
* Secure token management

#### Authorization

* Role-based access control
* Server membership verification
* Admin permission checking

#### Data Protection

* Transcript access restrictions
* Secure API endpoints
* CSRF protection

### Deployment

#### Local Development

```bash
# Default local configuration
base_url: "http://localhost:8080"
redirect_uri: "http://localhost:8080/oauth/callback"
```

#### Production Deployment

```bash
# Production configuration
base_url: "https://yourdomain.com"
redirect_uri: "https://yourdomain.com/oauth/callback"
```

#### Reverse Proxy Setup (Nginx)

```nginx
server {
    listen 80;
    server_name yourdomain.com;
    
    location / {
        proxy_pass http://localhost:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

### API Endpoints

#### Public Endpoints

* `GET /api/transcripts/{id}` - Get transcript data
* `GET /oauth/callback` - OAuth callback handler

#### Admin Endpoints

* `GET /api/admin/commands` - List custom commands
* `POST /api/admin/commands` - Create custom command
* `PUT /api/admin/commands/{name}` - Update custom command
* `DELETE /api/admin/commands/{name}` - Delete custom command
* `GET /api/admin/giveaways` - List giveaways
* `POST /api/admin/giveaways` - Create giveaway
* `GET /api/admin/reaction-roles` - List reaction roles
* `POST /api/admin/reaction-roles` - Create reaction role message

### Troubleshooting

#### Common Issues

**OAuth Errors**

**Problem**: "Invalid redirect URI" error during login **Solution**:

* Verify the redirect URI in Discord Developer Portal matches your configuration
* Ensure the URL includes the protocol (http/https)

**Access Denied**

**Problem**: Users can't access admin features **Solution**:

* Check that admin roles are properly configured in `settings.yml`
* Verify users have the required roles in Discord
* Ensure bot has permission to check member roles

**Transcripts Not Loading**

**Problem**: Ticket transcripts show as empty or error **Solution**:

* Verify MongoDB connection is working
* Check transcript data exists in database
* Ensure user has permission to view the transcript

**Server Won't Start**

**Problem**: Web server fails to start **Solution**:

* Check if the port is already in use
* Verify all required configuration fields are filled
* Check Java logs for specific error messages

#### Debug Information

Access debug information at `/admin/debug` (admin only) to view:

* Current configuration
* Active user sessions
* OAuth state information
* Server status

#### Log Files

Monitor server logs for:

* Authentication failures
* API request errors
* Database connection issues
* Permission violations

### Advanced Configuration

#### Custom Styling

The dashboard uses Discord-themed styling. CSS can be customized by modifying the embedded styles in the WebServer.java file.

#### Session Management

Sessions are stored in memory and expire when the server restarts. For production deployments, consider implementing persistent session storage.

#### Rate Limiting

Implement rate limiting for API endpoints to prevent abuse:

```yaml
webserver:
  rate_limiting:
    enabled: true
    requests_per_minute: 60
```

#### HTTPS Setup

For production deployments, always use HTTPS:

1. Obtain SSL certificates
2. Configure reverse proxy (Nginx/Apache)
3. Update `base_url` and `redirect_uri` to use https://

### Support

If you encounter issues with the web dashboard:

1. Check the troubleshooting section above
2. Review server logs for error messages
3. Join our [Discord](https://discord.plasma.services/) for support
4. Create a ticket for specific technical issues

For feature requests or bug reports, please contact our support team through the official Discord server.
