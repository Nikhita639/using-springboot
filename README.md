#student.java
package com.example.demo.model;
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.Id;
@Entity
public class Student {
 @Id
 @GeneratedValue
 private int StudentID;
 private String Name;
 private String DateOfBirth;
 private String Gender;
 private String Email;
 private long Phone;
 private String Address;
 private String DateOfJoining;
 private String Status;
 public int getStudentID() {
 return StudentID;
 }
 public void setStudentID(int studentID) {
 StudentID = studentID;
 }
 public String getName() {
 return Name;
 }
 public void setName(String name) {
 Name = name;
 }
 public String getDateOfBirth() {
 return DateOfBirth;
 }
 public void setDateOfBirth(String dateOfBirth) {
 DateOfBirth = dateOfBirth;
 }
 public String getGender() {
 return Gender;
 }
 public void setGender(String gender) {
 Gender = gender;
 }
 public String getEmail() {
 return Email;
 }
 public void setEmail(String email) {
 Email = email;
 }
 public long getPhone() {
 return Phone;
 }
 public void setPhone(long phone) {
 Phone = phone;
 }
 public String getAddress() {
 return Address;
 }
 public void setAddress(String address) {
 Address = address;
 }
 public String getDateOfJoining() {
 return DateOfJoining;
 }
 public void setDateOfJoining(String dateOfJoining) {
 DateOfJoining = dateOfJoining;
 }
 public String getStatus() {
 return Status;
 }
 public void setStatus(String status) {
 Status = status;
 }
}

#studentcontroller.java
package com.example.demo.controller;

import com.example.demo.model.Student;

import com.example.demo.repository.StudentRepository;

import org.springframework.beans.factory.annotation.Autowired;

import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController 
@CrossOrigin("http://localhost:3000")
public class StudentController {
 @Autowired

 private StudentRepository StudentRepository;
 @PostMapping()

 Student newStudent(@RequestBody Student newStudent) {

  return StudentRepository.save(newStudent);
 }
 @GetMapping("/student")

 List<Student> getAllStudents() {

  return StudentRepository.findAll();

 }
#studentrepository
package com.example.demo.repository;

import com.example.demo.model.Student;
import org.springframework.data.jpa.repository.JpaRepository;

public interface StudentRepository extends JpaRepository<Student,Integer> {

 /*Optional<Student> findById(Long studentID);*/

}

#studentapplication
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SbStudent1Application {

	public static void main(String[] args) {
		SpringApplication.run(SbStudent1Application.class, args);
	}

}
#studentapplicationtest
package com.example.demo;

import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;

@SpringBootTest
class SbStudent1ApplicationTests {

	@Test
	void contextLoads() {
	}

}

