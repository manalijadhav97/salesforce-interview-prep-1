# Behavioural Section

1. [How to answer behavioral questions](https://www.youtube.com/watch?v=lJOf8EtjV8g)
   Answer all the question using the STAR methodology.
   Situation - The time when something you did and the thing you did.
   Task - What was the goal
   Action - What did you do?
   Result - What was the outcome?

1. Tell me about yourself

    Explain -
    Current Role (shows you are professional. Interviewer is not interested in your personal life and what is your hometown, this is irrelavant)

    Success Metrics (shows you are result oriented, confident and capability)

    Recent Achievement that you are proud of (keeps the interviewer enagaed with your stroy and makes her/him curious about you. DO NOT TRY TO IMPRESS)

		Explain what are you and what do you currenty? what is your team's current goal? increase the enablement

		Explain leadership activities and initiatives you took

		Explain about past - concise, relevant, finish under 1 minute, select one key highlight from each experience

		Explain about future - as someone dong coding i'd like to apply my knowledge. my experience combined by international background makes me a perfect fit for this position.
		Highlight something you have done - increased overall to 40%

    Methods-
    Past, Present, Future method
    Highlight Method

    Must Watch -
    https://www.youtube.com/watch?v=es7XtrloDIQ


Hi, my name is Girish Shinde and I have a total of 5 years of experience in Salesforce and Software Industry in all sorts of roles such as developer, scrum master and recently a product manager.


I started my Salesforce development career 5 years ago in Accenture. While in Accenture, I was working for VMware where I worked on multiple projects in Service cloud including Knowledge Management Implementation and Classic to Lightning Migration and Experience Cloud implementation.


I later went on to join VMware in the same team with a new role. There, I took on the role of dev lead from India site and worked on projects such as cross platfrom integration and performance optimization to enhance the customer service experience.


After spending more than 4 years in VMware, I joined PayPal as a Senior Software Engineer, where my current role is to lead and deliver different business process for customer service platform along with other cross functional teams such as business, product, UX.


Apart from working on the business processes, I have also been part of many initatives such as building logging frameworks for UI, cleaning organizing the codebase etc. Apart from Salesforce, I have also volunteered in contrinuting to PayPal's internal skill exchange portal as a Java backend developer.


Since I wanted to understand more of the business side, recenty, I took on a new challenge of working as a Product Manager while continuing the dev lead role.


I wish to use my technical acumen to contrinute to a team like Delivery Hero that works at scale and creates a positive impact on a society.


1. Why Do You Want to Work Here?

1. Question to ask interviewer after the interview

    - Ask about themselves
    - Ask questions about the role
    - Ask questions about the company

---

### FA Behavioural Qs

1. How do you handle criticism - introspection and work on it
1. How do you criticize - let them know in a way that will help them getting better, for ex. what would have happened good if they did/did not have done that.
1. What is the worst feedback you have got - complaining (was not saying no, got burned out)
1. What does your past work aligns with this job role?
1. How will you handle the situation where you got into an argument with co-worker over implementation of a feature? What if manager supports the person with their decision? And What will be your reaction after something goes wrong with the co-worker's solution in Production and you know your solution would have worked? (the classic Told you so moment)

---

## Interview Experiences

#### 1. PayPal

##### Round 1 (Problem Solving + Technical Coding + Platform Knowledge) -

|      |                  |
| ---- | ---------------- |
| With | Senior Developer |
| Time | 1 Hour           |

1. Tell me about your current role in the team.
1. Write a code to store number of occurences of each integer in array.
1. What are multiple ways to call apex in lwc?
    - wire and imparatively.
1. How to pass parameters to apex method from lwc?
1. How to show data in template from JS? How to get particular field?
1. What are Promises in JS?
1. Write a trigger for given scenario.
   A custom Shipment object has a lookup on Account object and a has a custom field Quantity.
   Account has a custom field called Total Shipment Quantity which is sum of quantites of all the related shipments of the account.
   write a trigger to calculate the sum of all shipment quantities and store in Total Shipment Quantity field on Account.
1. How to communicate from child LWC to Parent LWC?
1. Any questions for me?

##### Round 2 (Technical depth, Coding) -

|      |                |
| ---- | -------------- |
| With | Lead Developer |
| Time | 1 Hour         |

1. Tell me about your current role in the team.
1. Write a lwc to get data from apex and show the data in the remplate

Student\_\_c Object -

| Degree   | Name     | Age |
| -------- | -------- | --- |
| B. Tech. | Ross     | 30  |
| MBA      | Monica   | 28  |
| B. Tech. | Chandler | 30  |
| MBA      | Rachel   | 27  |
| MA       | Joey     | 29  |
| MBA      | Pheobe   | 28  |

**Excpeted Output in LWC**

<table>
    <thead>
        <tr>
            <th>Degree</th>
            <th>Name</th>
            <th>Age</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=2>B. Tech.</td>
            <td>Ross</td>
            <td>30</td>
        </tr>
        <tr>
            <td>Chandler</td>
            <td>30</td>
        </tr>
        <tr>
            <td rowspan=3>MBA</td>
            <td>Monica</td>
            <td>28</td>
        </tr>
         <tr>
            <td>Rachel</td>
            <td>27</td>
        </tr>
        <tr>
            <td>Pheobe</td>
            <td>28</td>
        </tr>
         <tr>
            <td>MA</td>
            <td>Joey</td>
            <td>29</td>
        </tr>
    </tbody>
</table>

1. From above table, make the age field editable and whenever any age is modified, related name should be displayed in alert

1. How to establish communication betn two non related lwcs? assume they are on the account record details page.
   Ans - lms,pubsub,custom events

1. How to securely store api keys?
   Ans - Named credentials

1. What is the difference between future and queueable apex?

1. Why does the future method not allow non primitive data types whereas queueable allowes.
   Ans - The complex data types are passed by reference and not by value so by the time the future method gets executed, the state of the complex types might get changed and the future method might still refer to the old data

1. Whenever an Account is updated, another web application should be informed about the record change. this should be done immidiately when account is updated.
    1. In how many ways can we implement this?
       Ans - Workflow Outbound Message, Trigger, Platform Events.
    1. What if we have to do this asynchronously?
       Ans - Batch, Platform Events (check if this is possible)
1. Any questions for me?

##### Round 3 (System Design) -

|      |                |
| ---- | -------------- |
| With | Staff Engineer |
| Time | 1 Hour         |

1. Tell me about your current role in the team.
1. Given an employee table, design a system that prints org chart of the employees with thier manager and imidiate reportees (like in Role Hierarachy in salesforce).

Functionalities of the Org Chart -

1. We can find employee by thier name
1. Clicking on the employee name will show a tree structure that shows the manager of the employee and it's immidiate employees.
1. What is your tech stack? (Aura/LWC, Apex etc.)
1. How many components will be there
1. Give end-to-end design and explain how it will work.

| Employee Id | Name     | Manager Id |
| ----------- | -------- | ---------- |
| 1           | Ross     |            |
| 2           | Monica   | 1          |
| 3           | Chandler | 2          |
| 4           | Rachel   | 1          |
| 5           | Joey     | 3          |
| 5           | Pheobe   | 2          |

Follow up questions -

1. Will you build new component right away?
1. Will you use any external libraries to present data? If yes name what libraries will you use?
1. What if there is already a packge on AppExchange that provides this functionality?

1. Can we package code in Apex?
1. Any questions for me?

##### Round 4 (Behavioural) -

|      |                |
| ---- | -------------- |
| With | Hiring Manager |
| Time | 1 Hour         |

1. When was a time when you took some initiative and it was implemented? (this is a leadership question)
1. Any questions for me?

#### 2. Zoom
##### Round 1 (Screening + Platform Knowledge ) -

|      |                |
| ---- | -------------- |
| With | Hiring Manager |
| Time | 1 Hour         |

1. Tell me about your current role and responsibilities.
1. If I update the child record in MD relationship, what impact does it have on the parent record? (It locks the parent record)
1. What is the row lock timout limit? (a record will be locked for max 10 seconds and then error will be thrown)
1. How to avoid row lock on account when doing bulk data load (updating more then 20 million reocrds) on one of the chid objects of the account.
1. Why did you choose LWC over Aura?
1. Differentiate between future, batch and queueable.
1. Have you come across any governor limits? how did you tackle them?
1. What are some best practices in Salesforce?
1. Have you worked on apex? what have you done in apex?
1. When did you use batch apex? what was the use case?
1. What is the difference betn list and map?
1. Have you faced any challanges in the past and how did you overcame those?
1. Why did you particualry for Batch Data Activity for Knowledge Article Migration and why didn't choose Bulk API?
1. Why do you want to leave your current organization?
1. Any questions for me?

# Behavioural

Tell Me about yourself
2. Explain what are you and what do you currenty? what is your team's current goal? increase the enablement
3. Explain leadership activities and initiatives you took
4. Explain about past - concise, relevant, finish under 1 minute, select one key highlight from each experience
5. Explain about future - as someone dong coding i'd like to apply my knowledge. my experience combined by international background makes me a perfect fit for this position.
6. Highlight something you have done - increased overall to 40%


1. Why are we using Salesforce - reduce average case hadling time, out of the box features, architeture, cross functional teams, TMs love this since it is all info is presented



Why do you want to work here? (why are you interested in this position)
Migrate to Germenay for better quality of life
one of the fastest growing Startup in germany - i have been following DH for quite a long and the WLB as well as comapanies initiatives 


Conflict
Aaction
Result
Learning
