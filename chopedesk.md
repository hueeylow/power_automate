<h2>Chope My Desk with Power App</h2>
<h3>1. Introduction</h3>
<p>Hotdesking is increasingly common in modern workplaces as it provides flexibility and better utilisation of office space, however it can caused inconvenience when there is <b></b>no centralised desk booking system. </b></p>

<p>Employees may not know which desks are available and without a proper booking process, this can lead to desk conflicts and unnecessary manual coordination.</p>
<p>To simplify the hotdesking experience, in this project, I built a <b>Chope My Desk Portal</b> using <b>Microsoft Power App</b> to provide a centralised platform where employees can check desk availability, book a desk and manage their bookings.</p>
<p>In this post, I will walk through the process design and demonstration of the application.</p>

<h3>2. Process Design Flowchart</h3>
<p>Before building the application, the reservation process is mapped out to illustrate the user journey involved in reserving a desk.</p>
The application has two user paths:</br>
</br>
<b>[To insert process chart]</b></br>

<h4><b>2.1 Normal User</b></h4>
Employees can access the portal to manage their own desk reservation: </br>
</br>
<b>i. Create a Desk Booking</b></br>
Users can select a preferred date and reserve any desk that is available for that day.<br><br>
<b>ii. View Booking Summary</b></br>
Users can view their current reservation details, including the booking date and reserved desk.<br><br>
<b>iii. Delete Own Booking</b></br>
Users can remove their own reservation when the desk is no longer required.</b><br><br>
<b>iv. View Desk Availability</b></br>
The main page displays real-time desk availability based on the selected date.</b><br><br>
<b>v. Prevent Multiple Bookings</b></br>
Users cannot create more than one reservation for the same day.</b><br><br>
<b>vi. Prevent Double Booking</b></br>
A desk that has already been reserved for a selected date cannot be booked by another user.</b><br>

<h4><b>2.2 Administrator</b></h4>
Administrator have additional access and functionality to manage reservations across all users: <br><br>
<b>[To insert process chart]</b></br></br>
<b>i. View All Booking Reservations</b></br>
Administrator can view booking summaries and reservation details for all users.
This provides a centralised overview of desk usage.<br><br>
<b>ii. Delete Any User's Booking</b></br>
Administrator can delete reservation belonging to any user when required.<br><br>
<b>iii. View Desk Availability</b></br>

Administrator can also check desk availability based on the selected date.<br><br>
<b>iv. Create Booking on Behalf of User</b></br>
Administrator can create a desk reservation for another user by input his name and select an available desk.
This is useful when an administrator needs to manage a reservation on behalf of user.
</br></br>
<h3>3. Power App Application Demo</h3>
<h4>Overview</h4>
<p><b>Chope My Desk App </b> enables employees to view desk availability, reserve desk, and manage their reservation. To ensure fair usage and booking integrity, the application prevents multiple bookings by the same employee and eliminates double-booking conflicts. </p>

<h4>3.1 View Desk Availability and Book a Desk</h4>
<p>Employee can view current desk availability based on selected date and reserve an available workspace for their preferred date.</p>

<b>Demo Flow</b></br>
i. Select a booking date. </br>
ii. Desk availability is displayed on the right pane of the screen. </br>
iii. Select an available desk. </br>
iv. Submit the booking request. </br>

Outcome: Notification on booking request is successfully created. </br></br>
<b>a. Desk Availability </b></br>
[To insert Desk Availability screenshot]</br>

<b>b. Successful Desk Booking</b></br>
[To insert Successful Desk Booking screenshot]</br></br>

<h4>3.2 Prevent Multiple Bookings by the Same User</h4>
To ensure fair usage, each user is allowed only one desk reservation per day.</br></br>

<b>Validation Flow</b></br>
i. User has already reserved a desk for a selected date.</br>
ii. User attempts to reserve another desk on the same date.</br>
iii. The system checks for existing reservation.</br>
iv. The booking request is blocked.</br></br>
Outcome: Validation successfully prevents duplicate reservation. </br>

<b>a. Existing Reservation Found </b></br>
[To insert user existing reservation screenshot]</br>

<b>b. Duplicate Booking Validation Message </b></br>
[To insert you already have a booking for this date screenshot]</br>

<h4>3.3 Prevent Double Booking of the Same Desk</h4>
The application ensures that a desk can only be reserved once for a given date. </br></br>

<b>Validation Flow</b></br>
i. User A reserves a desk.</br>
ii. User B attempts to reserve the same desk for the same date.</br>
iii. The system checks for desk availability.</br>
iv. The booking request is rejected.</br></br>
Outcome: Double booking is successfully prevented. </br>

<b>a. Desk Already Reserved </b></br>
[To insert desk is already reserved screenshot]</br>

<b>a. Double Booking Error Message </b></br>
[To insert desk is already booked error screenshot]</br>

Example Message </br>
This desk has already been reserved for the selected date. Please choose another desk. </br></br>

<h4>3.4 Delete Existing Reservation</h4>
Users can manage their own reservations and delete bookings when required.</br></br>

<b>Demo Flow</b></br>
i. Navigates to <b>My Reservations</b> </br>
ii. Select the booking. </br>
iii. Click on <b>Delete this booking.</b> </br>
iv. Booking is deleted successfully. </br></br>
Outcome: Users can maintain their own reservations without administrator intervention.</br>

<b>a. My Reservations Page</b></br>
[To insert my reservation screenshot]</br>

<b>b. Reservation Deleted Successfully</b></br>
[To insert successful deletion notification]</br>

<h4>Key Features and Controls</h4>

<table style="border-collapse: collapse; width: 100%;">
<tr>
<th style="border:1px solid #666; padding:10px;">Feature</th>
<th style="border:1px solid #666; padding:10px;">Description</th>
</tr>
<tr>
<td style="border:1px solid #666; padding:10px;">Desk Availability</td>
<td style="border:1px solid #666; padding:10px;">Users can view desk availability on landing page</td>
</tr>
<tr>
<td style="border:1px solid #666; padding:10px;">Single Booking Per Day</td>
<td style="border:1px solid #666; padding:10px;">Users cannot reserve more than one desk on the same day</td>
</tr>
<tr>
<td style="border:1px solid #666; padding:10px;">Double-Booking Prevention</td>
<td style="border:1px solid #666; padding:10px;">A desk can only have one reservation per date</td>
</tr>
<tr>
<td style="border:1px solid #666; padding:10px;">Reservation Management</td>
<td style="border:1px solid #666; padding:10px;">Users can delete their own reservations</td>
</tr>
<tr>
<td style="border:1px solid #666; padding:10px;">User-Friendly Experience</td>
<td style="border:1px solid #666; padding:10px;">Simple workflow with clear validation messages</td>
</tr>
</table>

<h3>4. Summary</h3>
<p>The <b>Chope My Desk App</b> provides a streamlined desk reservation experience while enforcing key control mechanisms to ensure booking accuracy. Through automated validation checks, the application prevents both multiple bookings by the same user and double-booking of desks, creating a reliable and efficient workspace booking solution.</p>

<h3><b>Be right back. Editing in progress .. </b></h3>
