# amplify_deployment_vapt
Sample Vue Js application to get deploy to the Amplify

# Commands to be run 
         - npm install
         - apk add py3-pip
         - npm run build
         - ls -ltr
         - cd dist
         - zip -r ../code.zip .
         - ls -ltr
         - cd ..
         - aws s3 cp code.zip  s3://$BUCKET_NAME
         - ls -ltr
         - aws amplify start-deployment --app-id $AMPLIFY_APP_ID --branch-name $BRANCH_NAME --source-url s3://$BUCKET_NAME/code.zip

# CICD For Amplify

# Once Deploy Headers to be Added
customHeaders:
  - pattern: "*.*"
    headers:
      - key: Strict-Transport-Security
        value: max-age=31536000; includeSubDomains
      - key: X-XSS-Protection
        value: 1; mode=block
      - key: X-Frame-Options
        value: ALLOW-FROM http://URL/
      - key: Content-Security-Policy
        value: script-src 'self' https://cdn.jsdelivr.net/;  frame-ancestors
          http://alloweddomain.com/ ;
      - key: Cache-Control
        value: no-store
      - key: Referrer-Policy
        value: Origin-when-cross-origin
      - key: X-Content-Type-Options
        value: nosniff
