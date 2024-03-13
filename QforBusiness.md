# Amazon Q for Business

---
or GenAI's knowledge search use case, Amazon Q offers a managed solution for businesses to quickly build an AI assistant integrating with your data and systems. Just create an application and connect to your data with over [40 built-in connectors](https://docs.aws.amazon.com/amazonq/latest/business-use-dg/connectors-list.html), and you will have a Knowledge Search assistant set up with enterprise-level security in no time.

## Use Case
In this lab, we will be building a knowledge assistant for movies, so you can quickly find out information about Storyline of the movies, release dates, similar movie titles, and more.

We'll use the [movielens](https://www.kaggle.com/datasets/prajitdatta/movielens-100k-dataset) dataset provided by kaggle. The data contains information about movie titles, cast members and more. Amazon Q will be used to integrate with these data in S3 and provide accurate answer based on your questions.

## Create an Q Application
1. Open the [Amazon Q Console](https://us-east-1.console.aws.amazon.com/amazonq/home?region=us-west-2#welcome) and click the Get Started button.
2. Click the **Create Application** button.
3. On the Create application page, give a new application name. (e.g.: movie-assistant).

![0-q-create-app.png](images%2F0-q-create-app.png)

> **_NOTE:_** If you already have a Q role, you can toggle the switch and choose from the dropdown.
> 
> Amazon Q uses service managed key by default. If you want to manage your own key, check the box and choose or create your own KMS key.

4. Click **Next**
5. Select **Use native retriever** and use default 1 index unit.

![1-q-select-retriever.png](images%2F1-q-select-retriever.png)

> **_NOTE:_** Amazon Q for Business leverages Amazon Kendra. if you already have a Kendra instance, you can use it as an existing retriever. 
> 
> Index units configures number of document you can index and how much ingestion processing power you have. Review [Amazon Q pricing](https://aws.amazon.com/q/pricing/) for more detail.

6. Click **Next**
7. Click on the + next Amazon S3.
8. Fillout the data source detail as shown in screenshots below:

- Give a data source name

![2-s3-data-source-01.png](images%2F2-s3-data-source-01.png)

- Create a new role

![2-s3-data-source-02.png](images%2F2-s3-data-source-02.png)

- Configure Source Scope, Sync Mode and Schedule

![2-s3-data-source-03.png](images%2F2-s3-data-source-03.png)

> **_NOTE:_** Notice you can only enter the bucket for the data source location, but you can use advance settings and filter patterns for specific S3 prefixes.

9. Click on **Add data source**
10. Review the connect data sources page and click on **Create application**

![3-data-source-review.png](images%2F3-data-source-review.png)

## Synchronize the data
11. Click the new application from the list
12. Wait for your data source state to be **Active**, click on your data source (This make take a few minutes)

![4-data-source-sync.png](images%2F4-data-source-sync.png)

13. Under Sync history, click **Sync now**

> **_NOTE:_** This Syncing may take some time, be patient. We will move on configuring other things
> 
> Also, you can always edit and add more data connectors, but there is a [limit](https://docs.aws.amazon.com/amazonq/latest/business-use-dg/quotas-regions.html). 
> 
> Once the sync is done, you have access to CloudWatch logs to review any processing issues.

## Admin Control and Guardrail
In here you can configure security behavior and add guardrail for your assistant.

14. On the side menu of your application detail page, click **Admin controls and guardrails**. (you may need to expand the side menu)

![5-guardrail.png](images%2F5-guardrail.png)

15. Click on **Edit** in global control to force agent to only answer from data source, add a block word, and deny file upload

![6-gloabl-control.png](images%2F6-gloabl-control.png)

16. you can also configure the assistant response when the block word is hit. Make your changes and click **Save**

17. Create a deny topic by click on **Create topic control**. Be creative.

![7-deny-topic.png](images%2F7-deny-topic.png)

> **_NOTE:_** The description is the most important. FMs uses that to identify queries associated with the topic control you're configuring.

## Preview Web Experience
18. Go back to the application detail page anc click **Preview web experience**.

![8-preview-app.png](images%2F8-preview-app.png)

19. You can configure the title, subtitle, and welcome message. The default values can be retained, and to conceal the Customize web experience dialog, the right facing arrow should be clicked.

![9-preview-config.png](images%2F9-preview-config.png)

20. Make sure the data sync is complete, and start test your knowledge search assistant.

**Example questions:**
- What are movies about Toys?
- What is the plot for movie The American President?
- What is the rating for the movie Jumanji?

![14-chat-preview.png](images%2F14-chat-preview.png)

## [Optional] Deploy the application
You need to have SAML 2.0 compliant identity provider (IdP) to deploy. This will ensure only authorized users have access to your content. if you do, proceed int the next couple steps.

21. Select your application and click **Deploy web experience**

![10-deploy-web-experience.png](images%2F10-deploy-web-experience.png)

22. Follow the steps to configure the application with your SAML 2.0 provider.

![11-config-SAML.png](images%2F11-config-SAML.png)

If you have a IAM Identity Center setup with users, you can proceed to add a new SAML 2.0 application (You need to have Amazon Q configuration open side-by-side).

23. Under Application assignments -> Applications -> Click **Add application**

24. Select **I have an application I want to set up** and "SAML 2.0"

![12-config-SAML-01.png](images%2F12-config-SAML-01.png)

25. In the Configure application, give a display name and description.

![13-config-SAML-02.png](images%2F12-config-SAML-02.png)

26. Download IAM Identity Center metadata and upload to Amazon Q.

| IAM Identity Center             |  Amazon Q for Business |
:-------------------------:|:-------------------------:
![12-config-SAML-metadata.png](images%2F12-config-SAML-metadata.png) | ![12-config-SAML-metadata-q.png](images%2F12-config-SAML-metadata-q.png)

27. copy ACS URL and SP Entity ID from Amazon Q and paste into IAM Identity Center.

|  Amazon Q for Business                      |  IAM Identity Center |
:-------------------------------------------------------------:|:-------------------------:
![12-config-SAML-ACS-q.png](images%2F12-config-SAML-ACS-q.png) | ![12-config-SAML-ACS.png](images%2F12-config-SAML-ACS.png)

28. Add Email attribute of SAML assertion and click **Deploy** to publish Q application.
29. 
![12-config-SAML-deploy-Q.png](images%2F12-config-SAML-deploy-Q.png)

29. At same time, click **Submit** in IAM Identity Center. You an App setup like this in your IAM Identity Center.

![12-config-SAML-IDP-app.png](images%2F12-config-SAML-IDP-app.png)

30. Click Assign Users and Groups to give user or group access.

![12-config-SAML-access.png](images%2F12-config-SAML-access.png)

31. Last step before you can access your application publicly is to map the auth attributes. Click Actions -> Edit attribute mappings

![12-config-SAML-mapping.png](images%2F12-config-SAML-mapping.png)

32. Your App is configured, you can find the public URL in your **Web experience settings**

![13-published-url.png](images%2F13-published-url.png)

> Congratulations! You have successfully created a GenAI powered movie assistant using [Amazon Q](https://aws.amazon.com/q/business-expert/).




