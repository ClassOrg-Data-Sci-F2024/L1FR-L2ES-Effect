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
read_excel("A1IR.xlsx")
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
read_excel("A1VOY.xlsx")
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
read_excel("A1VAS.xlsx")
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
read_excel("A1VA.xlsx")
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
read_excel("A1VAMOS.xlsx")
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
read_excel("IRENG.xlsx")
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
read_excel("VOYENG.xlsx")
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
read_excel("VASENG.xlsx")
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
read_excel("VAENG.xlsx")
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
read_excel("VAMOSENG.xlsx")
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
read_excel("VANENG.xlsx")
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
FRENG <- list.files(path = ".", pattern = "*.xlsx*", all.files = FALSE, full.names = FALSE, recursive = FALSE)
A1 <- FRENG %>%
    set_names() %>%
    map_dfr(read_excel, .id = "Source")
A1
```

    ## # A tibble: 418 × 20
    ##    Source    Estudiante Tarea `Tipología textual` Tema    Edad Sexo  País  L1   
    ##    <chr>     <chr>      <chr> <chr>               <chr>  <dbl> <chr> <chr> <chr>
    ##  1 A1IR.xlsx 774        2154  Correo electrónico  Cambi…    22 Mujer Fran… Fran…
    ##  2 A1IR.xlsx 1239       3493  Correo electrónico  Cambi…    58 Homb… Fran… Fran…
    ##  3 A1IR.xlsx 1974       5564  Correo electrónico  Famil…    45 Homb… Fran… Fran…
    ##  4 A1IR.xlsx 776        2160  Correo electrónico  Cambi…    65 Mujer Fran… Fran…
    ##  5 A1IR.xlsx 2002       5639  Correo electrónico  Cambi…    64 Homb… Fran… Fran…
    ##  6 A1IR.xlsx 2002       5639  Correo electrónico  Cambi…    64 Homb… Fran… Fran…
    ##  7 A1IR.xlsx 380        1053  Nota/aviso          Nota …    37 Mujer Fran… Fran…
    ##  8 A1IR.xlsx 779        2169  Correo electrónico  Cambi…    52 Mujer Fran… Fran…
    ##  9 A1IR.xlsx 775        2158  Nota/aviso          Nota …    27 Mujer Fran… Fran…
    ## 10 A1IR.xlsx 781        2177  Correo electrónico  Famil…    36 Mujer Fran… Fran…
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
    ##    Source    Student Task  TypeText     Theme   Age Gender Country L1    Studies
    ##    <chr>     <chr>   <chr> <chr>        <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 A1IR.xlsx 774     2154  Correo elec… Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 A1IR.xlsx 1239    3493  Correo elec… Camb…    58 Hombre Francia Fran… Univer…
    ##  3 A1IR.xlsx 1974    5564  Correo elec… Fami…    45 Hombre Francia Fran… Secund…
    ##  4 A1IR.xlsx 776     2160  Correo elec… Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 A1IR.xlsx 2002    5639  Correo elec… Camb…    64 Hombre Francia Fran… Otros  
    ##  6 A1IR.xlsx 2002    5639  Correo elec… Camb…    64 Hombre Francia Fran… Otros  
    ##  7 A1IR.xlsx 380     1053  Nota/aviso   Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 A1IR.xlsx 779     2169  Correo elec… Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 A1IR.xlsx 775     2158  Nota/aviso   Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 A1IR.xlsx 781     2177  Correo elec… Fami…    36 Mujer  Francia Fran… Otros  
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
    ##    Source    Student Task  TypeText     Theme   Age Gender Country L1    Studies
    ##    <chr>     <chr>   <chr> <chr>        <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 A1IR.xlsx 774     2154  Correo elec… Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 A1IR.xlsx 1239    3493  Correo elec… Camb…    58 Hombre Francia Fran… Univer…
    ##  3 A1IR.xlsx 1974    5564  Correo elec… Fami…    45 Hombre Francia Fran… Secund…
    ##  4 A1IR.xlsx 776     2160  Correo elec… Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 A1IR.xlsx 2002    5639  Correo elec… Camb…    64 Hombre Francia Fran… Otros  
    ##  6 A1IR.xlsx 2002    5639  Correo elec… Camb…    64 Hombre Francia Fran… Otros  
    ##  7 A1IR.xlsx 380     1053  Nota/aviso   Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 A1IR.xlsx 779     2169  Correo elec… Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 A1IR.xlsx 775     2158  Nota/aviso   Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 A1IR.xlsx 781     2177  Correo elec… Fami…    36 Mujer  Francia Fran… Otros  
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
    ##    Source    Student Task  TypeText     Theme   Age Gender Country L1    Studies
    ##    <chr>     <chr>   <chr> <chr>        <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 A1IR.xlsx 774     2154  Correo elec… Camb…    22 Mujer  Francia Fran… Otros  
    ##  2 A1IR.xlsx 1239    3493  Correo elec… Camb…    58 Hombre Francia Fran… Univer…
    ##  3 A1IR.xlsx 1974    5564  Correo elec… Fami…    45 Hombre Francia Fran… Secund…
    ##  4 A1IR.xlsx 776     2160  Correo elec… Camb…    65 Mujer  Francia Fran… Otros  
    ##  5 A1IR.xlsx 2002    5639  Correo elec… Camb…    64 Hombre Francia Fran… Otros  
    ##  6 A1IR.xlsx 2002    5639  Correo elec… Camb…    64 Hombre Francia Fran… Otros  
    ##  7 A1IR.xlsx 380     1053  Nota/aviso   Nota…    37 Mujer  Francia Fran… Univer…
    ##  8 A1IR.xlsx 779     2169  Correo elec… Camb…    52 Mujer  Francia Fran… Otros  
    ##  9 A1IR.xlsx 775     2158  Nota/aviso   Nota…    27 Mujer  Francia Fran… Otros  
    ## 10 A1IR.xlsx 781     2177  Correo elec… Fami…    36 Mujer  Francia Fran… Otros  
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
    ##    Source     Student Task  TypeText    Theme   Age Gender Country L1    Studies
    ##    <chr>      <chr>   <chr> <chr>       <chr> <dbl> <chr>  <chr>   <chr> <chr>  
    ##  1 IRENG.xlsx 1681    4772  Nota/aviso  Nota…    63 Hombre Estado… Ingl… Univer…
    ##  2 IRENG.xlsx 201     552   Correo ele… Camb…    32 Mujer  Francia Ingl… Primar…
    ##  3 IRENG.xlsx 55      148   Correo ele… Camb…    52 Mujer  Irlanda Ingl… Otros  
    ##  4 IRENG.xlsx 1622    4601  Nota/aviso  Nota…    15 Hombre Estado… Ingl… Primar…
    ##  5 IRENG.xlsx 101     275   Nota/aviso  Nota…    49 Hombre Irlanda Ingl… Primar…
    ##  6 IRENG.xlsx 1630    4619  Correo ele… Camb…    23 Hombre Austra… Ingl… Univer…
    ##  7 IRENG.xlsx 53      142   Correo ele… Camb…    57 Hombre Irlanda Ingl… Otros  
    ##  8 IRENG.xlsx 1333    3775  Nota/aviso  Nota…    25 Mujer  China   Ingl… Univer…
    ##  9 IRENG.xlsx 59      161   Nota/aviso  Nota…    50 Hombre Irlanda Ingl… Otros  
    ## 10 IRENG.xlsx 101     275   Nota/aviso  Nota…    49 Hombre Irlanda Ingl… Primar…
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
unnecessary for my analyses. These include the L1 column because they
are all French anyway, as well as the 17th and 18th columns, as they
have no data.

``` r
A1 <- subset(A1IRNEW, select = -c(L1, OrthoWord1, ExInfo1))
A1
```

    ## # A tibble: 418 × 17
    ## # Groups:   Student [83]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 774     2154  Correo e… Camb…    22 Mujer  Francia Otros         22
    ##  2 A1IR.xlsx 1239    3493  Correo e… Camb…    58 Hombre Francia Univer…       58
    ##  3 A1IR.xlsx 1974    5564  Correo e… Fami…    45 Hombre Francia Secund…       45
    ##  4 A1IR.xlsx 776     2160  Correo e… Camb…    65 Mujer  Francia Otros         64
    ##  5 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  6 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  7 A1IR.xlsx 380     1053  Nota/avi… Nota…    37 Mujer  Francia Univer…        5
    ##  8 A1IR.xlsx 779     2169  Correo e… Camb…    52 Mujer  Francia Otros          1
    ##  9 A1IR.xlsx 775     2158  Nota/avi… Nota…    27 Mujer  Francia Otros         20
    ## 10 A1IR.xlsx 781     2177  Correo e… Fami…    36 Mujer  Francia Otros         14
    ## # ℹ 408 more rows
    ## # ℹ 7 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

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

    ## # A tibble: 244 × 17
    ## # Groups:   Student [46]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 774     2154  Correo e… Camb…    22 Mujer  Francia Otros         22
    ##  2 A1IR.xlsx 1239    3493  Correo e… Camb…    58 Hombre Francia Univer…       58
    ##  3 A1IR.xlsx 1974    5564  Correo e… Fami…    45 Hombre Francia Secund…       45
    ##  4 A1IR.xlsx 776     2160  Correo e… Camb…    65 Mujer  Francia Otros         64
    ##  5 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  6 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  7 A1IR.xlsx 779     2169  Correo e… Camb…    52 Mujer  Francia Otros          1
    ##  8 A1IR.xlsx 781     2177  Correo e… Fami…    36 Mujer  Francia Otros         14
    ##  9 A1IR.xlsx 840     2344  Correo e… Fami…    61 Mujer  Francia Univer…       60
    ## 10 A1IR.xlsx 2042    5752  Nota/avi… Nota…    71 Hombre Francia Otros         13
    ## # ℹ 234 more rows
    ## # ℹ 7 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Amigos")
```

    ## # A tibble: 86 × 17
    ## # Groups:   Student [19]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 380     1053  Nota/avi… Nota…    37 Mujer  Francia Univer…        5
    ##  2 A1IR.xlsx 775     2158  Nota/avi… Nota…    27 Mujer  Francia Otros         20
    ##  3 A1IR.xlsx 777     2163  Correo e… Camb…    36 Hombre Francia Univer…       35
    ##  4 A1IR.xlsx 777     2164  Nota/avi… Nota…    36 Hombre Francia Univer…       35
    ##  5 A1IR.xlsx 636     1766  Correo e… Camb…    60 Mujer  Francia Secund…       58
    ##  6 A1IR.xlsx 372     1029  Correo e… Camb…    19 Mujer  Líbano  Univer…       18
    ##  7 A1IR.xlsx 775     2157  Correo e… Camb…    27 Mujer  Francia Otros         20
    ##  8 A1IR.xlsx 636     1767  Nota/avi… Nota…    60 Mujer  Francia Secund…       58
    ##  9 A1IR.xlsx 2129    5993  Nota/avi… Nota…    23 Mujer  Costa … Secund…       23
    ## 10 A1IR.xlsx 638     1773  Nota/avi… Nota…    62 Hombre Francia Univer…       60
    ## # ℹ 76 more rows
    ## # ℹ 7 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Amigos&Familiares")
