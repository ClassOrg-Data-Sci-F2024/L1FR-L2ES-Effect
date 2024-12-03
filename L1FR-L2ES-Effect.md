L1FR-L2ES-Effect
================
CMVA
2024-11-07

# Initial Read-in

The data was downloaded from the corpus originally as separate excel
files that were all A1 level Spanish learners, but each file was for a
different conjugation of the verb *ir* ‘to go’.

There are two datasets: L1 French speakers and L1 English speakers.
These were chosen in order to analyze whether having a language with the
same periphrastic future construction does actually affect language
transfer.

The individual Excel files will be read in and then combined into one
dataset (per language) for analysis.

``` r
getwd()
```

    ## [1] "C:/Users/vegam/OneDrive/Documents/L1ES-L2FR-Effect"

``` r
read_excel("Excels/A1IR.xlsx")
```

    ## # A tibble: 166 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 774        2154  Correo electrónico  Cambio…    22 Mujer Fran… Fran… Otros   
    ##  2 1239       3493  Correo electrónico  Cambio…    58 Homb… Fran… Fran… Univers…
    ##  3 1974       5564  Correo electrónico  Familia    45 Homb… Fran… Fran… Secunda…
    ##  4 776        2160  Correo electrónico  Cambio…    65 Mujer Fran… Fran… Otros   
    ##  5 2002       5639  Correo electrónico  Cambio…    64 Homb… Fran… Fran… Otros   
    ##  6 2002       5639  Correo electrónico  Cambio…    64 Homb… Fran… Fran… Otros   
    ##  7 380        1053  Nota/aviso          Nota l…    37 Mujer Fran… Fran… Univers…
    ##  8 779        2169  Correo electrónico  Cambio…    52 Mujer Fran… Fran… Otros   
    ##  9 775        2158  Nota/aviso          Nota l…    27 Mujer Fran… Fran… Otros   
    ## 10 781        2177  Correo electrónico  Familia    36 Mujer Fran… Fran… Otros   
    ## # ℹ 156 more rows
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/A1VOY.xlsx")
```

    ## # A tibble: 50 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 840        2342  Correo electrónico  Cambio…    61 Mujer Fran… Fran… Univers…
    ##  2 840        2343  Nota/aviso          Nota l…    61 Mujer Fran… Fran… Univers…
    ##  3 831        2318  Correo electrónico  Cambio…    68 Mujer Fran… Fran… Univers…
    ##  4 791        2207  Correo electrónico  Familia    57 Homb… Fran… Fran… Secunda…
    ##  5 840        2342  Correo electrónico  Cambio…    61 Mujer Fran… Fran… Univers…
    ##  6 1463       4138  Correo electrónico  Cambio…    37 Mujer Guin… Fran… Primaria
    ##  7 1463       4139  Nota/aviso          Nota l…    37 Mujer Guin… Fran… Primaria
    ##  8 840        2342  Correo electrónico  Cambio…    61 Mujer Fran… Fran… Univers…
    ##  9 2129       5993  Nota/aviso          Nota l…    23 Mujer Cost… Fran… Secunda…
    ## 10 2042       5751  Correo electrónico  Cambio…    71 Homb… Fran… Fran… Otros   
    ## # ℹ 40 more rows
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/A1VAS.xlsx")
```

    ## # A tibble: 4 × 19
    ##   Estudiante Tarea `Tipología textual` Tema      Edad Sexo  País  L1    Estudios
    ##   <chr>      <chr> <chr>               <chr>    <dbl> <chr> <chr> <chr> <chr>   
    ## 1 371        1028  Correo electrónico  Familia     25 Mujer Líba… Fran… Univers…
    ## 2 638        1774  Correo electrónico  Familia     62 Homb… Fran… Fran… Univers…
    ## 3 1239       3495  Correo electrónico  Familia     58 Homb… Fran… Fran… Univers…
    ## 4 636        1767  Nota/aviso          Nota ll…    60 Mujer Fran… Fran… Secunda…
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/A1VA.xlsx")
```

    ## # A tibble: 50 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 2096       5907  Correo electrónico  Familia    52 Mujer Fran… Fran… Univers…
    ##  2 480        1334  Nota/aviso          Nota l…    43 Mujer Bélg… Fran… Univers…
    ##  3 390        1083  Correo electrónico  Familia    42 Mujer Fran… Fran… Secunda…
    ##  4 829        2314  Correo electrónico  Familia    45 Mujer Líba… Fran… Univers…
    ##  5 1406       3982  Correo electrónico  Cambio…    37 Mujer Guin… Fran… Univers…
    ##  6 831        2320  Correo electrónico  Familia    68 Mujer Fran… Fran… Univers…
    ##  7 257        711   Correo electrónico  Cambio…    18 Mujer Fran… Fran… Secunda…
    ##  8 2096       5907  Correo electrónico  Familia    52 Mujer Fran… Fran… Univers…
    ##  9 827        2308  Correo electrónico  Familia    64 Mujer Fran… Fran… Univers…
    ## 10 827        2308  Correo electrónico  Familia    64 Mujer Fran… Fran… Univers…
    ## # ℹ 40 more rows
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/A1VAMOS.xlsx")
```

    ## # A tibble: 12 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 775        2159  Correo electrónico  Familia    27 Mujer Fran… Fran… Otros   
    ##  2 791        2207  Correo electrónico  Familia    57 Homb… Fran… Fran… Secunda…
    ##  3 480        1333  Correo electrónico  Cambio…    43 Mujer Bélg… Fran… Univers…
    ##  4 838        2338  Correo electrónico  Familia    60 Mujer Fran… Fran… Univers…
    ##  5 840        2343  Nota/aviso          Nota l…    61 Mujer Fran… Fran… Univers…
    ##  6 2129       5992  Correo electrónico  Cambio…    23 Mujer Cost… Fran… Secunda…
    ##  7 797        2224  Nota/aviso          Nota l…    55 Mujer Fran… Fran… Univers…
    ##  8 480        1334  Nota/aviso          Nota l…    43 Mujer Bélg… Fran… Univers…
    ##  9 2096       5907  Correo electrónico  Familia    52 Mujer Fran… Fran… Univers…
    ## 10 777        2164  Nota/aviso          Nota l…    36 Homb… Fran… Fran… Univers…
    ## 11 232        641   Nota/aviso          Nota l…    16 Homb… Móna… Fran… Secunda…
    ## 12 1973       5560  Nota/aviso          Nota l…    55 Homb… Fran… Fran… Secunda…
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/IRENG.xlsx")
```

    ## # A tibble: 47 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 1681       4772  Nota/aviso          Nota l…    63 Homb… Esta… Ingl… Univers…
    ##  2 201        552   Correo electrónico  Cambio…    32 Mujer Fran… Ingl… Primaria
    ##  3 55         148   Correo electrónico  Cambio…    52 Mujer Irla… Ingl… Otros   
    ##  4 1622       4601  Nota/aviso          Nota l…    15 Homb… Esta… Ingl… Primaria
    ##  5 101        275   Nota/aviso          Nota l…    49 Homb… Irla… Ingl… Primaria
    ##  6 1630       4619  Correo electrónico  Cambio…    23 Homb… Aust… Ingl… Univers…
    ##  7 53         142   Correo electrónico  Cambio…    57 Homb… Irla… Ingl… Otros   
    ##  8 1333       3775  Nota/aviso          Nota l…    25 Mujer China Ingl… Univers…
    ##  9 59         161   Nota/aviso          Nota l…    50 Homb… Irla… Ingl… Otros   
    ## 10 101        275   Nota/aviso          Nota l…    49 Homb… Irla… Ingl… Primaria
    ## # ℹ 37 more rows
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/VOYENG.xlsx")
```

    ## # A tibble: 47 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 57         154   Correo electrónico  Cambio…    49 Mujer Irla… Ingl… Otros   
    ##  2 98         266   Nota/aviso          Nota l…    60 Homb… Irla… Ingl… Primaria
    ##  3 59         161   Nota/aviso          Nota l…    50 Homb… Irla… Ingl… Otros   
    ##  4 2278       6385  Correo electrónico  Cambio…    22 Mujer Core… Ingl… Univers…
    ##  5 1333       3774  Correo electrónico  Cambio…    25 Mujer China Ingl… Univers…
    ##  6 356        983   Correo electrónico  Cambio…    63 Mujer Rein… Ingl… Univers…
    ##  7 59         161   Nota/aviso          Nota l…    50 Homb… Irla… Ingl… Otros   
    ##  8 98         265   Correo electrónico  Cambio…    60 Homb… Irla… Ingl… Primaria
    ##  9 138        371   Nota/aviso          Nota l…    43 Homb… Core… Ingl… Otros   
    ## 10 58         157   Correo electrónico  Cambio…    61 Homb… Irla… Ingl… Otros   
    ## # ℹ 37 more rows
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/VASENG.xlsx")
```

    ## # A tibble: 1 × 19
    ##   Estudiante Tarea `Tipología textual` Tema      Edad Sexo  País  L1    Estudios
    ##   <chr>      <chr> <chr>               <chr>    <dbl> <chr> <chr> <chr> <chr>   
    ## 1 98         266   Nota/aviso          Nota ll…    60 Homb… Irla… Ingl… Primaria
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/VAENG.xlsx")
```

    ## # A tibble: 30 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 56         153   Correo electrónico  Familia    23 Homb… Irla… Ingl… Univers…
    ##  2 1630       4619  Correo electrónico  Cambio…    23 Homb… Aust… Ingl… Univers…
    ##  3 356        985   Correo electrónico  Familia    63 Mujer Rein… Ingl… Univers…
    ##  4 231        639   Correo electrónico  Familia    28 Homb… Rein… Ingl… Univers…
    ##  5 53         142   Correo electrónico  Cambio…    57 Homb… Irla… Ingl… Otros   
    ##  6 201        554   Correo electrónico  Familia    32 Mujer Fran… Ingl… Primaria
    ##  7 55         150   Correo electrónico  Familia    52 Mujer Irla… Ingl… Otros   
    ##  8 140        377   Correo electrónico  Familia    52 Mujer Esta… Ingl… Univers…
    ##  9 201        554   Correo electrónico  Familia    32 Mujer Fran… Ingl… Primaria
    ## 10 53         142   Correo electrónico  Cambio…    57 Homb… Irla… Ingl… Otros   
    ## # ℹ 20 more rows
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/VAMOSENG.xlsx")
```

    ## # A tibble: 10 × 19
    ##    Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País  L1    Estudios
    ##    <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr> <chr> <chr>   
    ##  1 55         150   Correo electrónico  Familia    52 Mujer Irla… Ingl… Otros   
    ##  2 210        576   Nota/aviso          Nota l…    31 Mujer Cana… Ingl… Univers…
    ##  3 1629       4618  Correo electrónico  Familia    42 Mujer Aust… Ingl… Univers…
    ##  4 101        275   Nota/aviso          Nota l…    49 Homb… Irla… Ingl… Primaria
    ##  5 101        275   Nota/aviso          Nota l…    49 Homb… Irla… Ingl… Primaria
    ##  6 231        637   Correo electrónico  Cambio…    28 Homb… Rein… Ingl… Univers…
    ##  7 356        983   Correo electrónico  Cambio…    63 Mujer Rein… Ingl… Univers…
    ##  8 210        576   Nota/aviso          Nota l…    31 Mujer Cana… Ingl… Univers…
    ##  9 2278       6385  Correo electrónico  Cambio…    22 Mujer Core… Ingl… Univers…
    ## 10 210        576   Nota/aviso          Nota l…    31 Mujer Cana… Ingl… Univers…
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
read_excel("Excels/VANENG.xlsx")
```

    ## # A tibble: 1 × 19
    ##   Estudiante Tarea `Tipología textual` Tema     Edad Sexo  País   L1    Estudios
    ##   <chr>      <chr> <chr>               <chr>   <dbl> <chr> <chr>  <chr> <chr>   
    ## 1 201        554   Correo electrónico  Familia    32 Mujer Franc… Ingl… Primaria
    ## # ℹ 10 more variables: `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>,
    ## #   `Información adicional 1` <lgl>, `Contexto a la derecha` <chr>

