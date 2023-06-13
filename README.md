# vue-components-communication

In Vue 3, you can use the Composition API to define components and communicate between them using props. The Composition API provides a more flexible and powerful way to organize and reuse component logic.

To demonstrate how components communicate via props in Vue 3 with the Composition API, let's create a simple example.

## Parent component
This is the parent component code:

```vue
<template>
  <div>
    <h1>Parent Component</h1>
    <ChildComponent :message="parentMessage" />
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

// Define a reactive property
const parentMessage = ref("Hello from parent");
</script>
```

In this example, we have a parent component that renders a child component and passes a prop named "message" to it. The parent component defines a reactive property parentMessage using the ref function from the Composition API. This property holds the message that will be passed to the child component.

## Child component
The child component can then receive and use the prop passed from the parent component. Here's the code for the child component:

```vue
<template>
  <div>
    <h2>Child Component</h2>
    <p>{{ message }}</p>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";

// Define a reactive property
const message = ref("");
</script>
```

The child component defines a reactive property "message" for receiving the parent property. 
Finally, the child component can access and render the value of the "message" prop passed from the parent component using props.message in the template.

Remember to create separate files for the parent and child components, naming them accordingly. The parent component should import and use the child component, as shown in the parent component code snippet.

## App.vue component
This is the code for the "App" component:

```vue
<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <ParentComponent />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ParentComponent from "./components/ParentComponent.vue";

export default defineComponent({
  name: "App",
  components: {
    ParentComponent,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
