import React, { useState } from 'react';
import Calendar from 'react-calendar';

const MyComponent = () => {
  const [showCalendar, setShowCalendar] = useState(false);
  const [selectedDate, setSelectedDate] = useState(new Date());

  const handleDateChange = (date) => {
    setSelectedDate(date);
    setShowCalendar(false);
  };

  return (
    <div>
      <h1>My Component</h1>
      <button onClick={() => setShowCalendar(true)}>Select a Date</button>
      {showCalendar && (
        <Calendar
          value={selectedDate}
          onChange={handleDateChange}
        />
      )}
      <p>You selected: {selectedDate.toLocaleDateString()}</p>
    </div>
  );
};

export default MyComponent;
