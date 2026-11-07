# Lab 5 — Seattle-Elliott Bay Vessel Flow Map

## 1. Study Area and Dates

My study area focuses on Seattle, Elliott Bay, and the surrounding waterways between Seattle and Bainbridge Island. I selected this area because it contains several active vessel routes, including passenger ferry traffic and other marine activity near the Seattle waterfront. The data were requested from NOAA's AccessAIS for July 15, 2025. AccessAIS timestamps are recorded in UTC, while the web map displays the time in Seattle local time (PDT for this July dataset). I used a one-day time period and a relatively small geographic area to keep the dataset manageable while still capturing enough vessel movement to identify spatial and temporal patterns. 

## 2. Interpretation

The map shows that passenger vessels tend to follow repeated corridors rather than spreading evenly throughout the study area. The clearest concentration is around the Seattle waterfront, where several paths converge before extending west across Elliott Bay toward Bainbridge Island and other nearby destinations. At the evening times I inspected, the Passenger filter showed multiple overlapping routes between Seattle and the west side of the study area, making the ferry corridors especially visible. Some routes are repeated closely enough that they form nearly identical lines, suggesting regularly used travel paths rather than random movement. Filtering the map by vessel type makes these patterns easier to see because it removes unrelated vessel traffic that would otherwise overlap the passenger routes. The animation and time slider also make it easier to see when vessels enter or leave these corridors instead of displaying an entire day of movement at once.

## 3. Feature Proposal for a Potential User

A potential user of this map could be a transportation planner or port analyst who wants to inspect individual vessel movements. One useful additional feature would be an interactive tooltip or popup that appears when the user clicks or hovers over a vessel path. The popup could show information such as the vessel name, vessel type, MMSI, speed, and current time. This idea is informed by the deck.gl interactivity guide, which explains how picking and tooltips can be used to inspect individual objects in a visualization.

This feature would make the map more useful because the current version shows vessel movement patterns but does not identify individual vessels. A transportation planner could use the popup to compare specific vessels and better understand which types of vessels are using particular routes at certain times.

Resource: https://deck.gl/docs/developer-guide/interactivity