---
layout: post
title:  "Keynote Machine Learning"
categories: reinvent2022 keynote machine-learning
permalink: /:categories/:title
---

# Machine Learning Keynote

[Swami Sivasubramanian's keynote](https://www.youtube.com/watch?v=TL2HtX-FmiQ) focused on machine learning, with new services and features for the managed service SageMaker. To build, train, and deploy models using geospatial data, there is the [preview release of SageMaker‘s geospatial capabilities](https://aws.amazon.com/blogs/aws/preview-use-amazon-sagemaker-to-build-train-and-deploy-ml-models-using-geospatial-data/). The new geospatial image can be used to transform and visualize data inside geospatial notebooks using open-source libraries such as NumPy, GDAL, GeoPandas, and Rasterio.

[New machine learning governance tools](https://aws.amazon.com/blogs/aws/new-ml-governance-tools-for-amazon-sagemaker-simplify-access-control-and-enhance-transparency-over-your-ml-projects/) were announced, improving access control and transparency for ML projects.

It is now possible to share artifacts, such as models and notebooks, with other users using [SageMaker JumpStart](https://aws.amazon.com/blogs/aws/new-share-ml-models-and-notebooks-more-easily-within-your-organization-with-amazon-sagemaker-jumpstart/). To increase efficiency across the development workflow, a [newer version of SageMaker Notebooks](https://aws.amazon.com/blogs/aws/next-generation-sagemaker-notebooks-now-with-built-in-data-preparation-real-time-collaboration-and-notebook-automation/) was introduced together with [support for shadow testing](https://aws.amazon.com/blogs/aws/new-for-amazon-sagemaker-perform-shadow-tests-to-compare-inference-performance-between-ml-model-variants/).

> Shadow testing helps you build further confidence in your model and catch potential configuration errors and performance issues before they impact end users. Once you complete a shadow test, you can use the deployment guardrails for SageMaker inference endpoints to safely update your model in production.
>

[Glue for Ray](https://aws.amazon.com/about-aws/whats-new/2022/11/aws-glue-ray-preview/) helps data engineers process large datasets with Python and Python libraries. [Olalekan Elesin](https://www.linkedin.com/in/elesinolalekan/), director of data platform at HRS Group and AWS Machine Learning Hero, wrote an article to demonstrate how to use the new service to [train a Facebook Prophet forecast model](https://elesin-olalekan.medium.com/aws-glue-for-ray-facebook-prophet-train-large-scale-time-series-forecast-models-260ad1f2da46) in a distributed environment.

[DataZone](https://aws.amazon.com/datazone/) is a management service to share, search, and discover data at scale across organizational boundaries. All the data in DataZone is governed by access and use policies that the organization can define.
