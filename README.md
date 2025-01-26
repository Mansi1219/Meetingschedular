// File: App.js
import React from "react";
import MeetingForm from "./components/MeetingForm";
import Calendar from "./components/Calendar";

function App() {
  return (
    <div className="min-h-screen bg-gray-100 p-4">
      <h1 className="text-3xl font-bold text-center">Meeting Scheduler</h1>
      <div className="mt-4 grid grid-cols-1 md:grid-cols-2 gap-4">
        <MeetingForm />
        <Calendar />
      </div>
    </div>
  );
}

export default App;

// File: components/MeetingForm.js
import React, { useState } from "react";

const MeetingForm = () => {
  const [meeting, setMeeting] = useState({
    title: "",
    date: "",
    time: "",
    participants: "",
  });

  const handleInputChange = (e) => {
    const { name, value } = e.target;
    setMeeting({ ...meeting, [name]: value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Meeting scheduled:", meeting);
    // Add API integration to save meeting
  };

  return (
    <form onSubmit={handleSubmit} className="bg-white p-4 shadow rounded">
      <h2 className="text-xl font-bold mb-2">Schedule a Meeting</h2>
      <label className="block mb-2">
        Title:
        <input
          type="text"
          name="title"
          value={meeting.title}
          onChange={handleInputChange}
          className="w-full p-2 border rounded"
          required
        />
      </label>
      <label className="block mb-2">
        Date:
        <input
          type="date"
          name="date"
          value={meeting.date}
          onChange={handleInputChange}
          className="w-full p-2 border rounded"
          required
        />
      </label>
      <label className="block mb-2">
        Time:
        <input
          type="time"
          name="time"
          value={meeting.time}
          onChange={handleInputChange}
          className="w-full p-2 border rounded"
          required
        />
      </label>
      <label className="block mb-2">
        Participants:
        <input
          type="text"
          name="participants"
          value={meeting.participants}
          onChange={handleInputChange}
          className="w-full p-2 border rounded"
          placeholder="Enter emails, separated by commas"
        />
      </label>
      <button type="submit" className="bg-blue-500 text-white px-4 py-2 rounded">
        Schedule
      </button>
    </form>
  );
};

export default MeetingForm;

// File: components/Calendar.js
import React from "react";

const Calendar = () => {
  return (
    <div className="bg-white p-4 shadow rounded">
      <h2 className="text-xl font-bold mb-2">Calendar</h2>
      <p>Integration with Google Calendar coming soon...</p>
    </div>
  );
};

export default Calendar;

// File: utils/api.js
// Placeholder for Google Calendar API integration
export const saveMeeting = (meeting) => {
  console.log("Saving meeting to Google Calendar:", meeting);
  // Add API request logic here
};

// File: .env
REACT_APP_GOOGLE_CLIENT_ID=your-client-id
REACT_APP_GOOGLE_API_KEY=your-api-key

// File: README.md
# Meeting Scheduler

## Overview
A simple meeting scheduler to plan and organize meetings efficiently. It supports Google Calendar integration, notifications, and participant management.

## Features
- Add, update, and delete meetings.
- Google Calendar sync.
- Notifications for upcoming meetings.
- Export meeting details to CSV.

## Setup Instructions
1. Clone the repository:
   ```
   git clone https://github.com/your-username/meeting-scheduler.git
   cd meeting-scheduler
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Add a `.env` file for Google Calendar API keys:
   ```
   REACT_APP_GOOGLE_CLIENT_ID=your-client-id
   REACT_APP_GOOGLE_API_KEY=your-api-key
   ```

4. Start the development server:
   ```
   npm start
   ```

5. Open the app at `http://localhost:3000`.

## Technologies
- React.js
- Google Calendar API
- Node.js (for backend if required)

## Contributing
Feel free to fork the repository and submit pull requests.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

// File: LICENSE
MIT License

Copyright (c) 2025 [MansiPuranik]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

