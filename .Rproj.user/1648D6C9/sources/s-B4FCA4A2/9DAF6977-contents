# Load libraries, data -----------------------------------------------
characters <- read.csv("data/characters.csv")


# Page 1 - Introduction ----------------------------------------------
intro_panel <- tabPanel(
  "Introduction",
  
  titlePanel("Characteristics of Mario Kart Drivers"),
  
  img(src = "mariokart8.jpg", height = 400, width = 800),
  br(), br(),
  
  p("This is the final assignment of the Developing Data Products Course from Johns Hopkins University Data Science Specialization. This is the scope:
Write a shiny application with associated supporting documentation. The documentation should be thought of as whatever a user will need to get started using your application.
Deploy the application on Rstudio’s shiny server
Share the application link by pasting it into the provided text box
Share your server.R and ui.R code on github"),
  
  p(a(href = "https://www.kaggle.com/barelydedicated/mariokart8?select=characters.csv", "Data Source (Kaggle)"))
)

# Page 2 - Vizualization -------------------------------------------
select_values <- colnames(characters)
select_values <- select_values[! select_values %in% c('Character', 'Class')] # remove unwanted columns

sidebar_content <- sidebarPanel(
  selectInput(
    "y_var",
    label = "Y Variable",
    choices = select_values,
    selected = 'Speed'
  )
)

main_content <- mainPanel(
  plotOutput("plot")
)

second_panel <- tabPanel(
  "Visualization",
  titlePanel("What are the Characteristics of each Mario Kart 8 Driver?"),
  p("Use the selector input below to choose which variable you would like to see."),
  sidebarLayout(
    sidebar_content, main_content
  )
)



# User Interface -----------------------------------------------------
ui <- navbarPage(
  "Mario Kart Characteristics",
  intro_panel,
  second_panel
)