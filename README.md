# rplots
---
title: "Plots for QPM Project"
author: "Ruyi Ding"
date: "November 19, 2015"
output: pdf_document
---

```{r}
setwd("/Users/dingruyi/Documents/Wustl SP2016/materials")
data=read.csv("Education2.csv")
library(ggvis)
```

data preparation
```{r}
# math white/hispanic #1
data$hispagmath <- data$WHITEMATH - data$HISPANICMATH 

# reading white/hispanic #2
data$hispagrdg <- data$WHITERDG - data$HISPANICRDG 

# math white/nonhispanic black #3
data$nhbagmath <- data$WHITEMATH - data$NHBMATH 

# reading white/nonhispanic black #4
data$nhbagrdg <- data$WHITERDG - data$NHBRDG 

# reading nolunch/lunch #5
data$readingaglunch <- data$RDGNOLUNCH - data$RDGLUNCHPROG 

# math nolunch/lunch #6
data$mathaglunch <- data$MATHNOLUNCH - data$MATHLUNCHPROG 

# reading withoutdis/dis #7
data$disagreading <- data$NODISREAD - data$SPECREAD 

# math withoutdis/dis #8
data$disagmath <- data$NODISMATH - data$SPECMATH 
```

Plot
```{r}
# TITLEI
data %>% ggvis(~TITLEI,~hispagmath,fill= ~hispagmath) %>% 
    layer_points(size= ~hispagmath) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20, 90)) %>%
    add_legend(c("fill","size"), title = "Title I funds") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "Title I funds") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)

data %>% ggvis(~TITLEI,~hispagrdg,fill= ~hispagrdg) %>% 
    layer_points(size= ~hispagrdg) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20, 90)) %>%
    add_legend(c("fill","size"), title = "Title I funds") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "Title I funds") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)


data %>% ggvis(~TITLEI,~nhbagmath,fill= ~nhbagmath) %>% 
    layer_points(size= ~nhbagmath) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20, 90)) %>%
    add_legend(c("fill","size"), title = "Title I funds") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "Title I funds") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)

data %>% ggvis(~TITLEI,~nhbagrdg,fill= ~nhbagrdg) %>% 
    layer_points(size= ~nhbagrdg) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20, 90)) %>%
    add_legend(c("fill","size"), title = "Title I funds") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "Title I funds") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)

# SPENDCNA
data %>% ggvis(~SPENDCNA,~readingaglunch,fill= ~readingaglunch) %>% 
    layer_points(size= ~readingaglunch) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20,90)) %>%
    add_legend(c("fill","size"), title = "Child Nutrition Act funding") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "Child Nutrition Act funding") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)

data %>% ggvis(~SPENDCNA,~mathaglunch,fill= ~mathaglunch) %>% 
    layer_points(size= ~mathaglunch) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20,90)) %>%
    add_legend(c("fill","size"), title = "Child Nutrition Act funding") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "Child Nutrition Act funding") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)

# SPECFUND
data %>% ggvis(~SPECFUND,~disagreading,fill= ~disagreading) %>% 
    layer_points(size= ~disagreading) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20,90)) %>%
    add_legend(c("fill","size"), title = "federal funding for special education") %>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "federal funding for special education") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)

data %>% ggvis(~SPECFUND,~disagmath,fill= ~disagmath) %>% 
    layer_points(size= ~disagmath) %>%
    scale_numeric("fill", range = c("lightblue", "darkblue")) %>%
    scale_numeric("size", range = c(20,90)) %>%
    add_legend(c("fill","size"), title = "federal funding for special education")%>% 
    add_axis("y", title = "Achievement Gap") %>%
    add_axis("x", title = "federal funding for special education") %>%
    layer_smooths(stroke := "blue", strokeWidth := 2, strokeDash := 6)
```


