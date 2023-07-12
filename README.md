# Github Actions: 
1. Automate, customize, and execute your software development workflows right in your repository with GitHub Actions.
2. GitHub Actions also provides the facility to build end-to-end Continuous Integration (CI) and Continuous Deployment (CD) capabilities directly in the repository.
3. You can also use GitHub Actions to automate other tasks, such as sending notifications, running scripts, managing pull requests and issues, and much more.
4. For example, you can use GitHub Actions to automatically build and test your code every time you push a commit to GitHub. This ensures that your code is always up-to-date and working as expected.
5. GitHub Actions are highly customizable. You can create your own actions or use actions from the GitHub Marketplace to build workflows that meet your specific needs. For example, you can use a pre-built action to deploy your code to a specific cloud provider. Or you can create your own action to run a custom test suite.
6. You can also use GitHub Actions to automatically close issues or assign them to specific team members.

# Github Actions Components: 
1. Events: An event is anything that can happen on a Github repository. This goes from pushing a code, creating a branch, opening a pull request, and even commenting on an issue.
2. Workflows: A workflow is the main building block of GitHub Actions. It's an automated process defined in a YAML file (typically called workflow.yml) that describes a series of steps to be executed. Workflows are triggered by events such as code pushes, pull requests, or scheduled intervals.
3. Jobs: A job is a series of tasks that gets executed in a workflow upon being triggered by an event. Each step is either a script or a Github action. A workflow can have multiple jobs that run in parallel.
4. Runners: A runner is a server that runs your workflows when they’re triggered. Each runner can run a single job at a time. GitHub provides hosted runners with pre-installed software and tools, or you can set up your own self-hosted runners on your infrastructure.
5. Actions:  An action is a reusable unit of code that performs a specific task. Actions can be created by GitHub or the community, and they can be used in workflows to automate common development processes or customize your own workflows. Actions are typically stored in public repositories on GitHub.

# Jenkins vs Github Actions:
1. With Jenkins, you will be running it on a custom server. This means that you will have to maintain the Jenkins server continuously. However, Github Actions provides you with free runners you can use to perform your CI/CD operations. These runners are owned and maintained by Github but you can add self-hosted runners as well.
2. Jenkins deployments are typically self-hosted, with users maintaining the servers in their own data centers. GitHub Actions offers a hybrid cloud approach by hosting its own runners that you can use to run jobs, while also supporting self-hosted runners.

# Creating first Github Workflow – Hello World
1.	Create a .github/workflows directory in your repository on GitHub if this directory does not already exist.
2.	In the .github/workflows directory, create a file named hello-world.yml. 
3.	Copy the following yaml content into your hello-world.yml file

![image](https://github.com/srivapra/first-github-action/assets/138867223/17b1dd8b-fe4d-41a2-944e-6e81e472827a)

4. Commit the changes into your Github branch.
5. Committing the workflow file to a branch in your repository triggers the push event and runs your workflow.
6. After committing the file, navigate back to the Actions tab. We will see that our workflow has successfully run, as shown by the green checkmark. Click on update hello-world.yml' to see the details of our workflow.

![image](https://github.com/srivapra/first-github-action/assets/138867223/d8357c47-3b05-4f60-a24d-37584eca33a8)

7. In the detailed view, we can see our 2 jobs "Hello and goodbye”
8. We can check the logs of hello and goodbye jobs also. Click on hello jobs and you can see that “Hello World” is printed
![image](https://github.com/srivapra/first-github-action/assets/138867223/384d347e-391d-4535-9caa-bea7ed61aa00)

9. Click on goodbye jobs and you can see that “Goodbye World” is printed
![image](https://github.com/srivapra/first-github-action/assets/138867223/dffa90fd-41ad-4bf8-9437-59a143412546)

# Let's discuss a few important attributes to know from this YAML code above.
1. Name: The first attribute in the workflow is name. This is an optional attribute used to identify the workflow. It is useful when you have multiple workflows under 1 repository. If this attribute is not supplied, it will simply default to its filename instead. In our example, I have named it 'Hello World Workflow'.
2. On: This is an important attribute that indicates when the workflow will be run. In our example, it will be triggered on the push and pull_request events, specifically on the main branch only. It can also be triggered manually via the Actions tab, as defined by the workflow_dispatch event.
3. Jobs: Jobs are a series of steps that makes up a workflow. In this example, we only have 2 job called hello and goodbye.
4. Runs-on: Under each job, you must have a runs-on attribute. This attribute indicates the virtual environment the job is running on. In this example, our build job is running on the latest Ubuntu version
5. Steps, uses, and run : Steps are the individual tasks that makes up a job. Under our steps attribute, we can see 3 actions. An optional name attribute can be used to identify each action. The uses attribute indicates the location of the action for the job to run it. And so the first action, uses: actions/checkout@v2, checks out a copy of this repository for its job to access it. The next action is a simple command that prints "Hello, world!" on the console using the run attribute. 












