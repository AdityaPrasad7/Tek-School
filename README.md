# Tek School Backend

Backend server for Tek School registration form using Node.js, Express, and Nodemailer.

## 🚀 Quick Start

### 1. Install Dependencies

```bash
npm install
```

### 2. Configure Environment

Copy `.env.example` to `.env` and fill in your email credentials:

```bash
cp .env.example .env
```

Edit `.env` file:
```env
PORT=5000
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
```

### 3. Get Gmail App Password

1. Enable 2-Step Verification on your Google account
2. Go to https://myaccount.google.com/apppasswords
3. Generate an app password for "Mail"
4. Copy the 16-character password (no spaces)

### 4. Start the Server

```bash
npm start
# or for development with auto-reload:
npm run dev
```

Server will run on http://localhost:5000

## 📡 API Endpoints

### POST `/api/register`
Register a new user and send confirmation email

**Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "1234567890",
  "program": "MERN Stack"
}
```

**Response:**
```json
{
  "success": true,
  "message": "Registration successful and email sent!",
  "messageId": "message-id"
}
```

### GET `/api/health`
Health check endpoint

**Response:**
```json
{
  "status": "Server is running",
  "timestamp": "2024-01-01T12:00:00.000Z"
}
```

## 🚢 Deployment

See main `kodr-site/DEPLOYMENT_GUIDE.md` for deployment instructions.

Quick deploy to **Railway**:
1. Push code to GitHub
2. Go to https://railway.app
3. Deploy from GitHub
4. Add environment variables
5. Done!

## 📝 Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `PORT` | Server port | No (default: 5000) |
| `EMAIL_USER` | Email address | Yes |
| `EMAIL_PASSWORD` | App password | Yes |
| `SMTP_HOST` | SMTP hostname | No (default: smtp.gmail.com) |
| `SMTP_PORT` | SMTP port | No (default: 587) |

## 🛠️ Development

Watch mode with auto-reload:
```bash
npm run dev
```

## 📧 Email Providers

### Gmail
```env
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password
```

### Outlook
```env
SMTP_HOST=smtp-mail.outlook.com
SMTP_PORT=587
EMAIL_USER=your_email@outlook.com
EMAIL_PASSWORD=your_password
```

### Yahoo
```env
SMTP_HOST=smtp.mail.yahoo.com
SMTP_PORT=587
EMAIL_USER=your_email@yahoo.com
EMAIL_PASSWORD=your_app_password
```

## 🐛 Troubleshooting

**"Authentication failed"**
- Verify EMAIL_PASSWORD is correct
- Make sure it's an App Password for Gmail
- Check if 2-Step Verification is enabled

**"Connection refused"**
- Make sure the server is running
- Check if port 5000 is available
- Try changing PORT in .env

**Emails in spam**
- Use a professional email address
- Add SPF and DKIM records
- Include proper email headers

## 📄 License

ISC

