<script>
    import { slide } from 'svelte/transition';
    let sections = [
        {
            id: 1,
            title: "Section 1",
            active: false,
        },
        {
            id: 2,
            title: "Section 2",
            active: false,
        },
        {
            id: 3,
            title: "Section 3",  
            active: false,
            
        }
    ]
    
    const openSection = (section) => {
    sections = sections.map(button => {
        button.active = button.id === section.id && !section.active;
        return button;
    })
}
</script>

<style >
    .accordion {
    margin: 24px;
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

</style>

<div>
	<b><p style="font-size: 1.8rem; font-family: fira-sans,sans-serif;">
		2. Accordion
		</p></b>
</div>
{#each sections as section}
<div class="accordion">
    <button class='acc-button' on:click={() => openSection(section) }>{section.title}</button>
    {#if section.active}
        <div class="slider" transition:slide>       
			{#if section.title === 'Section 1' }     
				<h4>Subtitle 1</h4>
          		<p>Cras a vehicula orci. Nullam blandit, orci ac volutpat dapibus, ipsum nibh consequat massa, ut laoreet dui ligula ut sem. Sed condimentum volutpat justo. Donec tincidunt at lectus eu interdum. Vivamus pharetra efficitur magna, blandit accumsan orci lacinia non.</p>
            	<h4>Subtitle 2</h4>
             	<p>Ut sit amet semper tortor. Etiam ut finibus elit. Sed a rhoncus justo. Vestibulum in facilisis leo. Morbi rhoncus risus est, non gravida nunc porttitor id.</p>
              	<h4>Subtitle 3</h4>
               	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut sit amet semper tortor. Etiam ut finibus elit. Sed a rhoncus justo. Vestibulum in facilisis leo. Morbi rhoncus risus est, non gravida nunc porttitor id. Cras a vehicula orci. Nullam blandit, orci ac volutpat dapibus, ipsum nibh consequat massa, ut laoreet dui ligula ut sem. Sed condimentum volutpat justo. Donec tincidunt at lectus eu interdum. Vivamus pharetra efficitur magna, blandit accumsan orci lacinia non.</p>             
               
			{:else if section.title === 'Section 2'}
              	<p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut sit amet semper tortor. Etiam ut finibus elit. Sed a rhoncus justo. Vestibulum in facilisis leo. Morbi rhoncus risus est, non gravida nunc porttitor id. Cras a vehicula orci. Nullam blandit, orci ac volutpat dapibus, ipsum nibh consequat massa, ut laoreet dui ligula ut sem. Sed condimentum volutpat justo. Donec tincidunt at lectus eu interdum. Vivamus pharetra efficitur magna, blandit accumsan orci lacinia non.</p><p> Vestibulum in facilisis leo. Morbi rhoncus risus est, non gravida nunc porttitor id. Cras a vehicula orci.</p>
                
            {:else if section.title === 'Section 3'}
				   <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut sit amet semper tortor. Etiam ut finibus elit. Sed a rhoncus justo. Vestibulum in facilisis leo. Morbi rhoncus risus est, non gravida nunc porttitor id. Cras a vehicula orci. Nullam blandit, orci ac volutpat dapibus, ipsum nibh consequat massa, ut laoreet dui ligula ut sem. Sed condimentum volutpat justo. Donec tincidunt at lectus eu interdum. Vivamus pharetra efficitur magna, blandit accumsan orci lacinia non.</p>                             
				   {/if}
        </div>
    {/if}
</div>
{/each}