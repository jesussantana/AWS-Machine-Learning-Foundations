# Training the Transformer-XL to generate music
## What is AWS DeepComposer? 
AWS DeepComposer provides a creative, hands-on experience for learning generative AI and machine learning. With generative AI, one of the biggest recent advancements in artificial intelligence. With AWS DeepComposer, you can experiment with different generative AI architectures and models by creating and transforming musical inputs and accompaniments to create compositions.

Regardless of your experience with machine learning (ML) or music, you can use AWS DeepComposer to develop a working
knowledge of generative AI. AWS DeepComposer includes learning capsules, sample code, and training data to help you
understand and use generative AI models. 

**Note** 
> To use the AWS DeepComposer console and other AWS services, you need an AWS account. If you don't have an account, 
go to aws.amazon.com and choose **Create an AWS Account**. For detailed instructions, see [Create and Activate an AWS Account](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/).

>As a best practice, you should also create an AWS Identity and Access Management (AWS IAM) user with administrator
permissions and use that user for all work that doesn’t require root credentials. 

>To use the AWS Command Line Tool (AWS CLI), create a password for console access, and access keys. For more information, see [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html) in the *AWS IAM User Guide*.

## Prerequisites 
The best way to understand how to use this notebook is to read the following learning capsule first:
[Learn more about the Transformer technique](https://console.aws.amazon.com/deepcomposer/home?region=us-east-1#learningCapsules/transformerTechnique)

If you’re unfamiliar with Amazon SageMaker, also read [Getting started with Amazon SageMaker notebook
instances and SDKs](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-console.html)in the *Amazon SageMaker Developer Guide*.  


### Request a Service limit increase for use with a Amazon SageMaker Notebook Instance
To train the Transformer-XL model using an accelerated computing instance will decrease the amount of time required to train the model. When you create your **Notebook instance** we recommend that you select the `ml.p2.xlarge` instance. To use that instance you need to request a service Service limit increase.  

1. Open the [AWS Support Center console](https://console.aws.amazon.com/support/home?#/case/create)
2. On the AWS Support Center page, choose **Create Case** and then choose **Service limit increase**.
3. In the **Case classification** panel under **Limit type**, search for SageMaker.
4. In the Request panel, choose the **Region** that you are working in. For **Resource Type**, choose **SageMaker Notebooks**.
5. For **Limit** choose **ml.p2.xlarge** instances
6. For **New Limit Value**, verify that the value is **1**
7. In **Case description**, provide a brief explanation of why you need the Service limit increase. For example, I need to use this compute optimized notebook instance to train a deep learning model using TensorFlow. 
8. In **Contact options**, provide some details about how you would like to be contacted by the AWS service support team on the status of your **Service limit increase** request.

9. Choose **submit**.

After you submit your servive limit increase it can take 2-3 days for it to be approved.  

## Creating a notebook instance
To start creating a custom *Transformer-XL* model, launch a SageMaker notebook instance.

**Note**
>Jupyter notebooks are open-source web applications that you can use to create and share documents that contain live code, equations, visualizations, and instructions.
>The AWS DeepComposer Jupyter notebook in this repo contains code that shows how to train a custom Transformer-XL with SageMaker and AWS DeepComposer.

**Creating a SageMaker training instance**

1. Open the [Amazon SageMaker console](https://console.aws.amazon.com/sagemaker/home?region=us-east-1#/dashboard).

2. In the navigation pane, choose **Notebook instances**.

3. On the **Notebook instances** page, choose **Create notebook instance**.

4. On the **Create notebook instance** page, for **Notebook instance name**, enter your notebook name and then choose the  **ml.p2.xlarge** instance.

5. Choose your **IAM Role** to set up the correct permissions and encryption. If you already have an Amazon 
SageMaker IAM role, choose it from the list. If you are new to SageMaker, create an IAM role by choosing **Create a new role**.

6. On the **Create an IAM role** page, choose **Any S3 bucket** to give your new IAM role access to any S3 bucket you might create.

7. Choose **Create Role**. 

8. On the **Create notebook instance** page, for **IAM role**, choose your newly created IAM role.

9. Open the **GitHub repositories** panel. For **Default repository,** choose **Clone a public Git repository to this notebook instance only**.

10. The GitHub repository called [transformer-xl](https://github.com/aws-samples/aws-deepcomposer-samples/tree/master/transformer-xl) contains the Jupyter notebook 
required for this custom project. Copy this link and paste it into the field under **GitHub repositories**.

11. Choose **Create notebook instance**.

12. On the **Notebook instances** page, choose **Open Jupyter** to launch your new Jupyter notebook.

13. On the **Jupyter screen**, choose **New* and then choose the `conda_python3` virtual environment. This launches your new Jupyter notebook.


## Troubleshooting

You can reach out to the AWS DeepComposer engineering team for additional support by visiting the [AWS DeepComposer forum](https://forums.aws.amazon.com/forum.jspa?forumID=361)
 
## Legal

```
  Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
  
  Licensed under the Apache License, Version 2.0 (the "License").
  You may not use this file except in compliance with the License.
  You may obtain a copy of the License at
  
      http://www.apache.org/licenses/LICENSE-2.0
  
  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
```


