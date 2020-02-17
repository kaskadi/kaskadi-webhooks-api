**GitHub Actions workflows status**

![](https://img.shields.io/github/workflow/status/kaskadi/kaskadi-webhooks-api/deploy)

:point_right: **Badges here** :point_left:

****

# :warning: Disclaimer :warning:

On first deployment you may encounter an error message related to an issue with your stage.

**This is normal** and should not alarm you. Your API will be properly deployed.

The reason behind is that `serverless` seems to try to look for lambda functions to deploy in the given stage with your API. Since in this case there are no functions, the deployment send back an error message as feedback. But this behavior is not a problem on _Cloud Formation_ level and does not prevent _AWS_ from spinning up your _API Gateway_.

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

For this, simply follow **_Case 1_** from **_Step 3_**.

**Attention:** a domain cannot be mapped with more than one _A Record_ at a time. This means that for each API you will need a custom domain if you wish to use one.

****

:point_down: **Your documentation here** :point_down:
