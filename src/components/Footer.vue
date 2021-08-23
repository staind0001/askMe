<template>

      <nav class="sociales">
            <ul>
                <li>
                    <a href="https://www.facebook.com/enriquesotoDEV/"><ion-icon name="logo-facebook"></ion-icon></a>
                </li>
                <li>
                    <a href="https://github.com/staind0001?tab=repositories"><ion-icon name="logo-github"></ion-icon></a>
                </li>
                <li>
                    <a href="https://www.youtube.com/channel/UCztF_HudN9hgYv6EfuVlEeQ"><ion-icon name="logo-youtube"></ion-icon></a>
                    
                </li>
                <li>
                    <a href="https://www.enriquesoto.ch/"><ion-icon name="globe-outline"></ion-icon></a>
                </li>
                <li>
                    <a href="https://www.linkedin.com/in/enriquesotodev/"><ion-icon name="logo-linkedin"></ion-icon></a>
                </li>
            </ul>
             <div>@STDev 2021</div>
        </nav>
        
  
</template>

<script>


export default {

  
}
</script>

<style>
ion-icon {
  color:aliceblue;
  font-size: 32px;

}

.sociales ul li span{
    display: none;
}

.sociales li {
    list-style: none;
    padding:5px;
}

.sociales ul {
    display: flex;
    flex-wrap: wrap;
    /* justify-content: flex-start;
    justify-content: flex-end; */
    justify-content: center;
    /* justify-content: space-around;  */
    /* justify-content: space-between;   */
    flex:1 0 auto;
    text-decoration-skip: unset;
}

.sociales div{

    display: flex;
    flex-wrap: wrap;
    color: azure;
    justify-content: flex-end;
    justify-content: center;
   
}


</style>