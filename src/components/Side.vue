<template>
  <!-- Sidebar -->
  <div class="col-xl-4 col-md-12 widget-column mt-0">
    <!-- Countdown Timer -->
    <section class="section mb-5">
      <h4 class="mt-2 text-center"><strong><b>COUNTDOWN TO EVENT</b></strong></h4>
      <hr class="red title-hr" />
      <div class="table-responsive mt-4">
        <table class="table table-bordered custom-table">
          <thead class="thead-dark">
            <tr>
              <th class="text-center">Days</th>
              <th class="text-center">Hours</th>
              <th class="text-center">Minutes</th>
              <th class="text-center">Seconds</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td class="text-center" style="color: red; font-weight: bold;">{{ days }}</td>
              <td class="text-center" style="color: red; font-weight: bold;">{{ hours }}</td>
              <td class="text-center" style="color: red; font-weight: bold;">{{ minutes }}</td>
              <td class="text-center" style="color: red; font-weight: bold;">{{ seconds }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <hr class="my-3" />

    <!-- Announcements -->
    <section class="section mb-5">
      <h4 class="mt-2 text-center heading-font"><strong>ANNOUNCEMENT</strong></h4>
      <hr class="red title-hr" />
      <div class="table-responsive mt-4">
        <table class="table table-bordered custom-table">
          <thead class="thead-dark">
            <tr>
              <th class="text-center">Details</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td style="color: red;">
                <marquee
                  direction="up"
                  height="150px"
                  scrollamount="2"
                  scrolldelay="3"
                  onmouseover="this.stop();"
                  onmouseout="this.start();"
                >
                  All the accepted papers should be presented in physical mode only.
                  <br /><br />
                  Paper Submission starts : 30<sup>th</sup> June 2024<br /><br />
                  Deadline for Full Paper Submission :
                  <s>22<sup>nd</sup> October 2024</s> 30<sup>th</sup> October 2024 (hard deadline)
                  <br /><br />
                  Acceptance Notification :
                  <s>15<sup>th</sup> November 2024</s> 20<sup>th</sup> November 2024
                  <br /><br />
                  Camera Ready Paper Submission :
                  <s>30<sup>th</sup> November 2024</s> 5<sup>th</sup> December 2024
                  <br /><br />
                  Registration Deadline :
                  <s>15<sup>th</sup> December 2024</s> 20<sup>th</sup> December 2024
                  <br /><br />
                </marquee>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <hr class="my-3" />

    <!-- Important Dates Section -->
    <section class="section mb-5">
      <h4 class="mt-2 text-center heading-font"><strong>IMPORTANT DATES</strong></h4>
      <hr class="red title-hr" />
      <div class="table-responsive mt-4">
        <table class="table table-bordered custom-table">
          <thead class="thead-dark">
            <tr>
              <th class="text-center" colspan="2">Important Dates</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>Camera ready:</strong></td>
              <td>5<sup>th</sup> December 2024</td>
            </tr>
            <tr>
              <td><strong>Registration deadline:</strong></td>
              <s>15<sup>th</sup> December 2024</s> 20<sup>th</sup> December 2024 
            </tr>
            <tr>
              <td><strong>Paper submission starts:</strong></td>
              <td>30<sup>th</sup> June 2024</td>
            </tr>
            <tr>
              <td><strong>Deadline for Full Paper Submission Extended to:</strong></td>
              <td>
                <s>22<sup>nd</sup> October 2024</s> 30<sup>th</sup> October 2024 (hard deadline)
              </td>
            </tr>
            <tr>
              <td><strong>Acceptance Notifications:</strong></td>
              <td>
                <s>15<sup>th</sup> November 2024</s> 20<sup>th</sup> November 2024
              </td>
            </tr>
            <tr>
              <td><strong>Camera Ready Paper Submission:</strong></td>
              <td>
                <s>30<sup>th</sup> November 2024</s> 5<sup>th</sup> December 2024
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Side",
  data() {
    return {
      eventDate: new Date("2025-01-20T08:00:00"), 
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  },
  mounted() {
    this.startCountdown();
  },
  methods: {
    startCountdown() {
      setInterval(() => {
        const now = new Date();
        const timeDifference = this.eventDate - now;

        if (timeDifference > 0) {
          this.days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
          this.hours = Math.floor((timeDifference / (1000 * 60 * 60)) % 24);
          this.minutes = Math.floor((timeDifference / (1000 * 60)) % 60);
          this.seconds = Math.floor((timeDifference / 1000) % 60);
        }
      }, 1000);
    },
  },
};
</script>

<style scoped>
.countdown-timer {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-top: 10px;
}

.time-block {
  text-align: center;
  margin: 0 10px;
}

.time {
  font-size: 2rem;
  font-weight: bold;
  color: #d32f2f;
}

p {
  margin: 0;
  font-size: 1rem;
  font-weight: bold;
}

ul.list-group {
  padding-left: 0;
}

.list-group-item {
  font-size: 1rem;
  font-weight: normal;
  line-height: 1.5;
  background-color: #fff;
}

.list-group-item:hover {
  background-color: rgb(184, 221, 248);
}

img {
  width: 100%;
  height: 100%;
}

li:hover {
  background-color: rgb(184, 221, 248);
}

.custom-font {
  font-family: Ubuntu, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
}

.heading-font {
  font-family: Ubuntu, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  font-weight: bold;
}

/* Custom Table Styling */
.custom-table {
  background-color: #f8f9fa;
  font-family: "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  font-size: 16px;
}

.custom-table thead {
  background-color: #343a40;
  color: #ffffff;
}

.custom-table th {
  text-align: center;
  padding: 10px;
}

.custom-table td {
  padding: 10px;
  vertical-align: middle;
}

.custom-table td:first-child {
  font-weight: bold;
}

.custom-table tbody tr:nth-child(odd) {
  background-color: #f1f1f1;
}

.custom-table tbody tr:nth-child(even) {
  background-color: #ffffff;
}

.custom-table tbody tr:hover {
  background-color: #e9ecef;
}

</style>



