# Odoo CRM + TrackSdk Integration

This repository contains a complete Odoo CRM setup with TrackSdk integration for testing analytics and tracking capabilities.

## 🚀 Quick Start

### Option 1: Render Deployment (Recommended)
1. **Fork this repository** to your GitHub account
2. **Connect to Render** and deploy as a Web Service
3. **Configure your domain** (e.g., `odoo.padyum.com`)
4. **Access Odoo** and set up your CRM

### Option 2: Local Development
1. **Clone this repository**
2. **Run**: `docker-compose up -d`
3. **Access**: `http://localhost:8069`

## 📁 Repository Structure

```
odoo-tracksdk/
├── docker-compose.yml          # Docker services configuration
├── config/
│   └── odoo.conf              # Odoo configuration
├── addons/
│   └── tracksdk_integration/   # TrackSdk integration addon
│       ├── __manifest__.py    # Addon manifest
│       └── views/
│           └── templates.xml   # TrackSdk integration template
└── README.md                  # This file
```

## 🔧 Configuration

### TrackSdk Integration
The TrackSdk is automatically integrated into Odoo through the custom addon. Update the endpoint in `addons/tracksdk_integration/views/templates.xml`:

```javascript
TrackSdk.init({
    tenantId: 'odoo-test',
    endpoint: 'https://your-tracksdk-service.com/api/v1/collect',
    // ... other options
});
```

### Odoo Configuration
Main configuration is in `config/odoo.conf`. Key settings:
- **Admin password**: `tracksdk_admin_2024`
- **Database**: PostgreSQL (configured in docker-compose.yml)
- **Addons path**: `/mnt/extra-addons`

## 🧪 Testing Scenarios

### 1. User Authentication
- Login/logout tracking
- User identification across sessions
- Role-based access tracking

### 2. Form Interactions
- Lead creation forms
- Contact management
- Opportunity tracking
- User profile updates

### 3. Navigation Testing
- Menu navigation
- Dashboard interactions
- Module switching
- Button clicks

### 4. Business Workflows
- Sales pipeline management
- Marketing campaigns
- Customer relationship management
- Data entry and updates

## 🔍 TrackSdk Features Tested

- **Page Views**: Automatic navigation tracking
- **Click Events**: Button and link interactions
- **Form Submissions**: User input tracking
- **User Identification**: Role-based tracking
- **Custom Events**: Business-specific actions
- **Privacy Controls**: PII redaction and consent management

## 🚀 Deployment Options

### Render (Recommended)
- **Free tier**: 750 hours/month
- **Automatic SSL**: HTTPS out of the box
- **Custom domains**: Easy domain setup
- **Zero server management**: Just push to deploy

### DigitalOcean
- **$5/month**: Basic droplet
- **Full control**: SSH access
- **Manual SSL**: Certificate configuration
- **Server management**: Docker, Nginx setup

### Local Development
- **Free**: Run on your machine
- **Docker required**: Docker Desktop
- **Port 8069**: Access via localhost
- **Development only**: Not for production

## 📊 Monitoring

### TrackSdk Events
- **Page views**: Navigation between Odoo modules
- **Click events**: Button and link interactions
- **Form events**: Data entry and submissions
- **User events**: Login, logout, role changes

### Odoo Logs
- **Docker logs**: `docker-compose logs web`
- **Render logs**: Available in Render dashboard
- **Browser console**: TrackSdk debugging

## 🔧 Troubleshooting

### Common Issues
1. **TrackSdk not loading**: Check browser console for errors
2. **Events not sending**: Verify TrackSdk service endpoint
3. **CORS errors**: Update TrackSdk service CORS settings
4. **Odoo not starting**: Check Docker logs

### Useful Commands
```bash
# View logs
docker-compose logs -f web

# Restart services
docker-compose restart

# Check status
docker-compose ps

# Update services
docker-compose pull
docker-compose up -d
```

## 📝 Next Steps

1. **Deploy to Render** using the provided guide
2. **Configure your domain** (e.g., `odoo.padyum.com`)
3. **Set up Odoo** through the web interface
4. **Configure TrackSdk service** to accept events
5. **Test different user scenarios**
6. **Validate tracking data**

## 🤝 Support

- **Technical issues**: Check Docker logs
- **Odoo questions**: Odoo documentation
- **TrackSdk issues**: Browser console debugging
- **Deployment issues**: Render documentation

## 📄 License

This project is for testing purposes. Odoo is licensed under LGPL v3.
