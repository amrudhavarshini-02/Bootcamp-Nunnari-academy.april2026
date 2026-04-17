# Bootcamp-Nunnari-academy.april2026
Nunnari Academy
import React from 'react';

const StudentCard = ({ name, course, status }) => {
  return (
    <div style={{
      border: '1px solid #ccc',
      borderRadius: '8px',
      padding: '16px',
      margin: '8px',
      width: '300px',
      boxShadow: '0 2px 4px rgba(0,0,0,0.1)'
    }}>
      <h3>{name}</h3>
      <p><strong>Course:</strong> {course}</p>
      <p><strong>Status:</strong> 
        <span style={{
          color: status === 'Active' ? 'green' : 'red',
          fontWeight: 'bold'
        }}>
          {status}
        </span>
      </p>
    </div>
  );
};

export default StudentCard;
[4/15, 6:42 PM] Varshini🦋: import React, { useState } from "react";

function StudentCard(props) {
  return (
    <div>
      <h3>Student Details</h3>
      <p>Name: {props.name}</p>
      <p>Course: {props.course}</p>
      <p>Status: {props.status}</p>
    </div>
  );
}

function App() {

  // State for input
  const [text, setText] = useState("");

  // State for form
  const [name, setName] = useState("");
  const [course, setCourse] = useState("");

  // Button event
  const handleClick = () => {
    console.log(text);
  };

  // Form submit
  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Name:", name);
    console.log("Course:", course);
  };

  return (
    <div>

      {/* Exercise 1 & 2 - Component with Props */}
      <StudentCard 
        name="Amrudha"
        course="B.Sc Computer Science"
        status="Active"
      />

      <hr/>

      {/* Exercise 3 - useState */}
      <h3>Input Example</h3>
      <input
        type="text"
        placeholder="Enter text"
        onChange={(e) => setText(e.target.value)}
      />

      <hr/>

      {/* Exercise 4 - Event Handling */}
      <button onClick={handleClick}>Click Me</button>

      <hr/>

      {/* Exercise 5 - Form UI */}
      <h3>Student Form</h3>
      <form onSubmit={handleSubmit}>

        <input
          type="text"
          placeholder="Enter Name"
          onChange={(e) => setName(e.target.value)}
        />

        <br/><br/>

        <input
          type="text"
          placeholder="Enter Course"
          onChange={(e) => setCourse(e.target.value)}
        />

        <br/><br/>

        <button type="submit">Submit</button>

      </form>

    </div>
  );
}

export default App;
