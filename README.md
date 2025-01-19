Welcome to the Supermetrics SRE Interview!

We have a simple cluster definition using (helmfile)[https://github.com/helmfile/helmfile]. It uses by default a local Docker Desktop cluster, but you the deployment can use anything you want. The initial deployment has a simple monitoring stack that you can use.



Assignment:

In the file assignment.tar.gz you have a git repository with two branches, main and add-todo-application. The `add-todo-application` branch has been sent to you for PR review by a colleague. Please go through the changes and list any possible issues you can find. You can also fix the issues if that feels like the easiest way to go. Also try to look at the high level structure and suggest improvements.

The repository contains a cluster definition in `clusters/local/helmfile.yaml` - it can be deployed on any Kubernetes cluster using the `helmfile` application. Testing the deployment is recommended.

Please prepare to present the issues in the technical interview and prepare to answer some questions on your suggested fixes.

Important notes:

* This shouldn't require much time to work on, but we'd appreciate it if you submitted it within 5 working days.
* Once submitted (find the link for submission in this email as well), I'll share it with the team for review.
* The next stage would be the Technical Interview Assignment Presentation. I'll share more details once we get there.
* You can submit tasks in PDF, PPT, Google Docs, or any other format we can share during the meeting.

Let me know if you have any


Question 1
Please go through the changes and list any possible issues you can find.

Question 2
Also try to look at the high level structure and suggest improvements.

Improvements
1. Postgres should be a statefulset not a deployment 
2. We shouldnt use default ports 
3. Change hardcoding of values like target ports 
4. Have a pod distruption buedget for the application. It ensures that we have at least one pod running for traffic during changes 
5. Place Resource Limits 
6. Adding Taints and tolorations 
7. Database should have its own namespace for proper segmentation
8. We can add taints and tolorations to ensure the database runs on the right nodetype suited for its operations. 
9. Network Policies allows only the app to connect to the database
10. Add finalizer to the POD 
11. Add more than one replica of the todo app 