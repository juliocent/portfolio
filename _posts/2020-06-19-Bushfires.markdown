---
layout: page
title:  "Bushfires in NSW"
date:   2020-06-19 12:19:31 +1000
categories: project_bushfire
permalink: "/bushfire"
---
This was the final project I developed in the General Assembly Bootcamp.

It was my first contact with **Geographical Information Systems (GIS)** and an extraordinarily complex problem. The biggest challenge faced in this project is that there is a difference between the location of events and their time that makes data collection and features engineering overly complex.

For example, take the image below:
![undinned map](./assets/bushfire/2019.gif)

Each one of the points above is an event, a bushfire. Each event will have a different intensity, position and specific time. It is likely that points that are close, both in time and in space, are highly related. However, there is also a probable relation between points that are close in space, but **far in time**.

The best example for the paragraph above is the concept behind **prescribed burns**. If there is no fuel to burn, there is no fire. That is one of the probable relation between the events in time. More about prescribed burns [here](https://www.aph.gov.au/About_Parliament/Parliamentary_Departments/Parliamentary_Library/Publications_Archive/CIB/cib0203/03Cib08), and [here](https://www.smh.com.au/national/reality-check-there-are-limits-to-fighting-fire-with-fire-20191113-p53ac0.html).

Even if there are no prescribed burns, the fact that bushland has come under fire in the past **can influence the future** and feature engineering (creating features that a machine learning model will be able to understand) becomes very computationally intensive and prone to mistakes. This process needs to be **additive and very careful**.

The first approach in dealing with this complexity was to reduce the geographical area we were looking at to just cover NSW. It ended up looking something like this:
![undinned map NSW](./assets/bushfire/december.gif)

One important point to highlight now, binning further down may be problematic. If we subdivide the state in 1 degree squares and look at them we may loose information of the neighbouring events.
see the image below for example and let's consider the square with the blue dot (the 42nd square).
![binned nsw](./assets/bushfire/binned_nsw.png)

If we use only that area for analysis we loose the possible connection between the events and the neighbour areas. Not to mention that squares may have hidrographical and vegetation features that they share. Fires do not respect arbritary boundaries, we should not use them in our project as well.

---

This project is still in development and will be for some time.

So far, this project has a small app that I developed using Streamlit and Heroku (I am still having some problems with the deployment, once fixed I will link it here).

<!-- The best visualization for the project is using a density map, looking like the one below, but interactive:
![bushfire density map above](/assets/bushfire/above.jpg)

![bushfire density map angle](/assets/bushfire/angle.jpg) -->