```

    ## # A tibble: 35 × 17
    ## # Groups:   Student [8]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 371     1027  Nota/avi… Nota…    25 Mujer  Líbano  Univer…       24
    ##  2 A1IR.xlsx 794     2214  Correo e… Camb…    62 Mujer  Francia Univer…        1
    ##  3 A1IR.xlsx 796     2220  Correo e… Camb…    67 Hombre Francia Univer…       66
    ##  4 A1IR.xlsx 371     1028  Correo e… Fami…    25 Mujer  Líbano  Univer…       24
    ##  5 A1IR.xlsx 371     1027  Nota/avi… Nota…    25 Mujer  Líbano  Univer…       24
    ##  6 A1IR.xlsx 792     2208  Correo e… Camb…    26 Hombre Suiza   Otros         26
    ##  7 A1IR.xlsx 371     1026  Correo e… Camb…    25 Mujer  Líbano  Univer…       24
    ##  8 A1IR.xlsx 792     2208  Correo e… Camb…    26 Hombre Suiza   Otros         26
    ##  9 A1IR.xlsx 1986    5597  Correo e… Camb…    43 Mujer  Marrue… Univer…        1
    ## 10 A1IR.xlsx 1973    5561  Correo e… Fami…    55 Hombre Francia Secund…       55
    ## # ℹ 25 more rows
    ## # ℹ 7 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Familiares")
```

    ## # A tibble: 27 × 17
    ## # Groups:   Student [5]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 1270    3587  Nota/avi… Nota…    33 Mujer  Francia Univer…       33
    ##  2 A1IR.xlsx 793     2211  Correo e… Camb…    61 Mujer  Francia Univer…       60
    ##  3 A1IR.xlsx 791     2205  Correo e… Camb…    57 Hombre Francia Secund…       57
    ##  4 A1IR.xlsx 791     2207  Correo e… Fami…    57 Hombre Francia Secund…       57
    ##  5 A1IR.xlsx 1270    3586  Correo e… Camb…    33 Mujer  Francia Univer…       33
    ##  6 A1IR.xlsx 1270    3586  Correo e… Camb…    33 Mujer  Francia Univer…       33
    ##  7 A1IR.xlsx 1270    3587  Nota/avi… Nota…    33 Mujer  Francia Univer…       33
    ##  8 A1IR.xlsx 836     2330  Correo e… Camb…    44 Mujer  Francia Univer…       44
    ##  9 A1IR.xlsx 827     2308  Correo e… Fami…    64 Mujer  Francia Univer…        1
    ## 10 A1IR.xlsx 827     2308  Correo e… Fami…    64 Mujer  Francia Univer…        1
    ## # ℹ 17 more rows
    ## # ℹ 7 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

