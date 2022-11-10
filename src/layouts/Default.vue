<template>
  <div class="layout">
    <slot />
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style lang="scss">
@import "../scss/normalize";
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@100;300;400;600&display=swap");

html {
  font-family: "Josefin Sans", sans-serif;
  font-size: 62.5%;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: inherit;
}

body {
  background-color: #f2f2f2;
  margin: 0;
  padding: 0;
  color: #494C6B;
}

.layout {
  height: 100vh;
}

.header {
  display: flex;
  align-items: center;
  flex-direction: column;
  text-align: center;
  background-image: url("../images/bg-desktop-light.jpg");
  background-size: cover;
  width: 100%;
  height: 300px;
  h1 {
    font-size: 4rem;
    font-weight: bold;
    margin-bottom: 10px;
    color: #fff;
    letter-spacing: 1.2rem;
    text-align: left;
  }
  .container {
    display: grid;
    align-items: center;
    grid-template-columns: 1fr 1fr;
    margin-top: 20px;
    .image-toggle {
      justify-self: end;
      cursor: pointer;
    }
  }
}

main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: -140px;
  margin-bottom: 60px;
}

.container {
  width: 540px;
  margin: 0 auto;
  text-align: center;
  @media only screen and (max-width: 550px) {
    width: 340px;
  }
}

input {
  font-size: 1.8rem;
  padding: 20px 24px;
  font-family: "Josefin Sans", sans-serif;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.6);
  border: none;
  &:checked + label {
    text-decoration: line-through;
  }
}

.todo-input {
  width: 100%;
}

button {
  font-family: "Gugi", cursive;
  background-color: #e76042;
  color: #b8d1c6;
  font-size: 1.8rem;
  display: inline-flex;
  padding: 0;
  margin: 0;
  justify-content: center;
  align-items: center;
  //border-radius: 50%;
  color: #ffffff;
  width: 25%;
  height: 3rem;
  display: none;
}

form {
  margin-bottom: 24px;
  cursor: pointer;
}

label {
  padding-left: 20px;
}
.todo {
  margin-bottom: 24px;
  align-items: center;
  justify-content: center;
}

ul {
  margin: 0;
  font-size: 1.8rem;
  list-style-type: none;
  padding-left: 0;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.6);
  li {
    border-bottom: 1px solid #f2f2f2;
    background: #ffffff;
    div {
      display: flex;
    }
    label {
      padding: 20px 24px;
      display: inline-block;
      width: 100%;
      text-align: left;
      cursor: pointer;
    }
    input {
      margin-left: 20px;
      cursor: pointer;
    }
  }
}

.complete {
  text-decoration: line-through;
  color: #b8d1c6;
}

a {
  text-decoration: none;
}

.complete {
  text-decoration: line-through;
}

.info {
  font-size: 1.4rem;
}

.list-functions {
  padding: 20px 24px;
  text-align: right;
  span {
    cursor: pointer;
    font-size: 1.4rem;
  }
}

.todo-wrapper {
  position: relative;
  .delete {
    position: absolute;
    right: 20px;
    top: 12%;
    cursor: pointer;
    display: block;
    background: transparent;
    border: none;
    font-size: 4rem;
    height: auto;
    width: auto;
    font-family: 'Helvetica';
    display:none;
    span {
      color: #494C6B;
    }
  }
  &:hover {
    .delete {
      display: block;
    }
  }
}

//Dark Theme Styles 
.dark-theme {
  background-color: #171823;
  .header {
      background-image: url("../images/bg-desktop-dark.jpg");
  }
  input, .todo-wrapper {
    background-color: #25273D;
    color: #C8CBE7;
  }
  li {
    border-color: #393A4B;
  }
}

</style>
