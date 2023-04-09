# ProductCarousel
Created a Product Carousel for Featured Products


The HTML structure consists of a .carousel-container with a .carousel-track containing multiple .carousel-items. The navigation buttons (previous and next) are also included in the container.
The CSS sets the container to have overflow: hidden so that only one item is displayed at a time, and uses flexbox to arrange the items side by side. The navigation buttons are positioned absolutely and styled as arrows.
The JavaScript selects the necessary DOM elements and adds event listeners to the navigation buttons. The initial position of the carousel is set, and the itemWidth is calculated based on the width of the first item. The automatic rotation is achieved using setInterval(), and the carousel is made responsive by adjusting itemWidth on window resize.
The carousel can be customized by changing the content of the .carousel-items and modifying the CSS to match the desired design.


This CSS code styles the featured product carousel by:

position: relative; allows us to position the navigation buttons inside the container.
max-width: 100%; sets the maximum width of the container to the full width of its parent element.
overflow: hidden; hides any content that overflows outside the container.
margin: 0 auto; centers the container horizontally.
display: flex; allows the items to be displayed in a row.
transition: transform 0.3s ease-in-out; adds a smooth transition effect when the track is translated left or right.
flex-direction: column; stacks the item content vertically.
justify-content: center; centers the item content vertically.
align-items: center; centers the item content horizontally.
min-width: 100%; ensures each item takes up the full width of the track.
height: 100%; ensures each item takes up the full height of the container.
text-align: center; centers any text content inside the item.
max-width: 100%; ensures the image is scaled down to fit the width of the item.
max-height: 100%; ensures the image is scaled down to fit the height of the item.
position: absolute; allows us to position the buttons on top of the carousel.
top: 50%; positions the buttons vertically in the center of the container.
transform: translateY(-50%); centers the buttons vertically by translating them up by half their height.
border: none; removes any borders around the buttons.
background: none; removes any backgrounds behind the buttons.
font-size: 2rem; sets the font size of the buttons to 2rem.
cursor: pointer; changes the cursor to a pointer when hovering over the buttons.
.carousel-prev { left: 20px; } positions the previous button 20 pixels from the left side of the container.



JavaScript Explaination:

document.querySelector and document.querySelectorAll methods to select the carousel track, the carousel items, and the navigation buttons with the classes .carousel-track, .carousel-item, .carousel-prev, and .carousel-next, respectively.
Here, we set up a variable itemWidth that will hold the width of each carousel item. We set its value to the width of the first item in the items array using the clientWidth property. We also set up a variable currentIndex to keep track of the current index of the carousel item being displayed, starting with the first item (index 0).
This line sets the initial position of the carousel track using the transform property. The translateX() function is used to move the track horizontally by a certain distance, which is calculated by multiplying the current index (currentIndex) by the item width (itemWidth) and making it negative so that the track moves to the left.
When the previous button is clicked, the currentIndex is decremented by 1, and if it becomes less than 0 (i.e. the first item), it wraps around to the last item by setting it to items.length - 1. Similarly, when the next button is clicked, the currentIndex is incremented by 1, and if it becomes greater than or equal to the length of the items array (i.e. the last item), it wraps around to the first item by setting it to 0. The track.style.transform property is updated to move the track to the new position based on the new currentIndex.
the setInterval() method to automatically rotate the carousel every 3 seconds. The currentIndex is incremented by 1, and if it becomes greater than or equal to the length of the items array (i.e. the last item), it wraps around to the first item by setting it to 0. The track.style.transform property is updated to move the track to the new position based on the new currentIndex.
adds a resize event listener to the window object, which fires whenever the window size is changed. Inside the event listener, we recalculate the itemWidth variable based on the new width of the first item in the carousel (items[0].clientWidth). This ensures that the item width is always up to date and accurate.
We then update the position of the carousel track by setting its transform property using the translateX() function, passing in the negative value of the current slide index multiplied by the new itemWidth. This ensures that the currently displayed slide stays in the same position relative to the left edge of the carousel container, even after the window size changes.
