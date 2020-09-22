<script>

    let formElement;
    function handleMouseenter() {
        formElement.style.backgroundColor = "red";
        formElement.style.boxShadow = "2px 2px 14px black";
    }    
    function handleMouseleave() {
        formElement.style.background = "linear-gradient(to bottom right, rgba(120,100,100,0.2), rgba(100,50,214,0.9))";
        formElement.style.boxShadow = "none";

    }

</script>


<div class="login-box">

	 <form method="post" class="form-group">
     
        <div class="both-form">
        
            <div class="form" bind:this={formElement} on:mouseenter={handleMouseenter} on:mouseleave={handleMouseleave}>
            <h2>Please log in</h2>
          <label for="myInput">Username:
          <input type="text" id="myInput" name="username" /></label><br>
          <label for="myInput">Password:
          <input type="password" id="myInput" name="password" /></label>

            <button type="submit" id="myButton">Login</button>

            </div>
        </div>
    </form>

</div>

<style type="text/scss">
.login-box {
    text-align: center;
    animation-name: animateappear;
    animation-duration: 0.6s;
    animation-fill-mode: both;
    
    & h3 {
        font-size: 18px;
        text-decoration: none;
        
    }
    .both-form {
        background: linear-gradient(to bottom, rgba(120,10,100,0.4), rgba(800,100,14,0.3));
        box-shadow: 1px 4px 4px black;
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(800px, 2fr));
        transition: all 0.3s;
        z-index: 10;
        align-content: center;
        overflow: hidden;
        margin-bottom: 5px;
        }
    }

.form {
    // margin: 5% 0% 0% 10%;
    padding-top: 1rem;
    background: linear-gradient(to bottom right, rgba(120,100,100,0.2), rgba(100,50,214,0.9));
    font-size: 1.6rem;
    font-weight: bold;
    text-align: center;
    border: 1px solid black;
    display: inline-block;
    padding: 1rem;
    grid-template-rows: repeat(auto-fill, minmax(200px, 1fr));
    grid-template-columns: repeat(auto-fill, minmax(200px, 5fr));
    margin: 0rem 10%;
    box-shadow: 1px 1px 5px black;
    border-radius: 8px;
    & #myInput {
        margin: 1rem 0% 2rem;
        width: 90%;
        padding: 0.5rem;
    }
    & #myButton {
        background: #9eaaa285;
        position: relative;
        margin: 0.5rem;
        padding: 0.5rem 1.6rem;
        border-radius: 4px;
        &:hover {
            background: #eee;
            box-shadow: 1px 1px 1px #2e3d3359;
            outline: none;
            cursor: pointer;
        }
    }   
}  

@media screen and (min-width: 600px) {
div.login-box, div.both-form {
    font-size: 1.6rem;
    padding: 2rem 2rem;
    }
}
@media screen and (max-width: 600px) {
.login-box, .both-form, .form {
    font-size: 1.2rem;
    padding: 0.2rem 0.8rem;
    margin-left: -1rem;
    & #myInput {
        padding-left: 1rem;
        margin-left: 3rem;
        width: 60%;
        display: block;
    }
    }
}


</style>


