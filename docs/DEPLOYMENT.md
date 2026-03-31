# Deployment Guide

This guide provides instructions for deploying Dashboard Hub to different environments.

## Prerequisites

- Node.js v16 or higher
- npm v7 or higher
- Git
- Access to deployment platform
- SSL certificate (for production)

## Build Process

### Development Build

```bash
npm run build:dev
```

Creates a development build with source maps for debugging.

### Production Build

```bash
npm run build
```

Creates an optimized production build:
- Minified JavaScript and CSS
- Unused code removal
- File optimization
- Source maps (optional)

Output in `dist/` folder.

## Deployment Environments

### Local Development

```bash
npm run dev
```

Runs development server on `http://localhost:8080` with hot reload.

### Staging Environment

1. Build the application:
```bash
npm run build
```

2. Deploy to staging server:
```bash
scp -r dist/* user@staging-server:/var/www/dashboard-staging/
```

3. Set environment variables
4. Test all features
5. Verify performance

### Production Environment

1. Build the application:
```bash
npm run build
```

2. Deploy to production server:
```bash
scp -r dist/* user@production-server:/var/www/dashboard-production/
```

3. Set environment variables
4. Configure SSL/TLS
5. Set up reverse proxy
6. Configure monitoring

## Cloud Deployment

### Netlify

1. Connect GitHub repository
2. Build settings:
   - Build command: `npm run build`
   - Output folder: `dist`
3. Set environment variables
4. Deploy

### Vercel

1. Connect GitHub repository
2. Build settings:
   - Build command: `npm run build`
   - Output folder: `dist`
3. Set environment variables
4. Deploy

### AWS S3 + CloudFront

1. Build the application
2. Upload to S3 bucket
3. Configure CloudFront distribution
4. Set up SSL certificate
5. Configure DNS

## Server Configuration

### Nginx Configuration

```nginx
server {
    listen 443 ssl http2;
    server_name dashboard.example.com;

    ssl_certificate /etc/ssl/certs/dashboard.crt;
    ssl_certificate_key /etc/ssl/private/dashboard.key;

    # Security headers
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
    add_header X-Content-Type-Options "nosniff" always;
    add_header X-Frame-Options "SAMEORIGIN" always;

    # Gzip compression
    gzip on;
    gzip_types text/plain text/css application/json application/javascript;

    location / {
        root /var/www/dashboard-production;
        try_files $uri $uri/ /index.html;
        expires 1h;
    }

    location /assets/ {
        root /var/www/dashboard-production;
        expires 1y;
    }
}

# Redirect HTTP to HTTPS
server {
    listen 80;
    server_name dashboard.example.com;
    return 301 https://$server_name$request_uri;
}
```

## Environment Variables

Create `.env.production` for production:

```env
VITE_API_URL=https://api.dashboard.example.com
VITE_APP_NAME=Dashboard Hub
```

## Security Checklist

- [ ] SSL/TLS certificate installed
- [ ] Security headers configured
- [ ] CORS configured correctly
- [ ] Environment variables protected
- [ ] Database credentials protected
- [ ] Regular backups enabled
- [ ] Monitoring and alerts configured
- [ ] Access logs enabled
- [ ] Rate limiting configured
- [ ] DDoS protection enabled

## Monitoring and Logging

- Set up application monitoring
- Configure error tracking
- Enable access logs
- Set up performance monitoring
- Configure alerts for critical issues

## Related Documentation

- [PROJECT_SETUP](./PROJECT_SETUP.md) - Setup instructions
- [SECURITY](./SECURITY.md) - Security best practices
- [TECHNOLOGIES](./TECHNOLOGIES.md) - Technology stack