``` r
FRENG <- list.files(path = "Excels", pattern = "*.xlsx*", all.files = TRUE, full.names = TRUE, recursive = FALSE)
A1 <- FRENG %>%
    set_names() %>%
    map_dfr(read_excel, .id = "Source")
A1
```

    ## # A tibble: 418 × 20
    ##    Source     Estudiante Tarea `Tipología textual` Tema   Edad Sexo  País  L1   
    ##    <chr>      <chr>      <chr> <chr>               <chr> <dbl> <chr> <chr> <chr>
    ##  1 Excels/A1… 774        2154  Correo electrónico  Camb…    22 Mujer Fran… Fran…
    ##  2 Excels/A1… 1239       3493  Correo electrónico  Camb…    58 Homb… Fran… Fran…
    ##  3 Excels/A1… 1974       5564  Correo electrónico  Fami…    45 Homb… Fran… Fran…
    ##  4 Excels/A1… 776        2160  Correo electrónico  Camb…    65 Mujer Fran… Fran…
    ##  5 Excels/A1… 2002       5639  Correo electrónico  Camb…    64 Homb… Fran… Fran…
    ##  6 Excels/A1… 2002       5639  Correo electrónico  Camb…    64 Homb… Fran… Fran…
    ##  7 Excels/A1… 380        1053  Nota/aviso          Nota…    37 Mujer Fran… Fran…
    ##  8 Excels/A1… 779        2169  Correo electrónico  Camb…    52 Mujer Fran… Fran…
    ##  9 Excels/A1… 775        2158  Nota/aviso          Nota…    27 Mujer Fran… Fran…
    ## 10 Excels/A1… 781        2177  Correo electrónico  Fami…    36 Mujer Fran… Fran…
    ## # ℹ 408 more rows
    ## # ℹ 11 more variables: Estudios <chr>,
    ## #   `Edad de inicio en el estudio del español` <dbl>,
    ## #   `Número de meses estudiando español` <dbl>,
    ## #   `Contactos personales en países de habla española` <chr>,
    ## #   `Contexto a la izquierda` <chr>, `Elemento gramatical 1` <chr>,
    ## #   `Etiqueta 1` <chr>, `Lema 1` <chr>, `Palabra ortográfica 1` <lgl>, …

