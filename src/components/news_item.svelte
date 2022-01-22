<script>
    export let item;
    const favThis = (item)=>{
        console.log(item.title);
    }
</script>

<div class="feed-item">
    <img class="js-icon"src="https://img.icons8.com/color/48/000000/javascript--v1.png" alt=""/>
   <h3>{item.title}</h3>
   <div>
    <a href={item.link} class="story-link" >Read More</a>
    <button on:click={()=>favThis(item)} class="favbtn">
        Add to favorites
    </button>
   </div>
   <div class="details">
       <b>{item.time_posted} | {item.author} | {item.score} upvotes</b>
   </div>
</div>

<style>
    .feed-item{
        margin: 15px;
        padding: 30px;
        background-color:lightblue;
        color: darkmagenta;
        border-radius: 25px;
        position: relative;
    }
    .story-link{
        background-color: darkmagenta;
        color: lightblue;
        padding: 10px;
        margin: 5px 5px;
        border-radius: 20px;
    }
    .details{
        font-size: 12px;
        color: darkmagenta;
        padding: 10px 0px 10px 0px;
    }
    .js-icon{
        border-radius: 50px;
        position: absolute;
        right: 15px;
        bottom: 10px;
    }
    .favbtn {
        padding: 10px;
        border-radius: 20px;
    }
</style>