``` r
A1 %>% 
  filter(Contacts == "Otros")
```

    ## # A tibble: 26 × 17
    ## # Groups:   Student [5]
    ##    Source     Student Task  TypeText Theme   Age Gender Country Studies AgeStart
    ##    <chr>      <chr>   <chr> <chr>    <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx  1406    3983  Nota/av… Nota…    37 Mujer  Guinea  Univer…       37
    ##  2 A1IR.xlsx  1463    4138  Correo … Camb…    37 Mujer  Guinea  Primar…        1
    ##  3 A1IR.xlsx  1463    4139  Nota/av… Nota…    37 Mujer  Guinea  Primar…        1
    ##  4 A1IR.xlsx  1463    4138  Correo … Camb…    37 Mujer  Guinea  Primar…        1
    ##  5 A1IR.xlsx  1406    3982  Correo … Camb…    37 Mujer  Guinea  Univer…       37
    ##  6 A1IR.xlsx  257     711   Correo … Camb…    18 Mujer  Francia Secund…       12
    ##  7 A1VA.xlsx  1406    3982  Correo … Camb…    37 Mujer  Guinea  Univer…       37
    ##  8 A1VA.xlsx  257     711   Correo … Camb…    18 Mujer  Francia Secund…       12
    ##  9 A1VOY.xlsx 1463    4138  Correo … Camb…    37 Mujer  Guinea  Primar…        1
    ## 10 A1VOY.xlsx 1463    4139  Nota/av… Nota…    37 Mujer  Guinea  Primar…        1
    ## # ℹ 16 more rows
    ## # ℹ 7 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>

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