``` r
write.csv(A1, "A1.csv", row.names = FALSE)
```

I am starting by translating all of the columns into English for ease of
understanding and access for learners who are not proficient in Spanish.

``` r
A1IR <- rename(A1, Student = Estudiante,
       Task = Tarea,
       TypeText = `Tipología textual`,
       Theme = Tema,
       Age = Edad,
       Gender = Sexo,
       Country = País,
       Studies = Estudios,
       AgeStart = `Edad de inicio en el estudio del español`,
       Months = `Número de meses estudiando español`,
       Contacts = `Contactos personales en países de habla española`,
       ContextL = `Contexto a la izquierda`,
       GramElem1 = `Elemento gramatical 1`,
       Tag1 = `Etiqueta 1`,
       Lemma1 = `Lema 1`,
       OrthoWord1 = `Palabra ortográfica 1`,
       ExInfo1 = `Información adicional 1`,
       ContextR = `Contexto a la derecha`)
```

# Tidying

The first thing I want to do with my datasets is see if there are any
duplicate productions from the same participant within the different
conjugations of “voy”.

``` r
A1IR
```

    ## # A tibble: 418 × 20
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ## # ℹ 408 more rows
    ## # ℹ 10 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>,
    ## #   OrthoWord1 <lgl>, ExInfo1 <lgl>, ContextR <chr>

``` r
unique(A1IR$Student)
```

    ##  [1] "774"  "1239" "1974" "776"  "2002" "380"  "779"  "775"  "781"  "840" 
    ## [11] "2042" "480"  "838"  "1972" "390"  "777"  "232"  "1075" "1975" "636" 
    ## [21] "371"  "794"  "1270" "483"  "778"  "722"  "796"  "372"  "2096" "793" 
    ## [31] "791"  "1406" "831"  "1463" "2129" "638"  "797"  "1988" "326"  "841" 
    ## [41] "836"  "829"  "257"  "827"  "792"  "2039" "1986" "1973" "1681" "201" 
    ## [51] "55"   "1622" "101"  "1630" "53"   "1333" "59"   "2740" "1728" "140" 
    ## [61] "54"   "138"  "98"   "96"   "61"   "57"   "60"   "210"  "58"   "1682"
    ## [71] "1680" "56"   "356"  "231"  "95"   "1629" "2278" "614"  "1631" "2741"
    ## [81] "1616" "1632" "770"

``` r
count(A1IR,Student)
```

    ## # A tibble: 83 × 2
    ##    Student     n
    ##    <chr>   <int>
    ##  1 101        10
    ##  2 1075        1
    ##  3 1239        7
    ##  4 1270        9
    ##  5 1333        4
    ##  6 138         4
    ##  7 140         3
    ##  8 1406        3
    ##  9 1463        6
    ## 10 1616        4
    ## # ℹ 73 more rows

``` r
A1IRNEW <- A1IR %>%
  group_by(Student)
A1IRNEW
```

    ## # A tibble: 418 × 20
    ## # Groups:   Student [83]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ## # ℹ 408 more rows
    ## # ℹ 10 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>,
    ## #   OrthoWord1 <lgl>, ExInfo1 <lgl>, ContextR <chr>

``` r
A1IRNEW %>% 
  filter(L1 == "Francés")
```

    ## # A tibble: 282 × 20
    ## # Groups:   Student [48]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ## # ℹ 272 more rows
    ## # ℹ 10 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>,
    ## #   OrthoWord1 <lgl>, ExInfo1 <lgl>, ContextR <chr>

