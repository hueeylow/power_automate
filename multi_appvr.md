<h2>Expense Claim Multi-Approval using Power Automate & SharePoint</h2>
<h3>1. Introduction</h3>
<p>Expense claims are a common business process that often require multiple levels of approval. Most organisation have existing expense claim system in place, but the solution came with relatively high licensing and maintenance costs.</p>

<p>This project explores how <b>Microsoft Power Automate and SharePoint List</b>can be used to provide a simpler and more cost-effective approach to managing the expense claim process.</p>

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
