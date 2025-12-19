# transfer box

```
# app.js-
import React, { useEffect, useState } from 'react';

// Mock API 1
function fetchStudentsFromAPI1() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve([
        { name: 'ABC', marks: '98%', registrationId: '1234' },
        { name: 'DEF', marks: '87%', registrationId: '5678' },
        { name: 'GHI', marks: '91%', registrationId: '9101' },
      ]);
    }, 1000);
  });
}

// Mock API 2
function fetchStudentsFromAPI2() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve([
        { name: 'ABC', marks: '98%', registrationId: '1234' },
        { name: 'JKL', marks: '85%', registrationId: '1122' },
        { name: 'MNO', marks: '92%', registrationId: '1314' },
      ]);
    }, 1000);
  });
}

function mergeAndRemoveDuplicates(arr1, arr2) {
  const combined = [...arr1, ...arr2];
  const unique = combined.reduce((acc, current) => {
    const x = acc.find(
      (item) => item.registrationId === current.registrationId
    );
    if (!x) {
      return acc.concat([current]);
    } else {
      return acc;
    }
  }, []);
  return unique;
}

const App = () => {
  const [selectedStudents, setSelectedStudents] = useState([]);
  const [box1Students, setBox1Students] = useState([]);
  const [box2Students, setBox2Students] = useState([]);

  useEffect(() => {
    Promise.all([fetchStudentsFromAPI1(), fetchStudentsFromAPI2()]).then(
      ([api1Data, api2Data]) => {
        const mergedData = mergeAndRemoveDuplicates(api1Data, api2Data);
        setBox1Students(mergedData);
      }
    );
  }, []);

  const handleSelectStudent = (registrationId) => {
    setSelectedStudents((prev) =>
      prev.includes(registrationId)
        ? prev.filter((id) => id !== registrationId)
        : [...prev, registrationId]
    );
  };

  const moveSelectedToBox2 = () => {
    const toMove = box1Students.filter((student) =>
      selectedStudents.includes(student.registrationId)
    );
    setBox2Students((prev) => [...prev, ...toMove]);
    setBox1Students((prev) =>
      prev.filter(
        (student) => !selectedStudents.includes(student.registrationId)
      )
    );
    setSelectedStudents([]);
  };

  const moveSelectedToBox1 = () => {
    const toMove = box2Students.filter((student) =>
      selectedStudents.includes(student.registrationId)
    );
    setBox1Students((prev) => [...prev, ...toMove]);
    setBox2Students((prev) =>
      prev.filter(
        (student) => !selectedStudents.includes(student.registrationId)
      )
    );
    setSelectedStudents([]);
  };

  return (
    <div className="student">
      <div className="box box1">
        <h3>Box 1</h3>
        <div className="student-list">
          {box1Students.map((student) => (
            <label key={student.registrationId} className="student-item">
              <input
                type="checkbox"
                checked={selectedStudents.includes(student.registrationId)}
                onChange={() => handleSelectStudent(student.registrationId)}
              />
              <span>
                {student.name} - {student.marks}
              </span>
            </label>
          ))}
        </div>
      </div>

      <div className="button-container">
        <button className='btn' onClick={moveSelectedToBox2}>&rarr; Move to Box 2</button>
        <button className='btn' onClick={moveSelectedToBox1}>&larr; Move to Box 1</button>
      </div>

      <div className="box box2">
        <h3>Box 2</h3>
        <div className="student-list">
          {box2Students.map((student) => (
            <label key={student.registrationId} className="student-item">
              <input
                type="checkbox"
                checked={selectedStudents.includes(student.registrationId)}
                onChange={() => handleSelectStudent(student.registrationId)}
              />
              <span>
                {student.name} - {student.marks}
              </span>
            </label>
          ))}
        </div>
      </div>
    </div>
  );
};
export default App;

# index.css-
.student{
    display: flex;
    padding: 10px;
    gap: 10px;
    .box1 ,.box2 {
        width: 100px;
        padding: 20px;
    }
    .btn{
        background: aliceblue;
        padding: 10px;
        display: block;
        margin-bottom: 5px;
    }
}
```
