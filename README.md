# Healthcare Analytics

This repository will contain portfolio projects relating to healthcare anlytics.

My goal is to pursue a career in healthcare analytics in hopes of enhancing healthcare by streamlining operations, facilitating research, and improving stakeholder knowledge and patient care.

<h2>Projects</h2>
<h3>1. Healthcare Mangement System</h3>
<h4>Objective</h4>
Design a relational database for a Healthcare Mangement System that allows healthcare companies to efficiently store and manage data related to patients, appointments, billing, inventory, and doctors.

<h4>Deliverables</h4>
<ol>
	<li>Entities and Attributes</li>
	<li>Entity Relationship Diagram</li>
	<li>Database Model</li>
	<li>Database Schema using SQL Server</li>
</ol>
<h4><b>1. Entities and Attributes</b></h4>		
<b>Patient entity stores personal details regarding the patient</b>
		<ul>
			<li>patient_id: Unique identifier for patients (Primary Key) </li>
			<li>first_name: First name of the patient</li>
			<li>last_name: Last name of patient</li>
			<li>dob: Date of birth of patient</li>
			<li>gender: Gender of patient</li>
			<li>address: Address of patient</li>
			<li>phone: Phone number of patient</li>
			<li>insurance_info: Insurance innformation of patient</li>
		</ul>
<b>Appointment entity stores information on appointments scheduled for patients</b>
		<ul>
			<li>appointment_id: Unique identiffier for appointsments (Primary Key) </li>
			<li>patient_id: Identifier of the patient for the appointment (Foreign Key referencing Patient table)  </li>
			<li>doctor_id: Identifier of  the doctor for the appointment (Foreign Key referencing Patient table) </li>
			<li>appointment_date: Date and time of the appointment </li>
			<li>status: status of the appointment</li>
		</ul>
  
<h5><b>2. Entity Relationship Diagram</b></h5>
		
<h5><b>3. Database Model</b></h5>
		
<h5><b>4. Database Schema using SQL Server</b></h5>
	<pre>
	-- Create Patient table
	CREATE TABLE Patient (
		patient_id int PRIMARY KEY,
		first_name VARCHAR(255) NOT NULL,
		last_name VARCHAR(255) NOT NULL,
		dob DATE NOT NULL,
		gender VARCHAR(10) NOT NULL,
		address TEXT,
		phone VARCHAR(20),
		insurance_info TEXT
	);
	-- Create Appointment table
	CREATE TABLE Appointment (
		appointment_id INT PRIMARY KEY,
		patient_id INT NOT NULL,
		doctor_id INT NOT NULL,
		appointment_date DATETIME NOT NULL,
		status VARCHAR(50) NOT NULL,
		FOREIGN KEY (patient_id) REFERENCES Patient(patient_id),
	    	FOREIGN KEY (doctor_id) REFERENCES Doctor(doctor_id)
	);
	--CREATE Billing table
	CREATE TABLE Billing (
		billing_id INT PRIMARY KEY,
		patient_id INT NOT NULL,
		amount DECIMAL(10, 2) NOT NULL,
		billing_date DATE NOT NULL,
		payment_status VARCHAR(50) NOT NULL
		FOREIGN KEY (patient_id) REFERENCES Patient(patient_id)
	);
	--CREATE Inventory table
	CREATE TABLE Inventory (
		inventory_id INT NOT NULL,
		item_name VARCHAR(255) NOT NULL,
		quantity INT NOT NULL,
		expiration_date DATE
	);
	-- Create Doctor table
	CREATE TABLE Doctor (
		doctor_id INT PRIMARY KEY,
		first_name VARCHAR(255) NOT NULL,
		last_name VARCHAR(255) NOT NULL,
		specialization VARCHAR(255) NOT NULL,
		schedule TEXT
	);
	</pre>
</ol>

<h4>Database Schema using SQL Server</h4>
<br></br>

<h4>Improving Database Design</h4>
<ol>
<li>Use indexing to improve query performance, especially on frequently accessed columns like patient_id.</li>
<li>Normalize the database schema to reduce data redundancy and improve data integrity.</li>
<li>Implement data encryption and access controls to ensure data security and compliance with healthcare regulations.</li>
<li>Regularly backup the database to prevent data loss and ensure data availability in case of system failures.</li>
<li>Use stored procedures and triggers to enforce business rules and ensure data consistency.</li>
</ol>
