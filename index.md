## Onramper Test

The following changes have been deployed :

https://github.com/umvahed/action-deploy-aws-static-site/blob/master/src/static-page-stack.ts

I have added RoutingRules within the WebsiteBucket as follows :
 websiteRoutingRules: [{
      hostName: 'index.html',
      httpRedirectCode: '404',
      protocol: RedirectProtocol.HTTPS,
      replaceKey: ReplaceKey.prefixWith('users/'),
      condition: {
        httpErrorCodeReturnedEquals: '200',
        keyPrefixEquals: 'index.html',
      }
    }],
    
   Additionally, you could add a routing policy directly to the bucket : https://github.com/umvahed/action-deploy-aws-static-site/blob/master/RoutingRules.json
   
   
   Please let me know if I have understood the requirements correctly.
   
   
