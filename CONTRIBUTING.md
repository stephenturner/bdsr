## Contributing

The BDSR book is written in Quarto. Useful resources include the Quarto book documentation (https://quarto.org/docs/books/) and the HOPR book rewritten using Quarto (source: https://github.com/jjallaire/hopr; rendered: https://jjallaire.github.io/hopr/).

### New chapters

Create new Quarto documents (.qmd) for new chapters using the [basics.qmd](basics.qmd) chapter as a template. Label top-level headings with section labels (e.g., `# Basics {#sec-basics}`) and refer to them in other sections of the book with a cross-reference (e.g., `see xx and yy in [Chapter -@sec-basics]`). Include these quarto filenames as `chapters` under the relevant `part` (see the [_quarto.yml](_quarto.yml)) for examples.

Create new appendices the same way as new chapters, but include them as `appendices` in the [_quarto.yml](_quarto.yml).

Unnumbered chapters, such as [index.qmd](index.qmd) are achieved with `# Preface {.unnumbered}`.

### Exercises

Using the [basics.qmd](basics.qmd) chapter as a template, set the exercise counter at the top to 1:

    ```{r}
    #| echo: false
    options(digits=3)
    options(max.print=200)
    .ex <- 1
    ```

Exercises are called out inline using the [callout box syntax](https://quarto.org/docs/authoring/callouts.html). The inline R code prints the exercise number, then increments the exercise counter for the next exercise in that chapter. 


    ::: {.callout-note}
    
    # Exercise `r .ex``r .ex=.ex+1`
    
    What are the values after each statement in the following?
    
    ```{r ex1}
    mass <- 50              # mass?
    age  <- 30              # age?
    mass <- mass * 2        # mass?
    age  <- age - 10        # age?
    mass_index <- mass/age  # massIndex?
    ```
    
    :::

### Building and deploying

Render the book using the "Render Book" button in the RStudio build pane, or using the keyboard shortcut Cmd-Shift-B. The compiled book will be placed in the [_book](_book) directory by default. This directory is ignored by git. Use `quarto publish gh-pages` to publish.
