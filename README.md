### Create Descriptive tables/statistics in Rstudio

table_1 <- Data%>%
  tbl_summary(
    by = group,
    missing="no",
    statistic = list(c(Age,BMI) ~ "{mean} ± {sd}"),
    digits = all_continuous() ~ 2,
    label = age ~ "Age (year)")%>%
  add_p(pvalue_fun = ~ style_pvalue(.x, digits = 3)) %>%
  add_overall() %>% 
  bold_labels()
table_1
