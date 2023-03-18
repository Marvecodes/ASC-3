<template>
    <div class="container">
      
        <h1 className="error">404 Error</h1>
        <h2 className="not-found">Oops, Nothing to see here!</h2>
          
          <router-link to="/" class="link">
              <p className="error-button">Back to Home Page</p>
          </router-link>
    </div>
</template>

<script>
export default {
    name: "NotFound",} 
</script>

<style lang="scss" scoped>
.container{
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 30vh 0;
    flex-direction: column;

    .error{
        color: red;
        font-family: 'Courier New', Courier, monospace;
    }

    .link{
        text-decoration: none;
    }
    .error-button{
        background-color: #f7e2c6;
        color: #2a2221;
        padding: 10px 20px;
        border-radius: 20px;
        cursor: pointer;
        font-size: 18px;
        font-weight: 600;
    }
}

</style>