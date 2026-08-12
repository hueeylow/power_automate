<h2>Expense Claim Multi-Approval using Power Automate & SharePoint</h2>
<h3>1. Introduction</h3>
<p>Expense claims are a common business process that often require multiple levels of approval. Most organisation have existing expense claim system in place, but the solution came with relatively high licensing and maintenance costs.</p>

<p>This project explores how <b>Microsoft Power Automate and SharePoint List</b> can be used to provide a simpler and more cost-effective approach to managing the expense claim process.</p>

<p>
In this project, I built a <b>two-level expense claim approval workflow</b>, where a claim is first submitted to the requestor manager for approval and, once approved, is routed to the Finance Head for final approval. </p>

<p>SharePoint Lists is used to store the claim information and track its status, while Power Automate manages the approval flow, notifications, and routing between the different approval stages.</p>

<p>
One of the key advantages of using Power Automate is its ability to integrate with existing Microsoft 365 services, allowing business processes to be automated without introducing another standalone application. It also provides flexibility to modify the workflow as business requirements change.</p>

<p>
This project demonstrates how Power Automate, SharePoint, and Teams can be combined to provide <b>better visibility, structured approval handling, and timely status updates</b>, while potentially reducing the licensing overhead associated with a dedicated expense management system.</p>

<p>
In this post, I will walk through the process design, SharePoint List structure, Power Automate workflow, Teams notifications, and a step-by-step demonstration of the solution.</p>

<h3>2. Process Design Flowchart</h3>
<p>Before developing the Power Automate workflow, the expense claim approval process was mapped out to clearly define the approval stages, routing logic, status updates, and notification.</p>
<p>The process consists of 2 approval levels:</p>
<p>
<b>1.	First Level – Manager Approval <br></b>
<ul>
<li>The expense claim is submitted by the requestor</li>
<li>The request is routed to the requestor’s designated manager for approval.</li>
<li>The manager’s approval outcome is recorded in the SharePoint list.</li>
<li>Once the request has been approved by the manager, the requestor receives a notification through Microsoft Teams.</li>
<li>The approved request is routed to the Finance team for 2nd level of approval.</li>
</ul>
<b>2.	Second Level – Finance Approval<br><br></b>
<ul>
<li>Finance reviews the expense claim after the manager has approved it.</li>
<li>The Finance approval outcome is recorded in the SharePoint list.</li>
<li>Once Finance completes the approval, the requestor receives another Microsoft Teams notification with the latest approval status.</li></ul>
</p>
<br>
<p align="center">
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/00.png"/>
</p>
<h3>3. Power Automate Workflow</h3>
<p>The expense claim approval process was automated using <b>Microsoft Power Automate</b>, with <b>SharePoint list </b> used to store and maintain the expense claim records and <b>Microsoft Teams</b> used to provide real-time notifications to the requestor.</p>
<p>The workflow is designed to automate the complete approval journey from submission through to the final Finance decision.</p>
<p align="center">
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/01.png"/>
</p>

<h3>i. Expense Claim Submission</h3>
<p>The workflow is triggered when a new expense claim is submitted.</p>
<p>Once the request is created, Power Automate retrieves the relevant information from the Sharepoint list, such as:</p>
<ul>
<li>Requestor</li>
<li>Expense claim details</li>
<li>Claim amount</li>
<li>Submission Date</li>
<li>Manager</li>
<li>Approval Status</li>
</ul>
<p>The initial approval status is recorded in Sharepoint to indicate that the expense claim has entered the approval process.</p>

<p align="center">
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/02.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/03.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/04.png"/></br></br> 
</p>

<h3>ii. First Level Manager Approval</h3>

<p>The first approval stage is assigned to the requestor's manager.</p>
<p>Power Automate creates an approval request and routes it to the appropriate manager. The manager can review the expense claim and either approve or reject the request. The workflow then evaluates the manager’s response.
</p>

<b><p>If the manager approves the claim:</p></b>
<ul>
<li>The SharePoint approval status is recorded to reflect manager’s approval.</li>
<li>A Microsoft teams notification is sent to the requestor to inform them that the first-level approval has been completed.</li>
<li>The workflow proceeds to the 2nd Level Finance approval.</li>
</ul>

<b><p>If the manager rejects the claim:</p></b>
<ul>
<li>The SharePoint approval status is updated accordingly.</li>
<li>The requestor is notified through Microsoft Teams.</li>
<li>The workflow ends without proceeding to Finance.</li>
</ul>


<p align="center">
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/05.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/06.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/07.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/08.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/09.png"/></br></br>
</p>

<h3>iii. Updating Approval Status in SharePoint List</h3>
<p>After each approval stage, Power Automate updates the corresponding SharePoint record, with either Approve or Reject status.</p>

<p align="center">
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/14.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/15.png"/>
</p>

<h3>iv. Second Level Finance Approval</h3>

<p>After the manager approves the expense claim, Power Automate routes the request to the Finance team for second level of approval.</p>
<p>Finance reviews the expense claim and provides the final approval decision. The workflow again evaluates the Finance approval outcome.</p>

<b><p>If Finance approves the claim:</p></b>
<ul>
<li>The SharePoint approval status is recorded to reflect the final approval.</li>
<li>A Microsoft teams notification is sent to the requestor.</li>
<li>The expense claim approval process is completed.</li>
</ul>

<b><p>If Finance rejects the claim:</p></b>
<ul>
<li>The SharePoint approval status is recorded to reflect the final approval.</li>
<li>A Microsoft teams notification is sent to the requestor.</li>
<li>The workflow will be ended.</li>
</ul>

<p align="center">
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/10.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/11.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/12.png"/></br></br>
  <img alt="center" src="https://github.com/hueeylow/power_automate/blob/main/13.png"/></br></br>
</p>

<h3>4. End-to-End Automation</h3>
<p>The completed Power Automate workflow therefore connects the entire expense claim approval process:</p>
<p>
  <b>SharePoint List</b></br>
Store expense claims information and approval status
</p>

<p>
  <b>Power Automate</b></br>
Control the approval logic, routing, status updates, and notifications
</p>


<p>
  <b>Microsoft Approvals</b></br>
Handles manager and Finance approval actions
</p>



<p>
  <b>Microsoft Teams</b></br>
Keep requestor informed of approval progress and final outcome. </br>
This automation reduces manual intervention, improves visibility of approval status, and provides a consistent approval process from expense claim submission through to final Finance approval.
</p>
</br>
<a href= "https://www.github.com/hueeylow"> << Back </a>