``` r
A1IRNEW %>% 
  filter(L1 == "Inglés")
```

    ## # A tibble: 136 × 20
    ## # Groups:   Student [35]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/IRENG… 1681    4772  Nota/av… Nota…    63 Hombre Estado… Ingl… Univer…
    ##  2 Excels/IRENG… 201     552   Correo … Camb…    32 Mujer  Francia Ingl… Primar…
    ##  3 Excels/IRENG… 55      148   Correo … Camb…    52 Mujer  Irlanda Ingl… Otros  
    ##  4 Excels/IRENG… 1622    4601  Nota/av… Nota…    15 Hombre Estado… Ingl… Primar…
    ##  5 Excels/IRENG… 101     275   Nota/av… Nota…    49 Hombre Irlanda Ingl… Primar…
    ##  6 Excels/IRENG… 1630    4619  Correo … Camb…    23 Hombre Austra… Ingl… Univer…
    ##  7 Excels/IRENG… 53      142   Correo … Camb…    57 Hombre Irlanda Ingl… Otros  
    ##  8 Excels/IRENG… 1333    3775  Nota/av… Nota…    25 Mujer  China   Ingl… Univer…
    ##  9 Excels/IRENG… 59      161   Nota/av… Nota…    50 Hombre Irlanda Ingl… Otros  
    ## 10 Excels/IRENG… 101     275   Nota/av… Nota…    49 Hombre Irlanda Ingl… Primar…
    ## # ℹ 126 more rows
    ## # ℹ 10 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>,
    ## #   OrthoWord1 <lgl>, ExInfo1 <lgl>, ContextR <chr>

Based on the information above, we see that there are a total of 48
students with French as their L1, with each participant having a
different number of total productions.As for English, there are 35 total
students with English as their L1. In total, we have 83 total students
in this dataset.

The second thing I am going to do is remove any columns I deem
unnecessary for my analyses. These include the 17th and 18th columns, as
they have no data.

``` r
A1 <- subset(A1IRNEW, select = -c(OrthoWord1, ExInfo1))
A1
```

    ## # A tibble: 418 × 18
    ## # Groups:   Student [83]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ## # ℹ 408 more rows
    ## # ℹ 8 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

# Basic Statistics

Now, I am going to do some basic statistical inquiries, just to see the
range of ages, as well as what country they are from, how old they were
when they started (to calculate how long they have been learning
Spanish), etc.

``` r
count(A1, Contacts)
```

    ## # A tibble: 83 × 3
    ## # Groups:   Student [83]
    ##    Student Contacts       n
    ##    <chr>   <chr>      <int>
    ##  1 101     No            10
    ##  2 1075    No             1
    ##  3 1239    No             7
    ##  4 1270    Familiares     9
    ##  5 1333    Otros          4
    ##  6 138     No             4
    ##  7 140     Amigos         3
    ##  8 1406    Otros          3
    ##  9 1463    Otros          6
    ## 10 1616    No             4
    ## # ℹ 73 more rows

``` r
unique(A1$Contacts)
```

    ## [1] "No"                "Amigos"            "Amigos&Familiares"
    ## [4] "Familiares"        "Otros"

``` r
A1 %>% 
  filter(Contacts == "No")
```

    ## # A tibble: 244 × 18
    ## # Groups:   Student [46]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  8 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 840     2344  Correo … Fami…    61 Mujer  Francia Fran… Univer…
    ## 10 Excels/A1IR.… 2042    5752  Nota/av… Nota…    71 Hombre Francia Fran… Otros  
    ## # ℹ 234 more rows
    ## # ℹ 8 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Amigos")
```

    ## # A tibble: 86 × 18
    ## # Groups:   Student [19]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  2 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ##  3 Excels/A1IR.… 777     2163  Correo … Camb…    36 Hombre Francia Fran… Univer…
    ##  4 Excels/A1IR.… 777     2164  Nota/av… Nota…    36 Hombre Francia Fran… Univer…
    ##  5 Excels/A1IR.… 636     1766  Correo … Camb…    60 Mujer  Francia Fran… Secund…
    ##  6 Excels/A1IR.… 372     1029  Correo … Camb…    19 Mujer  Líbano  Fran… Univer…
    ##  7 Excels/A1IR.… 775     2157  Correo … Camb…    27 Mujer  Francia Fran… Otros  
    ##  8 Excels/A1IR.… 636     1767  Nota/av… Nota…    60 Mujer  Francia Fran… Secund…
    ##  9 Excels/A1IR.… 2129    5993  Nota/av… Nota…    23 Mujer  Costa … Fran… Secund…
    ## 10 Excels/A1IR.… 638     1773  Nota/av… Nota…    62 Hombre Francia Fran… Univer…
    ## # ℹ 76 more rows
    ## # ℹ 8 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Amigos&Familiares")
```

    ## # A tibble: 35 × 18
    ## # Groups:   Student [8]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 371     1027  Nota/av… Nota…    25 Mujer  Líbano  Fran… Univer…
    ##  2 Excels/A1IR.… 794     2214  Correo … Camb…    62 Mujer  Francia Fran… Univer…
    ##  3 Excels/A1IR.… 796     2220  Correo … Camb…    67 Hombre Francia Fran… Univer…
    ##  4 Excels/A1IR.… 371     1028  Correo … Fami…    25 Mujer  Líbano  Fran… Univer…
    ##  5 Excels/A1IR.… 371     1027  Nota/av… Nota…    25 Mujer  Líbano  Fran… Univer…
    ##  6 Excels/A1IR.… 792     2208  Correo … Camb…    26 Hombre Suiza   Fran… Otros  
    ##  7 Excels/A1IR.… 371     1026  Correo … Camb…    25 Mujer  Líbano  Fran… Univer…
    ##  8 Excels/A1IR.… 792     2208  Correo … Camb…    26 Hombre Suiza   Fran… Otros  
    ##  9 Excels/A1IR.… 1986    5597  Correo … Camb…    43 Mujer  Marrue… Fran… Univer…
    ## 10 Excels/A1IR.… 1973    5561  Correo … Fami…    55 Hombre Francia Fran… Secund…
    ## # ℹ 25 more rows
    ## # ℹ 8 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Familiares")
