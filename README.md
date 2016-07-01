
# Random names

[![Travis-CI Build Status](https://travis-ci.org/karthik/randNames.png?branch=master)](https://travis-ci.org/karthik/randNames)  
[![Coverage Status](https://coveralls.io/repos/karthik/randNames/badge.svg)](https://coveralls.io/r/karthik/randNames)  
[![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/randNames)](https://cran.r-project.org/package=randNames)




**Installation**


```r
install.packages("randNames")
```

or for the development version  

```r
devtools::install_github("karthik/randNames")
```

It queries a random name API and returns a whole bunch of useful fields. 


```r
library(dplyr)
library(randNames)
20 %>%
  rand_names %>%
  select(first = name.first, last = name.last)
```

```
#> Source: local data frame [20 x 2]
#> 
#>       first        last
#>       (chr)       (chr)
#> 1     nalan    demirbaş
#> 2  danielle        lord
#> 3    nurdan     sepetçi
#> 4     julie       miles
#> 5     vedat     akyürek
#> 6     doris     jimenez
#> 7    cícero       pinto
#> 8  salvador      brooks
#> 9   florian    leclercq
#> 10    wyatt      harris
#> 11 caroline christensen
#> 12  علی رضا     نكو نظر
#> 13    megan    mitchell
#> 14  anthony       ennis
#> 15    bryan        cook
#> 16   jessie      tucker
#> 17      mia        ryan
#> 18     luis     legrand
#> 19   iolene     barbosa
#> 20     line       david
```

__Filter by nationality__


```r
15 %>% 
# Available nationalities: AU, BR, CA, CH, DE, DK, ES, FI, FR, GB, IE, IR, NL, NZ, TR, US
# You can specify multiple nationalities. e.g. "gb, us"
  rand_names(nationality = "GB") %>%  
  select(name.first, name.last)
```

```
#> Source: local data frame [15 x 2]
#> 
#>    name.first name.last
#>         <chr>     <chr>
#> 1       susan hernandez
#> 2      hector   jenkins
#> 3     caitlin    rhodes
#> 4     gregory  jennings
#> 5       vicki    fuller
#> 6   christian    gibson
#> 7       riley   holland
#> 8      ronald      boyd
#> 9         sam   jimenez
#> 10       ivan armstrong
#> 11       joey     grant
#> 12      alice  lawrence
#> 13     austin    davies
#> 14   florence      ward
#> 15      ruben     meyer
```

__Filter by gender__


```r
15 %>% 
  rand_names(gender = "female") %>% 
  select(name.first, name.last)
```

```
#> Source: local data frame [15 x 2]
#> 
#>    name.first    name.last
#>         (chr)        (chr)
#> 1     abigail        sirko
#> 2   annemarie         kern
#> 3     kristin      gerlach
#> 4      claire      legrand
#> 5      alicia      olivier
#> 6      shayna van de burgt
#> 7  clémentine     gauthier
#> 8        آوین      نكو نظر
#> 9        آوین         کوتی
#> 10     minttu        salmi
#> 11     مرسانا      محمدخان
#> 12    candice      holland
#> 13       anni        saksa
#> 14      tessa     gaillard
#> 15         la    de kruijf
```


__Set seed__


```r
15 %>% 
  rand_names(seed = 'foobar') %>% 
  select(name.first, name.last)
```

```
#> Source: local data frame [15 x 2]
#> 
#>    name.first  name.last
#>         (chr)      (chr)
#> 1       becky       sims
#> 2      amelia   anderson
#> 3       vilho   lampinen
#> 4      maëlle     robert
#> 5      kasper       palo
#> 6       macit    kılıççı
#> 7      alexis     walker
#> 8        cléa   rousseau
#> 9      allert    thielen
#> 10     jasper         li
#> 11      çetin       adan
#> 12        ray cunningham
#> 13      lewis     morris
#> 14       yann      roche
#> 15       elli   niskanen
```

__Additional fields beyond first and last name__

gender  
email  
registered"        
dob  
phone  
cell  
nat  
name.title  
name.first       
name.last  
location.street  
location.city  
location.state  
location.postcode  
login.username"    
login.password  
login.salt  
login.md5  
login.sha1  
login.sha256  
id.name  
id.value  
picture.large  
picture.medium     
picture.thumbnail  
