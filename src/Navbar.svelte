<style>  
        .topnav {
          overflow: hidden;
          background-color: #333;
          width:100%;
        }
        
        .topnav a {
          float: left;
          display: block;
          color: #f2f2f2;
          text-align: center;
          padding: 16px;
          text-decoration: none;
          font-size: 1rem;
        }
        
        @media screen and (max-width: 800px) {
            .topnav {
              font-size: 0.5rem;
          }
        }

        .topnav a:hover {
            background-color: #555;
        }

        .topnav .icon {
          display: none;
          padding: 10px;
        }
        
        .responsive {
          text-align: center;
        }

          .acc {
            margin-bottom: 6px;
            display: none;
        }
        .acc-button {
            display: flex;
            width: 100%;
            align-items: center;
            height: 60px;
            font-size: 1.5rem;    
        }
        
        .acc-button:hover {
            cursor: pointer;
        }
          
        .slider {
            padding: 6px;
            font-size: 20px;
            font-family: fira-sans,sans-serif;
        }
        
        .hidden a:hover {
          background-color: #555;
        }
        
        @media screen and (max-width: 800px) {
            
          .acc {
            display: block;
        }
          .topnav a:not(:first-child) {display: none;}
          .topnav a.icon {
            float: right;
            display: block;
          }
        }
        
        @media screen and (max-width: 800px) {
          .topnav.responsive {position: relative;}
          .topnav.responsive .icon {
            position: absolute;
            right: 0;
            top: 0;
          }
          .topnav.responsive a {
            float: none;
            display: inline-block;
            text-align: left;
          }
        }

        .responsive-nav {
            font-size: 1.8rem; 
            font-family: fira-sans,sans-serif;
        }

         @media screen and (max-width: 800px) {
            .responsive-nav {
                font-size: 0.8rem;
            }
        }
        </style>
        
        <script>
            import { slide } from 'svelte/transition';
            export let current = '';
           
            let sections = [
                {
                    title: "Open",
                    active: false,
                }
            ]
        
            const expand = (section) => {
            sections = sections.map(s => {
                s.active = s.id === section.id && !section.active;
                return s;
            })
        }
          </script>
        <div>
            <b><p class="responsive-nav">1. Responsive Navigation Bar</p></b>
            <p style='text-align: center'>Try resizing the browser!</p>
        </div>

        <nav style="margin-top: 16px;" class="standard-text body-text"> 
            <div class="topnav" id="myTopnav">
                <a href="#" >NavBar</a> 
                <a href="index.html" style='float: right;'>Home</a>
                <a href="#" style='float: right;'>Contact</a>
                <a href="#" style='float: right;'>About</a>
    
    
                {#each sections as section}
                    <div class="accn">
                        <a href='#' class="icon" on:click={() => expand(section) }>MENU</a>
    
                {#if section.active}
                    <div class="slider" transition:slide>
    
                        {#if section.title === 'Open' }
                            <div class='hidden'>
                                <br /><p><a style='color: white; width: 100%; text-align: center;' href="index.html">Home</a></p>   
                                <br /><p><a style='color: white; width: 100%; text-align: center;' href="#">Contact</a></p>    
                                <br /><p><a style='color: white; width: 100%; text-align: center;' href="#">About</a></p>   
                            </div>
                        {/if}
                     </div>
                {/if}
               
              </div>
              {/each}
            </div>
        </nav>