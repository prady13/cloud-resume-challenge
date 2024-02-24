# cloud-resume-challenge
It is project to put my resume in HTML on the cloud on AWS. It is a multiple-step resume project which helps build and demonstrate skills fundamental to pursuing a career in Cloud. The project was published by Forrest Brazeal.

Step 1: To create a S3 bucket to upload all the files of the website in the bucket.
<img width="1440" alt="Step 1" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/251cb1ca-8af4-42a5-87dd-fbd1716b8fa3">

Step 2: Since we have blocked the public access on the bucket, we need to create a cloudfront distribution and a policy so that cloudfront can access the bucket files and provide a link which will be global and public.
<img width="1440" alt="Step 2" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/2c8a1bdc-fc72-4fd9-a361-01bdd30146c8">


It will be visible as this:
<img width="1440" alt="Screenshot 2024-02-24 at 6 43 28 PM" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/29a5667b-cfb8-4592-84fe-6ea3485430b7">


For this challenge we also need to use a custom DNS which people can buy through either Route 53 or several other websites. (but i did not buy a custom domain)

Step 3: We have to create a DynamoDB table which will store the views count when the website has been visited.
<img width="1440" alt="Step 3" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/e05a57e3-b8d4-4dd7-a5e8-d0a047231f99">
create the table, setting the attributes.

Step 4: We will need to create an API that accepts requests from your web app and communicates with the database. I suggest using AWS’s Lambda for this. We are not using an API gateway instead we are using fURLs provided by Lambda.
<img width="1440" alt="Step 4" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/fa9d0019-ffe4-433d-9de8-5d8fcdf41b0a">
*boto3 is a library used to interact with aws services

** i used js to show a view counter on the website so everytime someone loads the page the view count increases by 1.
** the lambda function is connected to the dynamodb and we are using that function to fetch the view count from the table
** I've used python to write the lambda function code(api)
** make sure the lambda function has the permission to get the item from dynamodb table


the count is shown as below:
<img width="1418" alt="Screenshot 2024-02-24 at 9 13 26 PM" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/aaaaa6d5-2f01-4131-9099-41d3d1b877a9">

<img width="1440" alt="Screenshot 2024-02-24 at 9 13 41 PM" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/57ce4e1f-d2be-453c-b924-4279fbf72746">



Step 6:Now for source control we need to create a git repo and have a CI/CD front end, so that everytime we commit in git it gets pushed to the S3 bucket created on our AWS console.
<img width="1440" alt="Screenshot 2024-02-24 at 11 06 46 PM" src="https://github.com/prady13/cloud-resume-challenge/assets/62207613/2de6f78c-46d4-4b94-9642-48c4d69f9cd3">












