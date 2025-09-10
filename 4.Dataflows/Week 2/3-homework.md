# JavaScript/React Fundamentals Homework

## Exercise 1: Step-through Prep & Breaking Down the Problem

**Goal:** Set up the static structure of the application and plan its components without any interactivity.

**Task:** You will build a "Task List" application. For now, it will only display a static (hard-coded) list of tasks.

1.  **Gathering Requirements:** Your app must:
    *   Display a heading (e.g., "My Task List").
    *   Show an unordered list of at least 3 tasks.
    *   Each task list item should display the task's text and a button (which will later become a "Delete" button).
    *   Include an input field and an "Add Task" button (these will not be functional yet).

2.  **Breaking Down the Problem:** Identify the components you will need. At a minimum, you should have:
    *   An `App` component (the root).
    *   A `TaskList` component to contain the list.
    *   A `Task` component to represent a single task.

3.  **Instructions:**
    *   Create a new React project (e.g., using `create-react-app` or Vite).
    *   Code the static version of the app as described. Use hard-coded data in your state for the tasks array (e.g., `const [tasks, setTasks] = useState([{ id: 1, text: 'Learn React' }, ...]);`).
    *   **Render** the list of tasks by **mapping** over the `tasks` array in state and returning a `<Task />` component for each item. Pass the task's `text` and `id` as props.

**Focus:** This step is about planning (`Breaking Down the Problem`) and setting up the initial static structure and rendering (`Rendering Based on State`).

---

## Exercise 2: Identifying State & Introducing Interactivity

**Goal:** Add interactivity to your Task List by identifying and managing state, and capturing user events.

**Task:** Make the "Add Task" and "Delete" buttons functional.

1.  **Identifying State:** You already have one state variable: `tasks`. This is the single source of truth for what tasks are displayed.

2.  **Capturing Events & Re-rendering:**
    *   **Adding a Task:**
        *   Create a new state variable `inputText` to hold the value of the input field.
        *   Add an `onChange` event handler to the input to update `inputText` as the user types.
        *   Add an `onClick` event handler to the "Add Task" button. This function should:
            *   Create a new task object (with a unique `id` and the `text` from `inputText`).
            *   Update the `tasks` state by creating a *new array* containing the old tasks plus the new one (e.g., using the spread operator `...`).
            *   Clear the `inputText` state.

    *   **Deleting a Task:**
        *   Pass a function from the `App` component down to each individual `Task` component as a prop (e.g., `onDelete`).
        *   This function should take a task `id` as an argument.
        *   In the `Task` component, attach this function to the `onClick` handler of the "Delete" button.
        *   The `onDelete` function in the `App` component will update the `tasks` state by filtering out the task with the matching `id`.

3.  **Actually Re-rendering:** Understand that calling the state setter functions (`setTasks` and `setInputText`) is what tells React to **re-render** the components that depend on that changed state. The UI will update automatically.

**Focus:** This step practices `Identifying State`, `Capturing Events`, updating state, and letting React handle `Re-rendering`.

---

## Exercise 3: Refactoring to State + Render

**Goal:** Improve your code's structure and separation of concerns by explicitly separating the logic of calculating state from the logic of rendering the UI.

**Task:** Refactor your `App.js` component.

1.  **Refactoring to State+Render:**
    *   Clearly separate the *state and logic* section of your component from the *return/render* section.
    *   Group all state variables (`tasks`, `inputText`) and handler functions (`handleAddTask`, `handleInputChange`, `handleDeleteTask`) at the top of the component, before the `return` statement.
    *   The `return` statement should be clean and primarily contain JSX that uses these state variables and handlers.

2.  **Example Structure:**
    ```jsx
    function App() {
      // --- STATE & LOGIC SECTION ---
      const [tasks, setTasks] = useState([...]);
      const [inputText, setInputText] = useState('');

      const handleInputChange = (e) => { ... };
      const handleAddTask = () => { ... };
      const handleDeleteTask = (id) => { ... };

      // --- RENDER SECTION ---
      return (
        <div className="App">
          <h1>My Task List</h1>
          {/* Input and Add button */}
          <TaskList tasks={tasks} onDelete={handleDeleteTask} />
        </div>
      );
    }
    ```

3.  **Reacting:** Think about the flow of data and interaction:
    *   A user **reacts** with the UI (clicks a button, types text).
    *   An event handler is triggered.
    *   The handler updates the **state**.
    *   The change in state causes React to **re-render** the UI, which now reflects the new state.

**Focus:** This final step reinforces clean code structure (`Refactoring to State+Render`) and solidifies the complete React cycle of `Reacting` to events, updating state, and re-rendering.

---

## Submission Instructions

1.  Please ensure your code is pushed to a GitHub repository.
2.  The repository should contain a `README.md` file with a brief description of the project and any instructions needed to run it (e.g., `npm install`, `npm start`).
3.  Share the link to your GitHub repository for review.

**Bonus Challenge:** Add a new feature: the ability to mark a task as "completed" (e.g., with a checkbox and styled with a line-through on the text). This will require you to **introduce new state** (a `completed` boolean property on each task object) and modify your rendering and event handlers accordingly.

# Additional Exercises

Of course. Here are two new, self-contained beginner-level JavaScript/React exercises that require students to apply the core concepts from scratch.

---

### **Exercise 1: The Mood Tracker**

Build a simple application that allows a user to track their current mood.

**Your App Must:**
*   Display a heading: "How are you feeling today?"
*   Show the current mood prominently on the screen. Initially, it can display "I'm feeling..." or something similar.
*   Provide a set of buttons for the user to select their mood (e.g., "Happy", "Sad", "Energetic", "Calm").
*   When a mood button is clicked, the displayed mood should update immediately to reflect the user's choice (e.g., "I'm feeling Happy!").
*   The background color of the entire app should also change to a different color when the mood changes (e.g., yellow for happy, blue for sad). Choose any colors you like.

---

### **Exercise 2: The Digital Coffee Shop Menu**

Build an interactive menu board for a coffee shop where a user can select items to see the total cost of their order.

**Your App Must:**
*   Display a heading: "Coffee Shop Menu"
*   List at least 4 menu items. Each item should be displayed with its name and price.
*   Next to each menu item, include an "Add" button.
*   Show a section titled "Your Order" that starts empty.
*   When the "Add" button for an item is clicked, that item should be added to the "Your Order" list.
*   The app must keep a running total of the cost of all items in the order and display it clearly at the bottom of the "Your Order" section.
*   Include a "Reset Order" button that clears the current order and resets the total cost to zero.