```

    ## # A tibble: 27 × 18
    ## # Groups:   Student [5]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 1270    3587  Nota/av… Nota…    33 Mujer  Francia Fran… Univer…
    ##  2 Excels/A1IR.… 793     2211  Correo … Camb…    61 Mujer  Francia Fran… Univer…
    ##  3 Excels/A1IR.… 791     2205  Correo … Camb…    57 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 791     2207  Correo … Fami…    57 Hombre Francia Fran… Secund…
    ##  5 Excels/A1IR.… 1270    3586  Correo … Camb…    33 Mujer  Francia Fran… Univer…
    ##  6 Excels/A1IR.… 1270    3586  Correo … Camb…    33 Mujer  Francia Fran… Univer…
    ##  7 Excels/A1IR.… 1270    3587  Nota/av… Nota…    33 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 836     2330  Correo … Camb…    44 Mujer  Francia Fran… Univer…
    ##  9 Excels/A1IR.… 827     2308  Correo … Fami…    64 Mujer  Francia Fran… Univer…
    ## 10 Excels/A1IR.… 827     2308  Correo … Fami…    64 Mujer  Francia Fran… Univer…
    ## # ℹ 17 more rows
    ## # ℹ 8 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Otros")
```

    ## # A tibble: 26 × 18
    ## # Groups:   Student [5]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 1406    3983  Nota/av… Nota…    37 Mujer  Guinea  Fran… Univer…
    ##  2 Excels/A1IR.… 1463    4138  Correo … Camb…    37 Mujer  Guinea  Fran… Primar…
    ##  3 Excels/A1IR.… 1463    4139  Nota/av… Nota…    37 Mujer  Guinea  Fran… Primar…
    ##  4 Excels/A1IR.… 1463    4138  Correo … Camb…    37 Mujer  Guinea  Fran… Primar…
    ##  5 Excels/A1IR.… 1406    3982  Correo … Camb…    37 Mujer  Guinea  Fran… Univer…
    ##  6 Excels/A1IR.… 257     711   Correo … Camb…    18 Mujer  Francia Fran… Secund…
    ##  7 Excels/A1VA.… 1406    3982  Correo … Camb…    37 Mujer  Guinea  Fran… Univer…
    ##  8 Excels/A1VA.… 257     711   Correo … Camb…    18 Mujer  Francia Fran… Secund…
    ##  9 Excels/A1VOY… 1463    4138  Correo … Camb…    37 Mujer  Guinea  Fran… Primar…
    ## 10 Excels/A1VOY… 1463    4139  Nota/av… Nota…    37 Mujer  Guinea  Fran… Primar…
    ## # ℹ 16 more rows
    ## # ℹ 8 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

The contacts column is meant for the students to relay whether they have
any contacts who are Spanish speakers. There were a total of five
distinct answers given from the 48 L1 French students:

1.  No contacts
2.  “Amigos” -\> Friends
3.  “Amigos&Familiares” -\> Friends and Family
4.  “Familiares” -\> Family
5.  “Otros” -\> Others

The data was filtered five times for each category of answers to how
many tokens were accredited to each category of answers. The results
show that the majority of students with L1 French had no contacts who
are Spanish speakers (total of 25 students, 52%). The category with the
smallest students is the “Friends” category, with a total of 10 students
stating they have family members who are Spanish speakers, adding up to
approximately 10% of the students in the data.

As for students with an L1 of English, there were a total of four
distinct answers given from the 35 students:

1.  No contacts
2.  “Amigos” -\> Friends
3.  “Amigos&Familiares” -\> Friends and Family
4.  “Otros” -\> Others

The results show that the majority of students with L1 English had no
contacts who are Spanish speakers (total of 21 students, 60%). The
category with the smallest students is the “Friends and Family”
category, with a total of 2 students stating they have friends and
family members who are Spanish speakers, adding up to approximately 5.7%
of the students in the data.

``` r
unique(A1$Theme)
```

    ## [1] "Cambio trabajo"    "Familia"           "Nota llegar tarde"

The CAES corpus is comprised of all written texts from individuals who
are L2 learners of Spanish. For these particular datasets, there were
three distinct topics that the students wrote about: Job change, Family,
and Note of late arrival.

``` r
unique(A1$TypeText)
```

    ## [1] "Correo electrónico" "Nota/aviso"

There are two types of written data by the students in each dataset:

1.  “Correo electronico” -\> E-mail
2.  “Nota/aviso” -\> Note/Warning

``` r
count(A1, Country)
```

    ## # A tibble: 83 × 3
    ## # Groups:   Student [83]
    ##    Student Country            n
    ##    <chr>   <chr>          <int>
    ##  1 101     Irlanda           10
    ##  2 1075    Francia            1
    ##  3 1239    Francia            7
    ##  4 1270    Francia            9
    ##  5 1333    China              4
    ##  6 138     Corea del Sur      4
    ##  7 140     Estados Unidos     3
    ##  8 1406    Guinea             3
    ##  9 1463    Guinea             6
    ## 10 1616    Estados Unidos     4
    ## # ℹ 73 more rows

``` r
unique(A1$Country)
```

    ##  [1] "Francia"         "Bélgica"         "Mónaco"          "Líbano"         
    ##  [5] "Marruecos"       "Colombia"        "Guinea"          "Costa de Marfil"
    ##  [9] "Suiza"           "Estados Unidos"  "Irlanda"         "Australia"      
    ## [13] "China"           "Japón"           "Reino Unido"     "Corea del Sur"  
    ## [17] "Canadá"          "Filipinas"

