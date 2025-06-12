## UI Output Functions<!-- {docsify-ignore} -->

These functions are used in `app_server.R` to render data for display:

### `renderTable()`

Renders data frames as HTML tables in the UI.

**Common usage:**

```r
output$album_table <- renderTable({
    return(albums_by_bands(input$band_name))
})
```

### `renderText()`

Renders text output in the UI.

**Common usage:**

```r
output$avg_rating <- renderText({
    return(band_mean_rating(input$band_name))
})
```

### `renderPlot()`

Renders ggplot2 charts in the UI.

**Common usage:**

```r
output$compare_bands <- renderPlot({
    return(band_album_comparison_chart(input$band_name_1, input$band_name_2))
})
```
