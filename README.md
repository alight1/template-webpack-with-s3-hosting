# Webpack template with S3 auto-publish

A simple AWS S3-hosted webpack website template with plans to convert it to a webpack plugin distributed via npm.

## To do

- [ ] Create a webpack plugin hosted as a private npm package (lightmotive-s3-hosted-website-webpack) to eliminate copy/paste from this "template repository"
  - [ ] Package init command that replaces copy/paste.
  - [ ] Enable a centralized (multi-project) config-secure.js (maybe specify config-secure.js file path in a separate package-config.js file)

**[Online demo](https://lightmotive.pro/[published site folder]/)**

## Demonstrated concepts

**Main languages:** ..., ...
**Libraries:** ..., ...

- Concept 1
- Concept 2

**See also:** [Common concepts, config, and documentation](https://github.com/alight1/template-webpack-with-s3-hosting#common)

---

## Common

### Project config

- Run `npm install`
- View available scripts in package.json.

### Publish requirements

- Add a _config-secure.js_ file (ignored) that exports the following secrets:

```javascript
module.exports = {
  AWS_ACCESS_KEY_ID: "yourAccessKey",
  AWS_SECRET_ACCESS_KEY: "yourSecretAccessKey",
  AWS_BUCKET_REGION: "bucket-region",
  AWS_BUCKET_NAME: "bucket-name",
  AWS_BUCKET_BASE_PATH: "bucket-folder-name-or-/path/to/-or-empty-string",
};
```

### Concepts

- NPM + Webpack to securely automate build, test, and publish processes
  - Webpack with multiple configuration files for dev and prod builds.
  - Webpack dev server with watch and npm-run-all for concurrent process local discovery testing (automated testing coming soon).
  - [webpack-s3-uploader](https://www.npmjs.com/package/webpack-s3-uploader) for automated publish to AWS S3 bucket as web server.
    - AWS CloudFront, Route 53, and Certificate Manager provide CDN, DNS and TLS certificate functionality.

### Hosting documentation

- [Amazon S3 - Configuring a Static Website](https://docs.aws.amazon.com/AmazonS3/latest/dev/HostingWebsiteOnS3Setup.html)
- [Configuring a Static Website Using a Custom Domain Registered with Route 53](https://docs.aws.amazon.com/AmazonS3/latest/dev/website-hosting-custom-domain-walkthrough.html)
- [Use CloudFront to serve a static website hosted on Amazon S3](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/)
- [CloudFront - Using Alternate Domain Names and HTTPS](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/using-https-alternate-domain-names.html) | [Configuring Alternate Domain Names and HTTPS](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cnames-and-https-procedures.html)
