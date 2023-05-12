<script>
    import googleCalendarPlugin from '@fullcalendar/google-calendar';
    import dayGridPlugin from '@fullcalendar/daygrid'
    import FullCalendar from '../components/Calendar.svelte';
	import { PUBLIC_GOOGLE_CALENDAR_API_KEY, PUBLIC_GOOGLE_CALENDAR_ID } from '$env/static/public';
  
    let options = {
        initialView: 'dayGridMonth',
        plugins: [dayGridPlugin, googleCalendarPlugin],
        googleCalendarApiKey: PUBLIC_GOOGLE_CALENDAR_API_KEY,
        events: {
            googleCalendarId: PUBLIC_GOOGLE_CALENDAR_ID
        }
    };
  </script>
  
  <FullCalendar {options} />

  <style>
    :global(html) {
        font-family: Arial, Helvetica, sans-serif;
    }
  </style>