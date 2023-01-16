# Advertising Management Dashboard

## Deployment link

[https://pre-onboarding-7th-2-2-4-vv9dr45j2-wanted-4th.vercel.app](https://pre-onboarding-7th-2-2-4-vv9dr45j2-wanted-4th.vercel.app/)

# How to set up and run your environment

## Configuration Settings

1. It is recommended to run on NodeJS 16.14.2.

## Installation

```
npm ci
```

## Execute

```
npm start
```

# Directory structure

```
📦src
┣ ┣ 📂Components
┃ ┃ ┣ 📂Button
┃ ┃ ┣ 📂ComboBox
┃ ┃ ┣ 📂ContentHeader
┃ ┃ ┣ 📂Header
┃ ┃ ┣ 📂Layout
┃ ┃ ┣ 📂Main
┃ ┃ ┣ 📂SelectButton
┃ ┃ ┣ 📂Svg
┃ ┃ ┗ 📂assets
┣ ┣ 📂Pages
┃ ┃ ┣ 📂AdManagement
┃ ┃ ┃ ┣ 📂hooks
┃ ┃ ┗ 📂DashBoard
┃ ┃ ┃ ┣ 📂hooks
┣ ┣ 📂Routes
┣ ┣ 📂lib
┃ ┃ ┣ 📂api
┃ ┃ ┣ 📂constant
┃ ┃ ┣ 📂state
┃ ┃ ┣ 📂style
┃ ┃ ┗ 📂utils
┣ ┣ 📜App.tsx
┣ ┣ 📜index.tsx
┣ ┣ 📜logo.svg
┗ ┗ 📜react-app-env.d.ts
```

# Troubleshooting

## 1. Dependency concerns

- Project design was carried out after considering dependency reversal and dependency injection. I felt that it was more difficult than I thought to think about dependency and make code. So I applied it to a part of the project. When designing components and creating custom hooks, I had a lot of thoughts about how to design them with weak combinations.

## 2. Thinking about reducing overlapping components and optimizing rendering

- In the case of the ad management page, there are many components that change to input when modifying, so I thought about how to increase readability and save rendering resources for input components.
- Each component that changes to input ↔ span in a custom hook is grouped into a function, and the rendering function is memoized with useCallback so that the function can be rendered without creating a new function each time it is edited.

## 3. Global health management and data retention through recoil

- To implement dashboards and graphs on the main page, startDate and endDate selected by date picker were managed globally.
- Date status was very important because the dashboard for this project shows the data to the customer based on the date status was very important. The date had to be maintained even if you left the page and came back. Therefore, we used Recoil, a global health management tool, to ensure that the date status remains the date selected by the customer even when the component is unmounted.

# Usage Library

- styled-components
    
    I used it for CSS style.
    
- recoil
    
    You can easily manage global health by creating atom as a global health management tool.
    
- apexcharts
    
    APEXCHART is a chart library that visualizes data, and there are various styles such as line graphs, bubbles, timelines, and heat maps, and even custom functions are implemented in the responsive type.
    
- react-datepicker
    
    It was used to easily set a range of dates and get values.
    
- dayjs
    
    You used a small-sized date management library.
