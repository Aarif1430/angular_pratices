import React, { useState } from 'react';
import Calendar from 'react-calendar';
import 'react-calendar/dist/Calendar.css';

const MyComponent = () => {
  const [showCalendar, setShowCalendar] = useState(false);
  const [selectedDate, setSelectedDate] = useState(new Date());

  const handleDateChange = (date) => {
    setSelectedDate(date);
    setShowCalendar(false);
  };

  return (
    <div style={{ display: 'flex', alignItems: 'center' }}>
      <h1>My Component</h1>
      <button
        style={{
          marginLeft: '20px',
          padding: '10px 20px',
          fontSize: '16px',
          borderRadius: '5px',
          backgroundColor: '#0077c2',
          color: '#fff',
          border: 'none',
        }}
        onClick={() => setShowCalendar(true)}
      >
        Select a Date
      </button>
      {showCalendar && (
        <div
          style={{
            position: 'absolute',
            marginTop: '5px',
            zIndex: '100',
          }}
        >
          <Calendar
            style={{
              border: '1px solid #ccc',
              borderRadius: '5px',
              boxShadow: '0 2px 4px rgba(0, 0, 0, 0.2)',
              backgroundColor: '#fff',
              fontSize: '16px',
              lineHeight: '1.5',
              width: '280px',
            }}
            calendarType="US"
            minDetail="month"
            value={selectedDate}
            onChange={handleDateChange}
          />
        </div>
      )}
      <p style={{ marginLeft: '20px' }}>You selected: {selectedDate.toLocaleDateString()}</p>
    </div>
  );
};

export default MyComponent;

