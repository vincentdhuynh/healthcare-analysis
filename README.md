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
<li>Entity Relationship (ER) Diagram</li>
<li>Database Model</li>

  <li>Database Schema using SQL Server</li>
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
<h3>2. Healthcare Business Intelligence Dashboard</h3>

