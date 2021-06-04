# Inyectores

    ## Lectura de Datos
    ```{r}
    datosPb2 <- read.csv("problem2.csv",header = F)
    ```
    
    ## Parametros dela distribucion de probabilidades
    ```{r}
    set.seed(100)
    xbar <- mean(datosPb2$V1)
    xbar
    st1 <- sd(datosPb2$V1)
    st1
    ```
    
    ## simulacion de n valores aleatroios con Distribucion normal
    ```{r}
    numsimula <- 2000  # Tamaño de la muestra
    xbar2 <- vector("double",numsimula)
    for (i in 1:numsimula)
    {
      simula <- rnorm(1,xbar,st1)
      xbar2[i] <- simula
      
    }
    ```
    
    ## Media de los valores simulados
    ```{r}
    mediafinal <- mean(xbar2)
    mediafinal
    ```
    ## Intervalo de confianza
    ```{r}
    t.test(xbar2)
    error <- (mediafinal- 7.062327 )/mediafinal*100
    error
    ```
    
    
    ## Simuilacion de  n muestras y su promedio para simular Tiempo
    ```{r}
    set.seed(526)
    ## Simulacion con 1000 muestras
    
    numsimula <- 1500  # Numero de muestras
    xbar2 <- vector("double",numsimula) # Guardar las medias de cada muestra
    
    for (i in 1:numsimula) {
      simula <- runif(100,1000, 5000)# Tamaño de la muestra
      xbar2[i] <- mean(simula)
    }
    
    hist(xbar2, main = "Medias de las muestras")
    
    mediafinal <- mean(xbar2)
    mediafinal
    
    abline(v=mediafinal, col="red" )
    
    ```
    ```{r}
    t.test(xbar2)
    
    error = (3004.56- 2998.822)/2998.822 * 100
    error
    ```