``` r
count(A1, Studies)
```

    ## # A tibble: 83 × 3
    ## # Groups:   Student [83]
    ##    Student Studies         n
    ##    <chr>   <chr>       <int>
    ##  1 101     Primaria       10
    ##  2 1075    Universidad     1
    ##  3 1239    Universidad     7
    ##  4 1270    Universidad     9
    ##  5 1333    Universidad     4
    ##  6 138     Otros           4
    ##  7 140     Universidad     3
    ##  8 1406    Universidad     3
    ##  9 1463    Primaria        6
    ## 10 1616    Universidad     4
    ## # ℹ 73 more rows

``` r
mean(A1$Age)
```

    ## [1] 44.64354

``` r
A1AGE <- A1 %>% 
  group_by(Age) %>% 
  summarise(count = n())
  print(A1AGE)
```

    ## # A tibble: 38 × 2
    ##      Age count
    ##    <dbl> <int>
    ##  1    15     8
    ##  2    16     9
    ##  3    18     2
    ##  4    19     1
    ##  5    22    11
    ##  6    23    15
    ##  7    24     2
    ##  8    25    11
    ##  9    26    16
    ## 10    27    17
    ## # ℹ 28 more rows

As can be seen above, it appears that ages in the dataset range from 15
to 71 years old. Not only that, but the age group with the most amount
of students is the 61 year-olds who have 13 total individuals. The age
group with the least amount of students is the 15, 18, 19, 24, and 44
year-olds who only had one individual per age.

# Picking Out the Prescriptive Output

``` r
CA1 <- A1 %>%
    mutate(First2 = sub("^([[:alpha:]]+ [[:alpha:]]+).*", "\\1", ContextR))


# If needed, save the modified data frame to a new object or overwrite the existing one
A1 <- CA1
A1
```

    ## # A tibble: 418 × 19
    ## # Groups:   Student [83]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ## # ℹ 408 more rows
    ## # ℹ 9 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>,
    ## #   First2 <chr>

# Statistical Analyses

``` r
A1 <- A1 %>% 
  mutate(Correct = ifelse(grepl("^a.*r$", First2), 1, 0))

print(A1)
```

    ## # A tibble: 418 × 20
    ## # Groups:   Student [83]
    ##    Source        Student Task  TypeText Theme   Age Gender Country L1    Studies
    ##    <chr>         <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 Excels/A1IR.… 774     2154  Correo … Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 Excels/A1IR.… 1239    3493  Correo … Camb…    58 Hombre Francia Fran… Univer…
    ##  3 Excels/A1IR.… 1974    5564  Correo … Fami…    45 Hombre Francia Fran… Secund…
    ##  4 Excels/A1IR.… 776     2160  Correo … Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  6 Excels/A1IR.… 2002    5639  Correo … Camb…    64 Hombre Francia Fran… Otros  
    ##  7 Excels/A1IR.… 380     1053  Nota/av… Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 Excels/A1IR.… 779     2169  Correo … Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 Excels/A1IR.… 775     2158  Nota/av… Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 Excels/A1IR.… 781     2177  Correo … Fami…    36 Mujer  Francia Fran… Otros  
    ## # ℹ 408 more rows
    ## # ℹ 10 more variables: AgeStart <dbl>, Months <dbl>, Contacts <chr>,
    ## #   ContextL <chr>, GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>,
    ## #   First2 <chr>, Correct <dbl>

``` r
summary_df <- A1 %>%
    group_by(Age, Gender, Country, L1) %>%
    summarise(CorrectAnswers = sum(Correct))
```

    ## `summarise()` has grouped output by 'Age', 'Gender', 'Country'. You can
    ## override using the `.groups` argument.

``` r
print(summary_df)
```

    ## # A tibble: 76 × 5
    ## # Groups:   Age, Gender, Country [76]
    ##      Age Gender Country        L1      CorrectAnswers
    ##    <dbl> <chr>  <chr>          <chr>            <dbl>
    ##  1    15 Hombre Estados Unidos Inglés               1
    ##  2    15 Hombre Francia        Francés              0
    ##  3    15 Mujer  Irlanda        Inglés               0
    ##  4    16 Hombre Japón          Inglés               1
    ##  5    16 Hombre Mónaco         Francés              4
    ##  6    16 Mujer  Japón          Inglés               0
    ##  7    18 Mujer  Francia        Francés              2
    ##  8    19 Mujer  Líbano         Francés              0
    ##  9    22 Mujer  Corea del Sur  Inglés               4
    ## 10    22 Mujer  Francia        Francés              2
    ## # ℹ 66 more rows

``` r
model1 <- glm(Correct ~ Age + AgeStart + Gender + Country + Months + Studies + Contacts + L1, data = A1, family = binomial)

summary(model1)
```

    ## 
    ## Call:
    ## glm(formula = Correct ~ Age + AgeStart + Gender + Country + Months + 
    ##     Studies + Contacts + L1, family = binomial, data = A1)
    ## 
    ## Coefficients:
    ##                             Estimate Std. Error z value Pr(>|z|)   
    ## (Intercept)                2.198e-01  1.715e+00   0.128  0.89802   
    ## Age                       -2.215e-02  1.076e-02  -2.059  0.03949 * 
    ## AgeStart                   1.778e-02  6.518e-03   2.728  0.00638 **
    ## GenderMujer                1.441e-01  3.227e-01   0.447  0.65511   
    ## CountryBélgica            -5.554e-01  1.717e+00  -0.323  0.74636   
    ## CountryCanadá              3.440e+00  1.515e+00   2.270  0.02321 * 
    ## CountryChina               1.340e+00  1.743e+00   0.769  0.44205   
    ## CountryColombia           -1.759e+01  2.797e+03  -0.006  0.99498   
    ## CountryCorea del Sur       2.508e+00  1.332e+00   1.883  0.05964 . 
    ## CountryCosta de Marfil     1.727e+01  1.399e+03   0.012  0.99015   
    ## CountryEstados Unidos     -1.745e-01  1.410e+00  -0.124  0.90151   
    ## CountryFilipinas          -1.622e+01  3.956e+03  -0.004  0.99673   
    ## CountryFrancia            -5.788e-01  1.633e+00  -0.354  0.72297   
    ## CountryGuinea             -1.912e+01  1.309e+03  -0.015  0.98834   
    ## CountryIrlanda             2.972e-01  1.199e+00   0.248  0.80428   
    ## CountryJapón               2.085e+00  1.815e+00   1.148  0.25079   
    ## CountryLíbano             -1.461e+00  1.771e+00  -0.825  0.40959   
    ## CountryMarruecos          -1.776e+01  1.852e+03  -0.010  0.99235   
    ## CountryMónaco              2.319e+00  2.080e+00   1.115  0.26497   
    ## CountryReino Unido        -1.618e+01  1.315e+03  -0.012  0.99019   
    ## CountrySuiza              -1.705e+01  1.978e+03  -0.009  0.99312   
    ## Months                    -2.826e-02  1.778e-02  -1.590  0.11186   
    ## StudiesPrimaria            1.057e+00  5.368e-01   1.970  0.04884 * 
    ## StudiesSecundaria          8.551e-02  5.343e-01   0.160  0.87285   
    ## StudiesUniversidad         7.732e-01  3.493e-01   2.214  0.02686 * 
    ## ContactsAmigos&Familiares -5.927e-01  7.272e-01  -0.815  0.41502   
    ## ContactsFamiliares        -9.167e-01  5.474e-01  -1.675  0.09400 . 
    ## ContactsNo                 8.068e-02  3.373e-01   0.239  0.81096   
    ## ContactsOtros              1.040e+00  8.076e-01   1.287  0.19794   
    ## L1Inglés                  -2.150e+00  1.221e+00  -1.760  0.07834 . 
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 534.41  on 417  degrees of freedom
    ## Residual deviance: 426.47  on 388  degrees of freedom
    ## AIC: 486.47
    ## 
    ## Number of Fisher Scoring iterations: 16

