# Day Planner Agent — Specification

## What It Does
- Reads Google Calendar for existing events
- Accepts from Arjun: task list, meetings, undated goals
- Builds conflict-free daily schedule
- Factors in: shift times, shuttle timing, prep time, travel, buffers
- Flags any conflicts
- Suggests times for undated tasks
- Pushes approved plan to Google Calendar

## Shift Timing Rules
- Monday morning: must leave by 6am, prep from 5:30am
- Tuesday/Friday: must leave by 4:30pm, prep from 4pm
- After night shift: short nap only, avoid long sleep
- After 24h shift: recovery day Saturday afternoon

## Input Format (what Arjun tells it)
- Fixed meetings: name + time + duration
- Tasks: name + estimated time needed
- Undated goals: things to fit in somewhere
- Working/free hours for that day

## Output Format
- Hour by hour schedule
- Conflict warnings
- Reasoning for time slot choices

## Tech Implementation
- Python script
- Google Calendar API for read/write
- Groq API for reasoning
- Triggered via Telegram message