As can be seen above, it appears that ages in the L1 French dataset
range from 15 to 71 years old. Not only that, but the age group with the
most amount of students is the 61 year-olds who have 13 total
individuals. The age group with the least amount of students is the 15,
18, 19, 24, and 44 year-olds who only had one individual per age. (*need
to edit this for ENG*)

# Picking Out the Prescriptive Output

``` r
CA1 <- A1 %>%
    mutate(FirstWord = sub(" .*", "", ContextR))
CA1
```

    ## # A tibble: 418 × 18
    ## # Groups:   Student [83]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 774     2154  Correo e… Camb…    22 Mujer  Francia Otros         22
    ##  2 A1IR.xlsx 1239    3493  Correo e… Camb…    58 Hombre Francia Univer…       58
    ##  3 A1IR.xlsx 1974    5564  Correo e… Fami…    45 Hombre Francia Secund…       45
    ##  4 A1IR.xlsx 776     2160  Correo e… Camb…    65 Mujer  Francia Otros         64
    ##  5 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  6 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  7 A1IR.xlsx 380     1053  Nota/avi… Nota…    37 Mujer  Francia Univer…        5
    ##  8 A1IR.xlsx 779     2169  Correo e… Camb…    52 Mujer  Francia Otros          1
    ##  9 A1IR.xlsx 775     2158  Nota/avi… Nota…    27 Mujer  Francia Otros         20
    ## 10 A1IR.xlsx 781     2177  Correo e… Fami…    36 Mujer  Francia Otros         14
    ## # ℹ 408 more rows
    ## # ℹ 8 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>, FirstWord <chr>

