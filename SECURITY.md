# Security Policy

## 🔒 Reporting a Vulnerability

We take the security of Mantis seriously. If you believe you have found a security vulnerability, please report it to us as described below.

**Please do NOT report security vulnerabilities through public GitHub issues.**

### How to Report

Send an email to the project maintainer with the following information:

1. **Description of the vulnerability**
2. **Steps to reproduce** the issue
3. **Potential impact** of the vulnerability
4. **Suggested fix** (if you have one)

### Response Timeline

- **Initial Response**: We will acknowledge your report within 48 hours
- **Assessment**: We will assess the vulnerability and provide an initial response within 7 days
- **Fix Deployment**: For critical vulnerabilities, we aim to deploy a fix within 30 days

### What to Expect

After you submit a vulnerability report, you can expect us to:

1. Confirm receipt of your report within 48 hours
2. Provide a more detailed response within 7 days after verification
3. Keep you informed about our progress with the fix
4. Credit you in our security acknowledgments (unless you prefer to remain anonymous)

## 🛡️ Security Best Practices

When deploying Mantis, please follow these security guidelines:

### API Keys & Secrets

- **Never commit API keys** to version control
- Use environment variables (`.env` file) to store sensitive credentials
- The `.env.example` file is provided as a template - copy it to `.env` and add your keys
- Regularly rotate your API keys and secrets
- Use separate API keys for development and production

### Production Deployment

1. **Disable Mock Mode**: Set `MOCK_MODE=false` in production
2. **Use HTTPS**: Always serve the API over HTTPS in production
3. **Enable Rate Limiting**: Implement rate limiting on API endpoints
4. **Use Strong Authentication**: Secure your API with proper authentication
5. **Keep Dependencies Updated**: Regularly update Python packages to patch known vulnerabilities
6. **Monitor Logs**: Implement proper logging and monitoring

### Environment Variables

Keep the following secret:

- `OPENAI_API_KEY` - OpenAI API access key
- `ANTHROPIC_API_KEY` - Anthropic API access key
- `TWITTER_API_KEY`, `TWITTER_API_SECRET`, etc. - Social media platform credentials
- `META_ACCESS_TOKEN` - Meta platform access token
- `LINKEDIN_CLIENT_ID`, `LINKEDIN_CLIENT_SECRET` - LinkedIn API credentials

### CORS Configuration

The current implementation allows all origins (`allow_origins=["*"]`). In production, you should:

1. Restrict allowed origins to your specific domain(s)
2. Only allow necessary HTTP methods
3. Limit allowed headers to what your application needs

### Database Security

If you implement persistent storage:

- Use strong passwords for database access
- Enable database encryption at rest
- Implement proper backup procedures
- Use connection pooling with appropriate limits

## 📋 Dependency Security

We regularly monitor and update dependencies for security vulnerabilities. To check for known vulnerabilities in the project dependencies:

```bash
pip install safety
safety check -r requirements.txt
```

## 🔐 Secure Development Guidelines

For contributors:

1. Never commit secrets or API keys
2. Use parameterized queries to prevent SQL injection
3. Validate and sanitize all user inputs
4. Follow the principle of least privilege
5. Implement proper error handling without exposing sensitive information
6. Write tests that cover security-critical code paths

## ✅ Security Checklist

Before deploying to production:

- [ ] All API keys are stored in environment variables
- [ ] `MOCK_MODE` is set to `false`
- [ ] CORS is configured with specific allowed origins
- [ ] Rate limiting is implemented
- [ ] Input validation is in place
- [ ] Error messages don't expose sensitive information
- [ ] Dependencies are up to date
- [ ] HTTPS is enabled
- [ ] Proper logging and monitoring is configured
- [ ] Backup procedures are in place

---

Thank you for helping keep Mantis secure! 🙏
