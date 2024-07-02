# MySQL-database

create database employee;
create table employee(emp_no int not null auto_increment, emp_fname varchar(255)  not null, emp_lname varchar(255)  not null, emp_address varchar(255)  not null, emp_rank varchar(255)  not null, primary key (emp_no));
insert into  employee (emp_name,emp_address,emp_rank) values ("SHiro","Kitale","H.R"),  ("Chris","Kakamega","manager Director"),  ("Peakay","Kapsabet","Technician");
select* from employee;

create table section (emp_no int, sec_code int auto_increment, sec_name varchar (255), sec_head_name varchar (255), sec_head_sign varchar(255), primary key (sec_code), foreign key (emp_no) references employee(emp_no)); 

insert into  section (emp_no,sec_name,sec_head_name,sec_head_sign) values (4,"ICT","SAM","S.R"),  (5,"HumanResource","MAx","L.S"),  (6,"Tech","Lin","L.W");

insert into  section (emp_no,sec_name,sec_head_name,sec_head_sign) values (7,"Bio","Tracy","T.R");


create table salary(emp_no int not null auto_increment, B_salary int not null, H_allowance int not null, Med_allowance int not null, Travel_all int, PAYE int, NSSF int, NHIF int, Loan int, Net_salary int not null,  foreign key (emp_no) references employee(emp_no));

insert into  salary (emp_no,B_salary, H_allowance,Med_allowance, Travel_all, PAYE, NSSF, NHIF, Loan, Net_salary) values (1,50000,15000, 8000, 5000, 5000,  500, 700, 7000, 80000),
        (2,60000,15000, 8000, 5000, 5000, 500,  700, 7000, 90000),
         (3,70000,15000, 8000, 5000, 5000, 500,  700, 7000, 100000),
          (4,40000,15000, 8000, 5000, 5000, 500, 700, 7000, 70000),
           (5,20000,15000, 8000, 5000, 5000, 500,  700, 7000, 40000),
            (6,44000,15000, 8000, 5000, 5000, 500,  700, 7000, 64000);


select * from employee where emp_name like 'm%';
select * from salary where Net_salary > 80000;
select * from employee where emp_name like '_a%';
select * from salary where Net_salary > 20000 < 60000;

ALTER TABLE salary ADD COLUMN Total Decimal (10,2);
update salary
SET Total = B_salary + H_allowance + Med_allowance + Travel_all;




select * from section;
select * from salary;
commit;
rollback;
