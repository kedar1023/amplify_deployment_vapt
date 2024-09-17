# amplify_s3_deployment

This template should help get you started developing with Vue 3 in Vite.



## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
### Addtional COmmands to zip the files at root folder and push to s3
         - npm install
         - npm run build
         - ls -ltr
         - cd dist
         - zip -r ../code.zip .
         - ls -ltr
         - cd ..
         - aws s3 cp code.zip  s3://$BUCKET_NAME
         - ls -ltr
         - aws amplify start-deployment --app-id $AMPLIFY_APP_ID --branch-name $BRANCH_NAME --source-url s3://$BUCKET_NAME/code.zip

### Additional Headers to Be Added
customHeaders:
  - pattern: "*.*"
    headers:
      - key: Strict-Transport-Security
        value: max-age=31536000; includeSubDomains
      - key: X-XSS-Protection
        value: 1; mode=block
      - key: X-Frame-Options
        value: ALLOW-FROM https://url
      - key: Content-Security-Policy
        value: script-src 'self' https://cdn.jsdelivr.net/;  frame-ancestors
          http://allowed-domain.com/ ;
      - key: Cache-Control
        value: no-store
      - key: Referrer-Policy
        value: Origin-when-cross-origin
      - key: X-Content-Type-Options
        value: nosniff
