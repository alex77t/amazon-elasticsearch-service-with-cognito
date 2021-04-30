
### Access the Example Dashboard

As soon as the application is deployed completely the outputs of the AWS CloudFormation stack provides the links for the next steps. You will find two URLs in the AWS CloudFormation console called `createUserUrl` and `kibanaUrl`.

![AWS CloudFormation outputs](img/cfn_outputs.png)

* Use the `createUserUrl` link from the outputs, or navigate to the Amazon Cognito user pool in the console to create a new user in the pool. **Enter an email address as username and email**. **Enter a temporary password** of your choice with at least 8 characters. Leave the phone number empty and **uncheck the checkbox to mark the phone number as verified**. If you like you can check the checkboxes to send an invitation to the new user or to make the user verify the email address. Then choose **Create user**.

    ![Create the user in the Amazon Cognito user pool](img/create_user.png)

* The user has access restricted to the `logs-tenant`. If you want to provide full access control, including security management permissions, add the user to the `es-admins` group:

    ![Add the user to the es-admins group](img/user_admin_group.png)

* Access the Kibana dashboard with the `kibanaUrl` link from the outputs, or navigate to the Kibana link displayed in the Amazon Elasticsearch Service console.

* In Kibana, go to the tenant selection by choosing the **user menu** on the top right. Choose **Switch tenants**:

    ![User menu](img/switch_tenants_1.png)

* Choose the `logs-tenant` that has been created during the launch of the application. Choose **Confirm**.

    ![User menu](img/switch_tenants_2.png)

* Choose the **navigation menu** on top left and choose **Dashboard**. Choose the **Example Dashboard**. The dashboard contains instructions to add new documents to the search index and to visualize the documents with the graph in the dashboard.

    ![Screenshot of the example dashboard](img/example_dashboard.png)


## FAQs

### Q: In which region can I deploy the sample application?

The Launch Stack button above opens the AWS Serverless Application Repository in the US East 1 (Northern Virginia) region. You may switch to other regions from there before deployment.

### Q: How much do resources in this template cost?

Standard AWS charges apply to the resources you deploy with this template.

Amazon Elasticsearch Service provides customers in the [AWS Free Tier](https://aws.amazon.com/free/) free usage of up to 750 hours per month of the configuration in this template, i.e. a single-AZ `t3.small.elasticsearch` instance and 10GB of EBS storage for up to one year from the date the account was created. If you exceed the free tier limits, you will be charged the Amazon Elasticsearch Service rates for the additional resources you use.

The Amazon Cognito User Pool feature has a free tier of 50,000 monthly active users for users who sign in directly to Cognito User Pools. The free tier does not automatically expire at the end of your 12 month AWS Free Tier term, and it is available to both existing and new AWS customers indefinitely.

See offer terms of [Amazon Cognito](https://aws.amazon.com/cognito/pricing/) and [Amazon Elasticsearch Service](https://aws.amazon.com/elasticsearch-service/pricing/) for more details.


## License

This library is licensed under the MIT-0 License. See the [LICENSE](LICENSE) file.
