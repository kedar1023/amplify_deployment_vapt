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
