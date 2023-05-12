<script>
    import { onMount } from 'svelte'
    import googleCalendarPlugin from '@fullcalendar/google-calendar';
    import dayGridPlugin from '@fullcalendar/daygrid'
    import listPlugin from '@fullcalendar/list'
    import FullCalendar from '../components/Calendar.svelte';
	import { PUBLIC_GOOGLE_CALENDAR_API_KEY, PUBLIC_GOOGLE_CALENDAR_ID } from '$env/static/public';

    let currentView;
    let innerWidth;
    let options;
    onMount(() => {
        currentView = innerWidth > 812 ? 'dayGridMonth' : 'listWeek'

        options = {
        initialView: currentView,
        plugins: [listPlugin, dayGridPlugin, googleCalendarPlugin],
        googleCalendarApiKey: PUBLIC_GOOGLE_CALENDAR_API_KEY,
        events: {
            googleCalendarId: PUBLIC_GOOGLE_CALENDAR_ID
        }
    };
    })

  </script>
    <svelte:window bind:innerWidth />    
    <FullCalendar {options} />

    <style>
        :global(html) {
            font-family: Arial, Helvetica, sans-serif;
        }
    </style>