## Analysis - Model 1

Significant factors: Age, AgeStart (most), Being from Canada, Starting
in Primary School, Starting in Uni (more than Primary)

Almost Significant: Being from South Korea (crazy!), having family
members who speak Spanish, and having English as an L1.

# Visualizations

``` r
ggplot(model1, aes(AgeStart)) +
  geom_bar(color = "red", fill = "black", size = .5) +
  labs(title = "Bar Plot of Age Start vs. Correctness", x = "Age", y = "Correctness") + 
  theme_minimal()
```

    ## Warning: Using `size` aesthetic for lines was deprecated in ggplot2 3.4.0.
    ## ℹ Please use `linewidth` instead.
    ## This warning is displayed once every 8 hours.
    ## Call `lifecycle::last_lifecycle_warnings()` to see where this warning was
    ## generated.

![](L1FR-L2ES-Effect_files/figure-gfm/plot%201-1.png)<!-- --> Plot 1
shows that the largest number of correctness came from those who started
learning Spanish from birth.

``` r
ggplot(model1, aes(Age)) +
  geom_bar(color = "red", fill = "black", size = .5) +
  labs(title = "Bar Plot of Age vs. Correctness", x = "Age", y = "Correctness") + 
  theme_minimal()
```

![](L1FR-L2ES-Effect_files/figure-gfm/plot%202-1.png)<!-- --> Plot 2
shows that those who were around 50 years old had the most correct
answers.

``` r
ggplot(model1, aes(Country)) +
  geom_bar(width = 0.5, color = "red", fill = "black", size = .5) +
  labs(title = "Bar Plot of Country vs. Correctness", x = "Country", y = "Correctness") +
  theme(axis.text.x = element_text(angle = 90)) 
```

![](L1FR-L2ES-Effect_files/figure-gfm/plot%203-1.png)<!-- --> Plot 3
shows that those who are from France had the most correct productions of
the periphrastic future in French. Although interesting, it was Canada
that had a significant effect on the correctness according to the
logistic regression.

``` r
ggplot(model1, aes(Studies)) +
  geom_bar(width = 0.5, color = "red", fill = "black", size = .5) +
  labs(title = "Bar Plot of Where Students Started Studying Spanish vs. Correctness", x = "When Started", y = "Correctness") +
  theme_minimal()
```

![](L1FR-L2ES-Effect_files/figure-gfm/plot%204-1.png)<!-- --> Plot 4
shows that those who started learning Spanish at their university had
the most correct answers. The regression analysis shows that both those
who started in primary school and at their university had the most
significant effect on their correctness, with university learners having
slightly more significance (about 0.02 more significance).

``` r
ggplot(model1, aes(L1)) +
  geom_bar(width = 0.5, color = "red", fill = "black", size = .5) +
  labs(title = "Bar Plot of L1 vs. Correctness", x = "L1", y = "Correctness") +
  theme_minimal()
```

![](L1FR-L2ES-Effect_files/figure-gfm/plot%205-1.png)<!-- --> Plot 5
shows that those whose L1 is French had more correct answers. This
actually answers my main research question, which was whether having
French as an L1 allows one to have more correct productions than English
speakers. According to the regression, having English as an L1 was
*almost* significant. The negative estimate for L1 English means that
having an L1 of English reduced the production of correct periphrastic
future sentences.

``` r
ggplot(model1, aes(Contacts)) +
  geom_bar(width = 0.5, color = "red", fill = "black", size = .5) +
  labs(title = "Bar Plot of Contacts Who Speak Spanish vs. Correctness", x = "Contacts", y = "Correctness") +
  theme_minimal()
```

![](L1FR-L2ES-Effect_files/figure-gfm/plot%206-1.png)<!-- --> Plot 6
shows that participants with no contact who speaks Spanish had the most
correct periphrastic future productions. According to the regression
analysis, those with family members who speak Spanish almost had a
significant effect on correctness. Its negative estimate means that
having family members who speak Spanish reduces the correct productions,
which is interesting, considering that should actually be more helpful.
But with consideration, they may have a different, less prescriptive
production of Spanish which may in turn confuse the participant.

# Conclusion

