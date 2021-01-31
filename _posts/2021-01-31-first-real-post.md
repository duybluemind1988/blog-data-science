# A new post

## python code

```python
s = "Python syntax highlighting"
print s
```
```r

library(tidyverse)
library(ggplot)
print("my name is DNN")
```
```{r}
library(tidyverse)
# mutate_if() is particularly useful for transforming variables from one type to another
df <- attrition %>% mutate_if(is.ordered, factor, ordered = FALSE)
# Create training (70%) and test (30%) sets for the 
# rsample::attrition data.
set.seed(123)  # for reproducibility
churn_split <- initial_split(df, prop = .7, strata = "Attrition")
churn_train <- training(churn_split)
churn_test  <- testing(churn_split)
```

```{r}
set.seed(123)
cv_model1 <- train(
  Attrition ~ MonthlyIncome, 
  data = churn_train, 
  method = "glm",
  family = "binomial",
  trControl = trainControl(method = "cv", number = 5)
)
