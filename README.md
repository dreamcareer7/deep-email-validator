# Email Validator

Validates emails based on regex, common typos, disposable email blacklists, DNS records and SMTP server response.

- Validates email is compliant with RFC standard using regex.
- Validates common typos e.g. example@gmaill.com.
- Validates email was not generated by disposable email service.
- Validates MX records are present on DNS.
- Validates SMTP server is running.
- Validates mailbox exists on SMTP server.
- Native typescript support.

## Getting Started

Install like so

```
yarn add deep-email-validator
```

Use like so

```typescript
import validate from 'deep-email-validator'
const main = async () => {
  let res = await validate('asdf@gmail.com')
  // {
  //   "valid": false,
  //   "validators": {
  //       "regex": {
  //         "valid": true
  //       },
  //       "typo": {
  //         "valid": true
  //       },
  //       "disposable": {
  //         "valid": true
  //       },
  //       "mx": {
  //         "valid": true
  //       },
  //       "smtp": {
  //         "valid": false,
  //         "reason": "Invalid Mailbox",
  //       }
  //   }
  // }
}
```
