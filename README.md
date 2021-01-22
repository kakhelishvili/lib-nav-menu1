# ნავ. მენიუს ანიმაცია

**მოკლედ ამ კოდის შესახებ:**
- 1 არის მარტივი ჩასასმელი და გასასტილი
- 2 დაგჭირდებათ jquery-ს და bootstrap-ის მიბმა

პროექტის [Codepen-ში გახსნა](https://codepen.io/kakhelishvili/pen/mdrYMQO)

## დაყენების ინსტრუქცია

ვიწყებთ `html`-ით. პირველრიგში `head`-ის თაგს შორის ვამატებთ bootstrap-ის CSS-ს:

```html
<head>
  <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet"/>
</head>
```

სტილის დამატების გარდა დაგვჭირდება დავამატოთ jquery-ს და bootstrap-ის js-ფაილები.

```html
<body>
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
</body>
```
`html`-ის ფოლდერში ვამატებთ ღილაკის მარკაპს.

```html
<!-- Bootstrap Navigation -->
    <nav>
        <button class="navbar-toggler collapsed border-0" data-toggle="collapse" data-target="#collapsingNavbar">
            <span> </span>
            <span> </span>
            <span> </span>
        </button>
        <div class="" id="collapsingNavbar">
            <div>
                ჩამოშლა
            </div>
        </div>
    </nav>
```

ანიმაციისთვის დაგვჭირდება ჩვენს CSS ფაილში ჩავწეროთ შემდეგი კოდი:

```css
/* Define the shape and color of the hamburger lines */
.navbar-toggler span {
    display: block;
    background-color: #4f4f4f;
    height: 3px;
    width: 25px;
    margin-top: 5px;
    margin-bottom: 5px;
    position: relative;
    left: 0;
    opacity: 1;
    transition: all 0.35s ease-out;
    transform-origin: center left;
}

/* top line needs a little padding */
.navbar-toggler span:nth-child(1) {
    margin-top: 0.3em;
}

/*  Animate collapse into X. */

/* top line rotates 45 degrees clockwise and moves up and in a bit to close the center of the X in the center of the button */
.navbar-toggler:not(.collapsed) span:nth-child(1) {
    transform: translate(15%, -33%) rotate(45deg);
}
/* center line goes transparent */
.navbar-toggler:not(.collapsed) span:nth-child(2) {
    opacity: 0;
}
/* bottom line rotates 45 degrees counter clockwise, in, and down a bit to close the center of the X in the center of the button  */
.navbar-toggler:not(.collapsed) span:nth-child(3) {
    transform: translate(15%, 33%) rotate(-45deg) ;
}

/* top line moves back to initial position and rotates back to 0 degrees */
.navbar-toggler span:nth-child(1) {
    transform: translate(0%, 0%) rotate(0deg) ;
}
/* middle line goes back to regular color and opacity */
.navbar-toggler span:nth-child(2) {
    opacity: 1;
}
/* bottom line goes back to initial position and rotates back to 0 degrees */
.navbar-toggler span:nth-child(3) {
    transform: translate(0%, 0%) rotate(0deg) ;
}
```
## დამატებითი წყარო

- [stackoverflow](https://stackoverflow.com/questions/60725510/how-do-i-make-a-menu-icon-on-a-responsive-navigation-bar-animated-into-an-x-icon)
