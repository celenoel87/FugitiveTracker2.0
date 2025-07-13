# Real Scan Setup Guide

This guide will help you configure your Fugitive Tracker app to use real data sources instead of mock data.

## Prerequisites

1. **Legal Compliance**: Ensure you have proper authorization to access these data sources
2. **API Accounts**: Sign up for the data provider services you want to use
3. **Budget**: Most of these services require paid subscriptions

## Step 1: Choose Your Data Sources

### Social Media Intelligence
- **Twitter API**: Free tier available, paid for higher limits
- **LinkedIn API**: Requires business account and approval
- **Facebook Graph API**: Requires app approval
- **Instagram Basic Display API**: Requires app approval

### Public Records
- **LexisNexis**: Professional legal/research service
- **Accurint**: Skip tracing and location data
- **Clear**: Criminal records and background checks
- **TLOxp**: Public records and skip tracing

### Digital Footprint
- **HaveIBeenPwned**: Data breach information (free API available)
- **Hunter.io**: Email verification and finding
- **NumLookup**: Phone number intelligence

## Step 2: Get API Keys

### Twitter API
1. Go to https://developer.twitter.com/
2. Create a developer account
3. Create a new app
4. Get your API keys and bearer token

### HaveIBeenPwned (Free to start)
1. Go to https://haveibeenpwned.com/API/Key
2. Sign up for an API key
3. Free tier: 1,500 requests per month

### Hunter.io
1. Go to https://hunter.io/api
2. Sign up for an account
3. Get your API key

## Step 3: Configure Environment Variables

1. Copy `env.example` to `.env.local`
2. Fill in your actual API keys:

```bash
# Start with these free/accessible APIs
HIBP_API_KEY=your_actual_hibp_key
HUNTER_API_KEY=your_actual_hunter_key
TWITTER_BEARER_TOKEN=your_actual_twitter_token
```

## Step 4: Test Your Setup

1. Start your development server:
```bash
npm run dev
```

2. Go to `/scans` in your app
3. Try running a digital footprint scan with a real email address
4. Check the browser console and server logs for any errors

## Step 5: Add More Data Sources

### Public Records (Paid Services)
For LexisNexis, Accurint, or Clear:
1. Contact their sales teams
2. Complete their verification process
3. Get API credentials
4. Add to your environment variables

### Social Media APIs
For LinkedIn, Facebook, Instagram:
1. Create developer accounts
2. Submit apps for review
3. Get API credentials
4. Add to your environment variables

## Step 6: Error Handling

The app includes error handling for:
- Missing API keys
- Rate limiting
- Network errors
- Invalid responses

Check the browser console and server logs for detailed error messages.

## Step 7: Rate Limiting

The app includes built-in rate limiting to respect API limits:
- Twitter: 300 requests/minute
- LinkedIn: 100 requests/minute
- HaveIBeenPwned: 1,500 requests/minute

## Troubleshooting

### "API not configured" errors
- Check that your environment variables are set correctly
- Restart your development server after adding new environment variables

### "Rate limit exceeded" errors
- Wait for the rate limit to reset
- Consider upgrading your API plan

### "Failed to connect" errors
- Check your internet connection
- Verify API endpoints are correct
- Check if the API service is down

## Cost Considerations

### Free APIs (to start with)
- HaveIBeenPwned: Free tier available
- Twitter: Free tier available
- Hunter.io: 25 requests/month free

### Paid Services
- LexisNexis: $100+/month
- Accurint: $50+/month
- Clear: $30+/month
- LinkedIn API: $100+/month

## Legal Considerations

1. **Terms of Service**: Read and comply with each API's terms
2. **Data Privacy**: Ensure you have proper authorization
3. **Rate Limits**: Respect API rate limits
4. **Usage Rights**: Verify you have rights to access the data

## Next Steps

1. Start with free APIs (HaveIBeenPwned, Twitter)
2. Test thoroughly with your own data
3. Add paid services as needed
4. Monitor usage and costs
5. Implement proper logging and audit trails

## Support

If you encounter issues:
1. Check the browser console for client-side errors
2. Check the server logs for API errors
3. Verify your API keys are correct
4. Test API endpoints directly using tools like Postman 