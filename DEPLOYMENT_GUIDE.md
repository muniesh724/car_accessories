# Car Accessories Website - Deployment Guide

## Option 1: Free Cloud Hosting (Recommended for Testing)

### Render.com (Free)
1. Create account at https://render.com
2. Click "New +" → "Web Service"
3. Connect your GitHub repository
4. Build Command: `pip install -r requirements.txt`
5. Start Command: `python app.py`
6. Environment Variables:
   - `SECRET_KEY`: (generate a random key)
7. Deploy

### PythonAnywhere (Free Tier)
1. Create account at https://www.pythonanywhere.com
2. Create a "Web" app
3. Select Flask framework
4. Upload your files via web interface or git
5. Configure WSGI file
6. Set up virtual environment
7. Install requirements: `pip install -r requirements.txt`

## Option 2: Paid Cloud Hosting (Production Ready)

### Heroku
1. Install Heroku CLI
2. Login: `heroku login`
3. Create app: `heroku create your-app-name`
4. Deploy: `git push heroku main`
5. Set environment variables: `heroku config:set SECRET_KEY=your-key`

### DigitalOcean
1. Create Droplet (Ubuntu)
2. SSH into server
3. Install dependencies:
   ```bash
   sudo apt update
   sudo apt install python3-pip python3-venv nginx
   ```
4. Clone your code
5. Setup virtual environment
6. Configure Nginx as reverse proxy
7. Use Gunicorn as WSGI server

### AWS Elastic Beanstalk
1. Create AWS account
2. Install EB CLI
3. Initialize: `eb init`
4. Create environment: `eb create production`
5. Deploy: `eb deploy`

## Option 3: Traditional Web Hosting

### cPanel Hosting
1. Purchase hosting with Python support
2. Upload files via FTP or File Manager
3. Setup Python application in cPanel
4. Configure passenger_wsgi.py
5. Point domain to public folder

## Option 4: Static Hosting (Frontend Only)

### Netlify/Vercel
1. Export as static HTML (remove Flask backend)
2. Push to GitHub
3. Connect to Netlify/Vercel
4. Auto-deploy on push

## Pre-Deployment Checklist

### Security
- [ ] Change secret key in app.py
- [ ] Change default admin password
- [ ] Enable HTTPS/SSL
- [ ] Set up database backups
- [ ] Configure firewall rules

### Performance
- [ ] Optimize images
- [ ] Enable caching
- [ ] Use CDN for static files
- [ ] Minify CSS/JS

### Content
- [ ] Update contact information
- [ ] Add real products
- [ ] Test all forms
- [ ] Check mobile responsiveness

## Client Handover Package

### Files to Include
1. Source code (entire project folder)
2. Database file (car_accessories.db)
3. Admin credentials document
4. Deployment instructions
5. Maintenance guide

### Admin Credentials
```
Username: admin
Password: admin123
```
**Important:** Tell client to change this immediately!

### Documentation to Provide
1. How to access admin panel
2. How to add/edit products
3. How to backup database
4. How to update content
5. Contact support information

## Quick Deployment for Client (Easiest)

### Step 1: Zip the Project
```bash
# In the project directory
cd d:\Oberlo-1.0.0\Oberlo-1.0.0
# Compress entire folder
```

### Step 2: Send to Client
- Upload to Google Drive/Dropbox
- Send download link
- Include deployment instructions

### Step 3: Client Setup Instructions
1. Extract files
2. Install Python 3.8+
3. Install dependencies: `pip install -r requirements.txt`
4. Run: `python app.py`
5. Access at http://localhost:5000

## Domain Setup

### Purchase Domain
- GoDaddy, Namecheap, or similar
- Buy domain (e.g., caraccessories.com)

### Connect Domain
1. In hosting provider, add domain
2. Update DNS settings
3. Point A record to hosting IP
4. Enable SSL certificate

## Ongoing Maintenance

### Regular Tasks
- Weekly database backups
- Security updates
- Performance monitoring
- Content updates

### Backup Script
```python
import shutil
from datetime import datetime

backup_name = f"backup_{datetime.now().strftime('%Y%m%d')}.db"
shutil.copy('car_accessories.db', f'backups/{backup_name}')
```

## Support Contact
Provide client with:
- Your contact information
- Emergency support procedure
- Hourly rates for maintenance (if applicable)
