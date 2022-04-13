# Frontend Mentor - Interactive rating component solution

This is a solution to the [Interactive rating component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Select and submit a number rating
- See the "Thank you" card state after submitting a rating

### Screenshot

![](./screenshots/inicial-screen.png)


![](./screenshots/thanks-screen.png)

### Links

- Solution URL: [GitHub](https://github.com/mauriciomonti/mobile-interactive-rating)

## My process

### Built with

- HTML
- Tailwindcss
- Flexbox
- Mobile-first workflow
- [Jquery](https://releases.jquery.com/) - Jquery library
- [Tailwind](https://tailwindcss.com/docs/installation) - Tailwindcss
- [Styled Components](https://styled-components.com/) - For styles

### What I learned

This project helped me a lot to understand how the Tailwindcss front-end framework works, where I aimed to be able to create the layout using only this framework. I really liked it because it is very simple and works a lot with classes, and I also used some Jquery functionality to assign some effects to the buttons and pass on some information.

Submit button effects with Tailwindcss classes only:
```html
<button id="btnSubmit" class="text-sm text-white font-semibold tracking-widest h-12 w-full bg-orange-500 rounded-full grid place-items-center transform hover:text-orange-500 hover:bg-white transition-colors duration-200 ease-in-out">SUBMIT</button>
```
Modified colors to use with Tailwindcss:
```css
.proud-of-this-css {
    theme: {
        extend: {
            colors: {
                'cinza-claro': '#1f242f',
                'cinza-escuro': '#171e28',
            },
        }
        // ...
    }
}
```
Function to perform button color animation in Jquery using Tailwindcss classes:
```js
<!-- Script responsavel pelas função das notas -->
<script>
    /* Classes iniciais dos botões */
    btnInicialClasses = 'h-12 w-12 bg-[#282e39] rounded-full grid place-items-center transform hover:bg-orange-500 transition-colors duration-200 ease-in-out';
    btnClickedClasses = 'h-12 w-12 bg-gray-400 rounded-full grid place-items-center';

    // Adiciona as 5 estrelas
    for (let index = 1; index < 6; index++) {
        stringHtml = '<button id="btnStar' + index + '" type="btnEvaluate" class="' + btnInicialClasses + '">';
        stringHtml += '<h4 class="text-sm text-white font-normal opacity-50">' + index + '</h4>';
        stringHtml += '</button>';
        /* transform hover:bg-orange-500 transition-colors duration-200 ease-in-out = serve para adicionar o efeito de mudança de cor quando passa o mouse */
        $("#showStars").append(stringHtml);
    }

    /* Armazena o id Anterior */
    idAnterior = "Start";
    /* Função executa quando algum botão de numeros é clicado */
    $('button[type="btnEvaluate"]').click(function() {

        $('#botaoClicado').val($(this).text());

        if ($(this).attr('id') != idAnterior && idAnterior != "Start") {
            $("#" + idAnterior).attr('class', btnInicialClasses)
        }
        $(this).attr('class', btnClickedClasses)
        idAnterior = $(this).attr('id');
    });
</script>
}
```

### Continued development

I want to keep learning more and more about the Tailwind framework, I know it replaces many functions that would need Jquery.

### Useful resources

- [Center Elements with Tailwind CSS](https://daily-dev-tips.com/posts/center-elements-with-tailwind-css/) - This helped me figure out how to center an element inside a div. IVery useful in the future for organizing divs.

- [Instaling Tailwind](https://www.youtube.com/watch?v=1qH3wAtX4So) - This video helped me to install and run tailwindcss.

## Author

- LinkedIn - [Maurício Oliveira Monti](https://www.linkedin.com/in/maur%C3%ADcio-oliveira-monti-394086205/)
- Frontend Mentor - [@mauriciomonti](https://www.frontendmentor.io/profile/mauriciomonti)
- Github - [@mauriciomonti](https://github.com/mauriciomonti)