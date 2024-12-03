<template>
  <div class="container">
    <!-- First outlined box -->
    <div class="outlined-box">
      <!-- Profile icon in the top-left corner using Font Awesome -->
      <div class="profile-container">
        <i class="fas fa-user-circle profile-icon"></i>
      </div>

      <!-- Header inside the outlined box -->
      <h2 class="box-header">IIS Student / Guardian</h2>

      <!-- Some descriptive text inside -->
      <p class="box-text">IIS (Integrated Information System) is a web-based portal allowing Student access to internal systems and workflows.</p>

      <!-- Buttons inside the outlined box -->
      <div class="button-container">
        <!-- Loop through the buttons1 array to render each button -->
        <button 
          v-for="(button, index) in buttons1" 
          :key="index" 
          @click="handleButtonClick(button)" 
          :class="{'blue-button': index === 0 || index === 2}">
          {{ button.text }}
        </button>
      </div>
    </div>

    <!-- Second outlined box -->
    <div class="outlined-box">
      <!-- Profile icon in the top-left corner using Font Awesome -->
      <div class="profile-container">
        <i class="fas fa-user-circle profile-icon"></i>
      </div>

      <!-- Header inside the outlined box -->
      <h2 class="box-header">ISS Staff</h2>

      <!-- Some descriptive text inside -->
      <p class="box-text">IIS (Integrated Information System) is a web-based portal allowing Staff access to internal systems and workflows.</p>

      <!-- Buttons inside the outlined box -->
      <div class="button-container">
        <!-- Loop through the buttons2 array to render each button -->
        <button 
          v-for="(button, index) in buttons2" 
          :key="index" 
          @click="handleButtonClick(button)" 
          :class="{'blue-button': index === 0 || index === 2}">
          {{ button.text }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LandingComponent',
  props: {
    headerText: {
      type: String,
      default: 'Student / Guardian', // Default header text
      staff: 'Student / Guardian',
    },
    bodyText: {
      type: String,
      default: 'IIS (Integrated Information System) is a web-based portal allowing Student access to internal systems and workflows.', // Default body text
    },
    buttons1: {
      type: Array,
      default: () => [
        { text: 'IISV2 STUDENT PORTAL', url: 'https://iisv2.ucsiuniversity.edu.my/apex/iisv2/r/iis2-student-portal-login/login?session=16008151371632' },
        { text: 'IISV2 STUDENT BANGLADESH', url: 'https://iisv2bd.ucsiuniversity.edu.my/bgd/iisv2bgd/r/iis2-student-portal-login/login?session=332799292372' },
        { text: 'IISV2 PARENT PORTAL', url: 'https://iisv2.ucsiuniversity.edu.my/apex/iisv2/r/parent/' },
        { text: 'IISV2 PARENT BANGLADESH', url: 'https://iisv2bd.ucsiuniversity.edu.my/bgd/iisv2bgd/r/parent' }
      ], // Define button text and URLs here
    },
    buttons2: {
      type: Array,
      default: () => [
        { text: 'IIS', url: 'https://iis.ucsiuniversity.edu.my/Staff' },
        { text: 'IIS VERSION 2', url: 'https://iisv2.ucsiuniversity.edu.my/apex/f?p=510' },
        { text: 'IIS BANGLADESH', url: 'https://iisv2bd.ucsiuniversity.edu.my/bgd/f?p=510:43:15069985456062:::::&tz=8:00' },
      ], // Define button text and URLs here
    },
  },
  methods: {
    handleButtonClick(button) {
      // Redirect to the URL of the button when clicked
      window.location.href = button.url; // Redirect to the specified URL
    }
  }
};
</script>

<style scoped>
/* Container that holds the boxes */
.container {
  display: flex;
  flex-direction: column;  /* Stack the boxes vertically */
  justify-content: flex-start; /* Align the content to the top */
  align-items: center;  /* Center horizontally */
}

/* Styling for the outlined box */
.outlined-box {
  padding: 20px;
  width: 300px;
  text-align: center;
  border-radius: 8px; /* Optional: round corners for the rectangle */
  margin-top: 1px; /* Adds some spacing between the boxes */
  margin-bottom: 40px;
  position: relative; /* To allow positioning the profile icon */

  /* Grey-transparent background (50% opacity) */
  background-color: rgb(240, 240, 240); /* rgba with 50% opacity */
  
  /* Remove border */
  border: none;
}

/* Profile icon container */
.profile-container {
  display: flex;               /* Make this a flex container */
  justify-content: center;     /* Center content horizontally */
  align-items: center;         /* Center content vertically */
  width: 100%;                 /* Take up full width of the container */
  height: 80px;                /* Give it enough height to center the icon */
  position: relative;
  margin-bottom: -20px;        /* Space between the profile icon and the header */
  margin-top: 20px;
}

/* Profile icon styling */
.profile-icon {
  font-size: 100px;             /* Size of the profile icon */
  color: #555;                 /* Optional: Set the icon color */
}

/* Header inside the box */
.box-header {
  margin: 0;
  font-size: 1.5rem;
  font-weight: bold;
  padding-top: 50px; /* Adds padding to ensure the header doesn't overlap with the icon */
}

/* Body text inside the box */
.box-text {
  font-size: 1rem;
  color: #555;
  margin: 10px 0;
}

/* Container for buttons */
.button-container {
  display: flex;
  flex-direction: column; /* Arrange buttons in a column */
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
}

/* Button styling */
button {
  padding: 10px 20px;
  background-color: #e50e0e;
  color: white;
  border: none;
  font-size: small;
  font-weight: bold;
  cursor: pointer;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

/* Blue button styling for first and third buttons */
.blue-button {
  background-color: #007bf7; /* Blue color for the button */
}

/* Button hover effect */
button:hover {
  background-color: #3c4147;
}
</style>
