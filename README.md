# ApplicationSecurity
A repo containing work related to application security.

* Regarding the Artemis Financial Security Document

- Briefly summarize your client, Artemis Financial, and their software requirements. Who was the client? What issue did they want you to address?
  
Artemis financial is company that produces a banking application that allows customers to perform various actions against their accounts. Their requirements were security based - ensure their application security is up to industry standards. 

- What did you do very well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall wellbeing?
  
The code base in question here was lacking several security features. Specifically there was no authentication/authorization, no input validation and sanitizing of user inputs, no error handling and logging features and the code had not been statically tested, leaving it open to vulnerabilities within out of date dependent pacakges. Without these pieces, Artemis left themselves open to several different attack vectors, which could result in unauthorized access to their data. Exposing senstive customer data, especially financial data, is a major security breach that erodes customer trust and harms the success of the business.

- What part of the vulnerability assessment was challenging or helpful to you?

  The vulnerability assessment is really straight forward, oWasp and Java make it really easy to scan dependent packages, building a list that lays out all needed information to address issues. The challenging portion becomes when you have an application that hasn't had proper lifecycle management - the list of vulnerabilities can be extremely long, requiring a significant time investment to resolve each dependency issue and ensure application stability. An application with regular lifecycle management can keep these findings low by addressing them on a regular basis - reducing the amount of time spent on tech debt thereby allowing time for new features and innovation.

- How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?

In a few ways - First by updating all dependent packages called out on the report. Secondly, we added input validation around user inputs, ensuring we weren't blindly reusing data coming from end users. We also created stories (future work) for adding authorization and authentication of users and to secure communication with TLS and SSL certs (added bonus = identity validation). 

- How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?

After adding code/new dependencies we should be rerunning our depedency checks. In fact, if we have a proper CICD pipeline we should be running these checks as we check the code into our code repo, rejecting any merges if our checks/tests fail. Part of that pipeline should include running unit and integration test - cycling through code functionality ensuring soundness and accuracy of the changes. 

- What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?

I like using the Owasp site to get more information on particular vulnerabilities and fixes. I like to build my own virtual machine and converge code locally when I test, I can use tools like virtual box, vagrant, qemu-kvm and Chef to build a local VM with Ubuntu, converge my application and build my stack, and then run my tests ad nauseum testing different configurations. 

Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?

I think the biggest thing to take from this assignment is my general approach to identifying and fixing gaps in software security. I firmly believe in having a security focus when building and maintaining applications and that it is every engineers responsibility to wear a security hat. I think teams should be devoting development cycles to lifecycle managment, setting goals to find and remediate findings and eliminate technical debt. Teams should have security built into their application AND their CICD pipelines, taking a multi-pronged approach to secure their stacks and protect company assets.  