``` r
# If needed, save the modified data frame to a new object or overwrite the existing one
A1 <- CA1
A1
```

    ## # A tibble: 418 × 18
    ## # Groups:   Student [83]
    ##    Source    Student Task  TypeText  Theme   Age Gender Country Studies AgeStart
    ##    <chr>     <chr>   <chr> <chr>     <chr> <dbl> <chr>  <chr>   <chr>      <dbl>
    ##  1 A1IR.xlsx 774     2154  Correo e… Camb…    22 Mujer  Francia Otros         22
    ##  2 A1IR.xlsx 1239    3493  Correo e… Camb…    58 Hombre Francia Univer…       58
    ##  3 A1IR.xlsx 1974    5564  Correo e… Fami…    45 Hombre Francia Secund…       45
    ##  4 A1IR.xlsx 776     2160  Correo e… Camb…    65 Mujer  Francia Otros         64
    ##  5 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  6 A1IR.xlsx 2002    5639  Correo e… Camb…    64 Hombre Francia Otros         63
    ##  7 A1IR.xlsx 380     1053  Nota/avi… Nota…    37 Mujer  Francia Univer…        5
    ##  8 A1IR.xlsx 779     2169  Correo e… Camb…    52 Mujer  Francia Otros          1
    ##  9 A1IR.xlsx 775     2158  Nota/avi… Nota…    27 Mujer  Francia Otros         20
    ## 10 A1IR.xlsx 781     2177  Correo e… Fami…    36 Mujer  Francia Otros         14
    ## # ℹ 408 more rows
    ## # ℹ 8 more variables: Months <dbl>, Contacts <chr>, ContextL <chr>,
    ## #   GramElem1 <chr>, Tag1 <chr>, Lemma1 <chr>, ContextR <chr>, FirstWord <chr>

# Statistical Analyses

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
    ##  date     2024-11-21
    ##  pandoc   3.2 @ C:/Program Files/RStudio/resources/app/bin/quarto/bin/tools/ (via rmarkdown)
    ## 
    ## ─ Packages ───────────────────────────────────────────────────────────────────
    ##  package     * version date (UTC) lib source
    ##  cellranger    1.1.0   2016-07-27 [1] CRAN (R 4.4.1)
    ##  cli           3.6.3   2024-06-21 [1] CRAN (R 4.4.1)
    ##  colorspace    2.1-1   2024-07-26 [1] CRAN (R 4.4.1)
    ##  digest        0.6.37  2024-08-19 [1] CRAN (R 4.4.1)
    ##  dplyr       * 1.1.4   2023-11-17 [1] CRAN (R 4.4.1)
    ##  evaluate      0.24.0  2024-06-10 [1] CRAN (R 4.4.1)
    ##  fansi         1.0.6   2023-12-08 [1] CRAN (R 4.4.1)
    ##  fastmap       1.2.0   2024-05-15 [1] CRAN (R 4.4.1)
    ##  forcats     * 1.0.0   2023-01-29 [1] CRAN (R 4.4.1)
    ##  generics      0.1.3   2022-07-05 [1] CRAN (R 4.4.1)
    ##  ggplot2     * 3.5.1   2024-04-23 [1] CRAN (R 4.4.1)
    ##  glue          1.7.0   2024-01-09 [1] CRAN (R 4.4.1)
    ##  gtable        0.3.5   2024-04-22 [1] CRAN (R 4.4.1)
    ##  hms           1.1.3   2023-03-21 [1] CRAN (R 4.4.1)
    ##  htmltools     0.5.8.1 2024-04-04 [1] CRAN (R 4.4.1)
    ##  knitr         1.48    2024-07-07 [1] CRAN (R 4.4.1)
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
