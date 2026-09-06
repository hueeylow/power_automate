<h2>Chope My Desk with Power App</h2>
<h3>1. Introduction</h3>
<p>Hotdesking is increasingly common in modern workplaces as it provides flexibility and better utilisation of office space, however it can caused inconvenience when there is <b></b>no centralised desk booking system. </b></p>

<p>Employees may not know which desks are available and without a proper booking process, this can lead to desk conflicts and unnecessary manual coordination.</p>
<p>To simplify the hotdesking experience, in this project, I built a <b>Chope My Desk Portal</b> using <b>Microsoft Power App</b> to provide a centralised platform where employees can check desk availability, book a desk and manage their bookings.</p>
<p>In this post, I will walk through the process design and demonstration of the application.</p>

<h3>2. Process Design Flowchart</h3>
<p>Before building the application, the booking process was mapped out to illustrate the user journey involved in reserving a desk.</p>
The application has two user paths:</br>

<h4><b>2.1 Normal User</b></h4>
Employees can access the portal to manage their own desk reservations - </br>
</br>
<b>i. Create a Desk Booking</b></br>
Users can select a preferred date and reserve any desk that is available for that day.<br><br>
<b>ii. View Booking Summary</b></br>
Users can view their current reservation details, including the <b>booking date and reserved desk.</b><br><br>
<b>iii. Delete Own Booking</b></br>
Users can remove their own reservation when the desk is no longer required.</b><br><br>
<b>iv. View Desk Availability</b></br>
The main page displays real-time desk availability based on the selected date.</b><br><br>
<b>v. Prevent Multiple Bookings</b></br>
Users cannot create more than one reservation for the same day.</b><br><br>
<b>vi. Prevent Double Booking</b></br>
A desk that has already been reserved for a selected date cannot be booked by another user.</b><br><br>

<h4><b>2.2 Administrator</b></h4>
Administrator have additional access and functionality to manage reservations across all users - <br><br>
<b>i. View All Booking Reservations</b></br>
Administrator can view booking summaries and reservation details for all employees.
This provides a centralised overview of desk usage.<br><br>
<b>ii. Delete Any Employee's Booking</b></br>
Administrator can delete reservation belonging to any employee when required.<br><br>
<b>iii. View Desk Availability</b></br>
Administrator can also check desk availability based on the selected date.<br><br>
<b>iv. Create Booking on Behalf of a Employee</b></br>
Administrator can create a desk reservation for another employee by input his name and select an available desk.
This is useful when an administrator needs to manage a reservation on behalf of an employee.
<br><br>

<h3><b>Be right back. Editing in progress .. </b></h3>
