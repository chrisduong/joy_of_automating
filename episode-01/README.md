# Episode 1 - Scripts to Recipes (Tomcat on CentOS 7)

## Details

Air Date: March 18, 2016 10AM PDT

Converting the application installation and configuration instructions into tested recipes. In this episode we initially install Tomcat onto CentOS 7.

* [Live Show](https://www.youtube.com/watch?v=SYJjYO9saD8)
* Recording - NOT YET AIRED

## Resources

### Activity

In this episode we focus on taking the manual installation instructions found in [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-8-on-centos-7) and create a recipe that does the work for us.

* [How to Install Apache Tomcat 8 on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-8-on-centos-7)

### Further Activities

After completing the initial activity we encourage you to challenge yourselves with the following activities.

* Refactoring to Attributes

It is common to want to make certain values configurable within a cookbook. To do that we often refactor hard-coded values into attributes. While we do not have requirements driving us to change the code this is a good time to practice this technique.

In the episode we extracted the version number into a node attribute. Find other values within the recipe that you may want to define as node attributes.

* Desired State

When we use Test Kitchen to converge our test instance we are continually left with a few resources that are constantly taking action. This is inefficient if the system is already in the desired state. It is also noisy as they are constantly being reported in the output.

One way we can counter these 'wasteful' resources is through [resource guards](https://docs.chef.io/resources.html#guards). These guards allow you to define additional tests that are executed before the a resource takes action. Find a resource within the recipe that could implement a guard statement to stop it from executing. Then define that guard with the correct command to execute.

Another way is through [resource notifications](https://docs.chef.io/resources.html#notifications). When a resource defines a notification it will contact that resource when it takes action. This allows you to step up an "If This Then That" (IFTTT) chain of events. Find two resources within the recipe that appear dependent on one another. If one resource takes action then this other resource should take action. Then define a notification in the first resource to contact the second resource.
