**GitHub Actions workflows status**

![](https://img.shields.io/github/workflow/status/kaskadi/kaskadi-webhooks-api/deploy)

:point_right: **Badges here** :point_left:

****

# Add new endpoints

In order to add new endpoints, you can:
1. use `template-kaskadi-lambda` to create a new Lambda from our Lambda template
2. develop your lambda
3. configure its `serverless.yml` so that it can attach itself to this API (see `template-kaskadi-lambda` repository for more details)

# Using custom domain for your API

_For all custom domains you will need a certificate for this domain. Please make sure that you have the proper certificate generated, else create one associated with your domain. All this can be done [here](https://console.aws.amazon.com/acm/home?region=us-east-1#/)_

**Case 1: creating a new custom domain for API**

If the custom domain you wish to use hasn't been created yet (list of custom domains [here](https://eu-central-1.console.aws.amazon.com/apigateway/home?region=eu-central-1#/custom-domain-names)).

1. Go [here](https://eu-central-1.console.aws.amazon.com/apigateway/home?region=eu-central-1#/custom-domain-names) and click on _Create Custom Domain Name_
2. Configure your domain as you wish to
3. Once the domain is created and initialized, go to [Route 53](https://console.aws.amazon.com/route53/home?region=eu-central-1)
4. Go into the _Hosted Zone_ for the domain you wish to use and create a new _A Record_.
5. For this record, you should toggle the _Alias_ option, give for _name_ the custom domain name you wish to use and select for _Alias target_ the API you want to map to this domain. You may need to copy paste the base URL to that API to make this work

**Case 2: using an existing custom domain**

1. Go [here](https://eu-central-1.console.aws.amazon.com/apigateway/home?region=eu-central-1#/custom-domain-names)
2. Click on _Edit_ for the custom domain you wish to use
3. Add a base path you wish to map your API to for this domain and then select the API & its stage in the dropdown menus

**Attention:** you can only use an existing custom domain if this domain doesn't have already an empty path as base path.

****

:point_down: **Your documentation here** :point_down:
