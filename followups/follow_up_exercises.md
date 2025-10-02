# Follow up Exercises

## Tasks

1. Explain how code on your delivery is packaged and deployed.
2. Explain what you understand of the approach to hosting apps in the course.
3. How does this differ from approaches you've used before? What's the impact of changing our mind? and the benefits?
4. Explain the troubleshooting steps you would use on a failing pipeline, either those you learned on this course or those you have used on your delivery.
5. Identify a problem or improvement you could do on a pipeline on your delivery. What did your team decide to do to fix or improve it (even if it hasn't been prioritised yet)?

## Stretch task
1. Terraform resources to build docker images and push them to ECR is not the only way, it's not even the most usual way using github actions! Try out a new pipeline with different github actions to build and deploy the ex 6 image to the ex 6 ECR. You could start from your ex 3 pipeline syntax to build and test the node code first.
2. If you identified a different approach to hosting apps containers, investigate more and explain your discovered new approach including, what are the pros and cons of adopting it, if our start point is where the course examples left off?


## Add your answers here, or in this folder
1. My delivery has a manifest.yml in pipelines/bsl-v1 that defines the ecs machine that it will run onm providing things like the amount of memory and the cpu. There is also another manifest.yml in pipelines/bsl-benchexperiment-main which defines things such as the name of the pipeline the source (github repo) and the trigger for the pipeline which is a push to main. Lastly, there is a buildspec.yml that sets up run time environments downloads aws copilot cli and builds. It then checks if there are any jobs or services running, if not it raises an error which prevents the pipeline from deploying. 

2. The pipeline was seperated into two parts, CI and CD. CI featured the steps involved with setting up the environment for the runner, building the code and running tests on the code. CD involves steps such as deploying the app to a dev stage first to run more testing and then deploying to production.

3. I previously used the terraform and github actions on the end of bootcamp project so this course doesn't differ much to the approach we used on the project. However, this course was very useful for me to gain more confidence in writing my own pipelines from scratch and debugging terraform issues and other pipeline bugs. It also helped me to understand the different steps involved in a pipeline and how I would want them to behave.

4. I would start by running the pipeline and reading the error messages. After this I would go and fix the cause of the issue, supporting myself with information from aws console or other resources. I would then check the pipeline again to see if it works, if not I would repeat the steps again.

5. The buildspec.yml in my delivery is quite unreadable due to the fact it is written with some very complex bash and the comments that document the code do not explain it in enough detail to be able to understand what certain blocks of the script are doing. I would fix this by making some variable names more understandable and reduce the amount of one liners to increase the readability of the script and add more comments to the script.