Based on the information provided above, both research questions were
answered. First of all, having French as an L1 *does* in fact help
participants produce the periphrastic future better than those who have
English as an L1. As for the second question, the factors that affect
periphrastic future production in L2 Spanish are the age when they
started learning, their current age, whether or not they have any
contacts who speak Spanish, what country they are from, what their L1
is, and what school they were in when they learned/started learning
Spanish. The age when they started learning proved to be the most
significant factor based on the logistic regression model.

``` r
library(sessioninfo)
```

    ## Warning: package 'sessioninfo' was built under R version 4.4.2

``` r
session_info()
```

    ## ─ Session info ───────────────────────────────────────────────────────────────
    ##  setting  value
    ##  version  R version 4.4.1 (2024-06-14 ucrt)
    ##  os       Windows 11 x64 (build 22631)
    ##  system   x86_64, mingw32
    ##  ui       RTerm
    ##  language (EN)
    ##  collate  English_United States.utf8
    ##  ctype    English_United States.utf8
    ##  tz       America/New_York
    ##  date     2024-12-02
    ##  pandoc   3.2 @ C:/Program Files/RStudio/resources/app/bin/quarto/bin/tools/ (via rmarkdown)
    ## 
    ## ─ Packages ───────────────────────────────────────────────────────────────────
    ##  package     * version date (UTC) lib source
    ##  cellranger    1.1.0   2016-07-27 [1] CRAN (R 4.4.1)
    ##  cli           3.6.3   2024-06-21 [1] CRAN (R 4.4.1)
    ##  colorspace    2.1-1   2024-07-26 [1] CRAN (R 4.4.1)
    ##  crayon        1.5.3   2024-06-20 [1] CRAN (R 4.4.1)
    ##  digest        0.6.37  2024-08-19 [1] CRAN (R 4.4.1)
    ##  dplyr       * 1.1.4   2023-11-17 [1] CRAN (R 4.4.1)
    ##  evaluate      0.24.0  2024-06-10 [1] CRAN (R 4.4.1)
    ##  fansi         1.0.6   2023-12-08 [1] CRAN (R 4.4.1)
    ##  farver        2.1.2   2024-05-13 [1] CRAN (R 4.4.1)
    ##  fastmap       1.2.0   2024-05-15 [1] CRAN (R 4.4.1)
    ##  forcats     * 1.0.0   2023-01-29 [1] CRAN (R 4.4.1)
    ##  generics      0.1.3   2022-07-05 [1] CRAN (R 4.4.1)
    ##  ggplot2     * 3.5.1   2024-04-23 [1] CRAN (R 4.4.1)
    ##  glue          1.7.0   2024-01-09 [1] CRAN (R 4.4.1)
    ##  gtable        0.3.5   2024-04-22 [1] CRAN (R 4.4.1)
    ##  highr         0.11    2024-05-26 [1] CRAN (R 4.4.1)
    ##  hms           1.1.3   2023-03-21 [1] CRAN (R 4.4.1)
    ##  htmltools     0.5.8.1 2024-04-04 [1] CRAN (R 4.4.1)
    ##  knitr         1.48    2024-07-07 [1] CRAN (R 4.4.1)
    ##  labeling      0.4.3   2023-08-29 [1] CRAN (R 4.4.0)
    ##  lifecycle     1.0.4   2023-11-07 [1] CRAN (R 4.4.1)
    ##  lubridate   * 1.9.3   2023-09-27 [1] CRAN (R 4.4.1)
    ##  magrittr      2.0.3   2022-03-30 [1] CRAN (R 4.4.1)
    ##  munsell       0.5.1   2024-04-01 [1] CRAN (R 4.4.1)
    ##  pillar        1.9.0   2023-03-22 [1] CRAN (R 4.4.1)
    ##  pkgconfig     2.0.3   2019-09-22 [1] CRAN (R 4.4.1)
    ##  purrr       * 1.0.2   2023-08-10 [1] CRAN (R 4.4.1)
    ##  R6            2.5.1   2021-08-19 [1] CRAN (R 4.4.1)
    ##  readr       * 2.1.5   2024-01-10 [1] CRAN (R 4.4.1)
    ##  readxl      * 1.4.3   2023-07-06 [1] CRAN (R 4.4.2)
    ##  rlang         1.1.4   2024-06-04 [1] CRAN (R 4.4.1)
    ##  rmarkdown     2.28    2024-08-17 [1] CRAN (R 4.4.1)
    ##  rstudioapi    0.16.0  2024-03-24 [1] CRAN (R 4.4.1)
    ##  scales        1.3.0   2023-11-28 [1] CRAN (R 4.4.1)
    ##  sessioninfo * 1.2.2   2021-12-06 [1] CRAN (R 4.4.2)
    ##  stringi       1.8.4   2024-05-06 [1] CRAN (R 4.4.0)
    ##  stringr     * 1.5.1   2023-11-14 [1] CRAN (R 4.4.1)
    ##  tibble      * 3.2.1   2023-03-20 [1] CRAN (R 4.4.1)
    ##  tidyr       * 1.3.1   2024-01-24 [1] CRAN (R 4.4.1)
    ##  tidyselect    1.2.1   2024-03-11 [1] CRAN (R 4.4.1)
    ##  tidyverse   * 2.0.0   2023-02-22 [1] CRAN (R 4.4.1)
    ##  timechange    0.3.0   2024-01-18 [1] CRAN (R 4.4.1)
    ##  tzdb          0.4.0   2023-05-12 [1] CRAN (R 4.4.1)
    ##  utf8          1.2.4   2023-10-22 [1] CRAN (R 4.4.1)
    ##  vctrs         0.6.5   2023-12-01 [1] CRAN (R 4.4.1)
    ##  withr         3.0.1   2024-07-31 [1] CRAN (R 4.4.1)
    ##  xfun          0.47    2024-08-17 [1] CRAN (R 4.4.1)
    ##  yaml          2.3.10  2024-07-26 [1] CRAN (R 4.4.1)
    ## 
    ##  [1] C:/Users/vegam/AppData/Local/R/win-library/4.4
    ##  [2] C:/Program Files/R/R-4.4.1/library
    ## 
    ## ──────────────────────────────────────────────────────────────────────────────
