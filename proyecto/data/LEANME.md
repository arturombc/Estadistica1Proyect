Pongan aqui los .txt


{r, eval=TRUE, echo=FALSE, include=FALSE} 
# Colocar include=FALSE para que no se vea en la página

ui <- fluidPage(
  numericInput("n", "¿Cuántos carros?", 5),
  tableOutput("car_table")
)

server <- function(input, output) {
  output$car_table <- renderTable({
    head(cars, input$n)
  })
}

shinyApp(ui, server)