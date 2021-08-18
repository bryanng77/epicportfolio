# Cleaning Fabric Store Data

[Back to Home](README.md) | [Python Projects](pythonminiproject.md)

![image](https://user-images.githubusercontent.com/79688274/129765913-45908a97-0a7f-4b05-aaee-46b8b3244652.png)

Hello there, glad you could join me today! For this mini project, I will be using some basic Python functions (mainly For Loops, Functions and some string methods) to clean up some data that was generated from a very old cash register that my god-grandmother is still using up till this day in her sewing shop all the way at Tanglin Halt area. I thought it'd be fun to play around with the data and explore what I can do with it! Without further ado, LETS GO!



All the information will be stored in a string called **daily_sales**. (stored it in a string so that I can practice :P)

Some of the daily responsibilities that my god-grandmother does involves:
1. Keeping track of the name of our customers 
2. Calculating the total amount of money made
3. Tallying number of transactions for the day 
4. Number of fabrics sold



```python
# Data that I will be working on today! :D

daily_sales = \
"""Lizanne   ;,;$1.21   ;,;   white ;,; 
09/15/17   ,Robert Tan   ;,;   $7.29;,; 
white&blue;,;   09/15/17 ,Garrett Tan ;,;$12.52 
;,;   white&blue ;,; 09/15/17 ,Lucia Tan  
;,;   $5.13   ;,; white   ;,; 09/15/17,
Edmund Lee   ;,;$20.39;,; white&yellow 
;,;09/15/17   ,   Stacy Lim;,;$30.82;,;   
purple ;,;09/15/17 ,Verchelle;,; $1.85   ;,; 
purple&yellow ;,;09/15/17,   Shaun ;,; 
$17.98;,;purple&yellow ;,; 09/15/17 , 
Erick ;,;$17.41;,; blue ;,; 09/15/17, 
Michelle  ;,;$28.59;,; blue;,;   09/15/17   , 
Carrolyn ;,; $14.51;,;   purple&blue   ;,;   
09/15/17   , Teresa    ;,; $19.64 ;,; 
white;,;09/15/17   ,   Jacob  ;,; $11.40   
;,; white&red   ;,; 09/15/17, Cramery ;,; 
$8.79 ;,; white&blue&red   ;,;09/15/17   , 
Peggy Soh;,; $8.65 ;,;blue   ;,; 09/15/17,   Kenneth  ;,;   $10.53;,;   green&blue   ;,; 
09/15/17   ,   Marvin ;,;   $16.49;,; 
green&blue&red   ;,;   09/15/17 , Russell 
;,; $6.55 ;,;   green&blue&red;,;   09/15/17 ,
Ismail;,;   $11.86   ;,;black;,;  
09/15/17,   June   ;,;   $22.29 ;,;  
black&yellow ;,;09/15/17 , Jaime   ;,;   
$8.35;,;   white&black&yellow   ;,;   09/15/17,   
Rhonda ;,;$2.91 ;,;   white&black&yellow   
;,;09/15/17, Darren  ;,;$22.94;,;green 
;,;09/15/17, Malone;,;$4.70   ;,; green&yellow 
;,; 09/15/17   , Miles;,;   $3.59   
;,;green&yellow&blue;,;   09/15/17   , Joseph   ;,;$5.66   ;,; green&yellow&purple&blue 
;,;   09/15/17 , Samantha  ;,;$17.51   ;,;   
black   ;,;   09/15/17 , Audrey  ;,; 
$5.54;,;black&blue   ;,;09/15/17 , William ;,; 
$17.13;,; black&blue;,;   09/15/17,   Randy ;,;   $21.13 ;,;black ;,;09/15/17 ,Elissa ;,; $0.35   ;,; black&purple;,;   09/15/17   ,
Ernest ;,; $13.91   ;,;   black&purple ;,;   
09/15/17,   Shannon    ;,;$19.26   ;,; 
yellow;,; 09/15/17   , Sammy Koh;,; $5.45;,;   
yellow&red ;,;09/15/17 ,   Steven Roh ;,;$5.50   
;,;   yellow;,;   09/15/17, Ruben Ee   ;,; 
$14.56 ;,;   yellow&blue;,;09/15/17 , Esmae Ping;,;   $7.33   ;,;   yellow&blue&red
;,; 09/15/17   ,   Rene Hardy   ;,; $20.22   ;,; 
black ;,;   09/15/17 ,   Lucy Ng   ;,; $8.67   
;,;black&red  ;,; 09/15/17 ,Damien Tan ;,;   
$8.31;,;   black&red ;,;   09/15/17,   Stacey Lim 
;,;   $15.70   ;,;   white&black&red ;,;09/15/17   
,   Tanya Kim   ;,;   $6.74   ;,;yellow   ;,; 
09/15/17 , Melody Ho ;,;   $30.84   
;,;yellow&black;,;   09/15/17 , Louise    ;,; 
$12.31 ;,; green&yellow&black;,;   09/15/17 ,
Ryan tan;,;$2.94 ;,; yellow ;,; 09/15/17 
,Justin  ;,; $22.46   ;,;white&yellow ;,;   
09/15/17,   Benendict ;,;   $6.60;,;   
white&yellow&black ;,;09/15/17   ,   Dorathy  
;,;   $6.27 ;,; yellow   ;,;09/15/17 , Potter ;,;$21.12   ;,; yellow;,; 09/15/17   , 
Desiree Loh ;,;$2.10   ;,;white;,; 09/15/17  
, Garnett ;,; $14.22 ;,;white&black;,;   
09/15/17, Angelica ;,;$11.60;,;white&black   
;,;   09/15/17   ,   Jamie Seah   ;,; $25.27   ;,; 
white&black&red ;,;09/15/17   ,   Randy Poh   
;,;$8.26;,;   purple;,; 09/15/17 ,   Nadia 
;,;   $30.80 ;,;   purple&yellow   ;,; 09/15/17   , 
Hannah ;,;   $22.61   ;,;   purple&yellow   
;,;09/15/17, Richard;,;$22.19 ;,; 
green&purple&yellow ;,;09/15/17   ,Stanley  
;,; $7.47   ;,; red ;,; 09/15/17 , Anna ;,;$5.49 ;,; yellow&red ;,;   09/15/17   ,
Terrance Sim ;,;   $23.70  ;,;green&yellow&red 
;,; 09/15/17 ,   Brandon ;,; $26.66 ;,; 
red   ;,;09/15/17 , Morgan Freeman ;,; $25.95;,; 
green&red ;,;   09/15/17   ,Irvin Hu 
;,;$19.55 ;,; green&white&red ;,;   09/15/17 , Ross Lynch;,;   $15.68;,;   white ;,;   09/15/17 , Brandy Fu ;,;$23.57;,;   white&red   ;,;09/15/17, 
 Riley   ;,;$29.32;,; purple;,;09/15/17 ,Mike    ;,; $26.44 ;,;   purple   ;,; 09/15/17, 
Jamie    ;,; $17.24;,;green ;,; 09/15/17   , 
Noah  ;,;   $8.49   ;,;green   ;,;09/15/17   
,Josephine Lim ;,;$13.10 ;,;green;,;   09/15/17 ,   Tracey ;,;$20.39 ;,; red   ;,; 09/15/17 ,
Ignacio Parks;,;$14.70   ;,; white&red ;,;09/15/17 
, Beatrice  ;,;$22.45   ;,;white&purple&red 
;,;   09/15/17, Andre    ;,;   $28.46   ;,;   
red;,;   09/15/17 ,   Albert  ;,; $23.89;,;   
black&red;,; 09/15/17,   Javier    ;,;   
$24.49   ;,; black&red ;,; 09/15/17   , Everett  ;,;$1.81;,;   black&red ;,; 09/15/17 ,   
Abraham ;,; $6.81   ;,;green;,;   09/15/17   
,   Traci  ;,;$0.65;,; green&yellow;,; 
09/15/17 , Jeffrey Seah   ;,;$26.45;,; 
green&yellow&blue   ;,;   09/15/17,    Wilson 
;,;   $7.69 ;,; purple;,; 09/15/17,Janice   
;,;$8.74   ;,; purple&black   ;,;09/15/17 ,  
Leonard  ;,;   $1.86   ;,;yellow  
;,;09/15/17,Sanchez;,;$14.75   ;,; yellow;,;   
09/15/17   ,Donna ;,; $28.10  ;,; 
yellow&blue;,;   09/15/17   , Terrence   ;,; 
$9.91   ;,; green ;,;09/15/17   ,Jody ;,; 
$16.34 ;,; green ;,;   09/15/17,   Daryl  
;,;$27.57;,; white;,;   09/15/17   , Miguel ;,;$5.25;,; white&blue   ;,;   09/15/17 ,   
 Gonzalez;,; $9.51;,;   white&black&blue   
;,;   09/15/17   ,   Lora  ;,;$20.56 ;,; 
green;,;   09/15/17,Owena He ;,; $21.64   ;,;   
green&yellow;,;09/15/17,Malcolm  ;,;   
$24.99   ;,;   green&yellow&black;,; 09/15/17 ,   
Eric  ;,;$29.70;,; green ;,; 09/15/17 
,Madeline ;,;   $15.52;,;green;,;   09/15/17 
, Leticia  ;,;$15.70 ;,; green&purple;,; 
09/15/17 ,   Mario  ;,; $12.36 ;,;green ;,; 
09/15/17,Lewis ;,;   $13.66   ;,;   
green&white;,;09/15/17,    Phelps Ng   ;,;$30.52   
;,; green&white&blue   ;,; 09/15/17 , Myra Fernando
;,;   $22.66   ;,; green&white&blue;,;09/15/17"""
```

My goodness!! Look at how messy the data is! Today, our job here is to ensure that the data is split up properly so that we can proceed with our tasks. After much observation, you will be able to see that the data is organized in such a way that shows the **name of customer, cost of fabric, color of fabric and date of purchase**.

It looks like each transaction is separated from the next transaction by a "," and then each piece of data within a transaction is separated by the artifact ";,;". I realized that in order for us to split everything up, we will need to replace the ";,;" to something without a comma so that we do not split any of the transactions themselves. I'll show you what I mean very soon!


```python
# Case Study 1: If we do not replace the ";,;" with something else (WRONG)
daily_sales_replaced_trial = daily_sales.split(",")
print(daily_sales_replaced_trial)
```

    ['Lizanne   ;', ';$1.21   ;', ';   white ;', '; \n09/15/17   ', 'Robert Tan   ;', ';   $7.29;', '; \nwhite&blue;', ';   09/15/17 ', 'Garrett Tan ;', ';$12.52 \n;', ';   white&blue ;', '; 09/15/17 ', 'Lucia Tan  \n;', ';   $5.13   ;', '; white   ;', '; 09/15/17', '\nEdmund Lee   ;', ';$20.39;', '; white&yellow \n;', ';09/15/17   ', '   Stacy Lim;', ';$30.82;', ';   \npurple ;', ';09/15/17 ', 'Verchelle;', '; $1.85   ;', '; \npurple&yellow ;', ';09/15/17', '   Shaun ;', '; \n$17.98;', ';purple&yellow ;', '; 09/15/17 ', ' \nErick ;', ';$17.41;', '; blue ;', '; 09/15/17', ' \nMichelle  ;', ';$28.59;', '; blue;', ';   09/15/17   ', ' \nCarrolyn ;', '; $14.51;', ';   purple&blue   ;', ';   \n09/15/17   ', ' Teresa    ;', '; $19.64 ;', '; \nwhite;', ';09/15/17   ', '   Jacob  ;', '; $11.40   \n;', '; white&red   ;', '; 09/15/17', ' Cramery ;', '; \n$8.79 ;', '; white&blue&red   ;', ';09/15/17   ', ' \nPeggy Soh;', '; $8.65 ;', ';blue   ;', '; 09/15/17', '   Kenneth  ;', ';   $10.53;', ';   green&blue   ;', '; \n09/15/17   ', '   Marvin ;', ';   $16.49;', '; \ngreen&blue&red   ;', ';   09/15/17 ', ' Russell \n;', '; $6.55 ;', ';   green&blue&red;', ';   09/15/17 ', '\nIsmail;', ';   $11.86   ;', ';black;', ';  \n09/15/17', '   June   ;', ';   $22.29 ;', ';  \nblack&yellow ;', ';09/15/17 ', ' Jaime   ;', ';   \n$8.35;', ';   white&black&yellow   ;', ';   09/15/17', '   \nRhonda ;', ';$2.91 ;', ';   white&black&yellow   \n;', ';09/15/17', ' Darren  ;', ';$22.94;', ';green \n;', ';09/15/17', ' Malone;', ';$4.70   ;', '; green&yellow \n;', '; 09/15/17   ', ' Miles;', ';   $3.59   \n;', ';green&yellow&blue;', ';   09/15/17   ', ' Joseph   ;', ';$5.66   ;', '; green&yellow&purple&blue \n;', ';   09/15/17 ', ' Samantha  ;', ';$17.51   ;', ';   \nblack   ;', ';   09/15/17 ', ' Audrey  ;', '; \n$5.54;', ';black&blue   ;', ';09/15/17 ', ' William ;', '; \n$17.13;', '; black&blue;', ';   09/15/17', '   Randy ;', ';   $21.13 ;', ';black ;', ';09/15/17 ', 'Elissa ;', '; $0.35   ;', '; black&purple;', ';   09/15/17   ', '\nErnest ;', '; $13.91   ;', ';   black&purple ;', ';   \n09/15/17', '   Shannon    ;', ';$19.26   ;', '; \nyellow;', '; 09/15/17   ', ' Sammy Koh;', '; $5.45;', ';   \nyellow&red ;', ';09/15/17 ', '   Steven Roh ;', ';$5.50   \n;', ';   yellow;', ';   09/15/17', ' Ruben Ee   ;', '; \n$14.56 ;', ';   yellow&blue;', ';09/15/17 ', ' Esmae Ping;', ';   $7.33   ;', ';   yellow&blue&red\n;', '; 09/15/17   ', '   Rene Hardy   ;', '; $20.22   ;', '; \nblack ;', ';   09/15/17 ', '   Lucy Ng   ;', '; $8.67   \n;', ';black&red  ;', '; 09/15/17 ', 'Damien Tan ;', ';   \n$8.31;', ';   black&red ;', ';   09/15/17', '   Stacey Lim \n;', ';   $15.70   ;', ';   white&black&red ;', ';09/15/17   \n', '   Tanya Kim   ;', ';   $6.74   ;', ';yellow   ;', '; \n09/15/17 ', ' Melody Ho ;', ';   $30.84   \n;', ';yellow&black;', ';   09/15/17 ', ' Louise    ;', '; \n$12.31 ;', '; green&yellow&black;', ';   09/15/17 ', '\nRyan tan;', ';$2.94 ;', '; yellow ;', '; 09/15/17 \n', 'Justin  ;', '; $22.46   ;', ';white&yellow ;', ';   \n09/15/17', '   Benendict ;', ';   $6.60;', ';   \nwhite&yellow&black ;', ';09/15/17   ', '   Dorathy  \n;', ';   $6.27 ;', '; yellow   ;', ';09/15/17 ', ' Potter ;', ';$21.12   ;', '; yellow;', '; 09/15/17   ', ' \nDesiree Loh ;', ';$2.10   ;', ';white;', '; 09/15/17  \n', ' Garnett ;', '; $14.22 ;', ';white&black;', ';   \n09/15/17', ' Angelica ;', ';$11.60;', ';white&black   \n;', ';   09/15/17   ', '   Jamie Seah   ;', '; $25.27   ;', '; \nwhite&black&red ;', ';09/15/17   ', '   Randy Poh   \n;', ';$8.26;', ';   purple;', '; 09/15/17 ', '   Nadia \n;', ';   $30.80 ;', ';   purple&yellow   ;', '; 09/15/17   ', ' \nHannah ;', ';   $22.61   ;', ';   purple&yellow   \n;', ';09/15/17', ' Richard;', ';$22.19 ;', '; \ngreen&purple&yellow ;', ';09/15/17   ', 'Stanley  \n;', '; $7.47   ;', '; red ;', '; 09/15/17 ', ' Anna ;', ';$5.49 ;', '; yellow&red ;', ';   09/15/17   ', '\nTerrance Sim ;', ';   $23.70  ;', ';green&yellow&red \n;', '; 09/15/17 ', '   Brandon ;', '; $26.66 ;', '; \nred   ;', ';09/15/17 ', ' Morgan Freeman ;', '; $25.95;', '; \ngreen&red ;', ';   09/15/17   ', 'Irvin Hu \n;', ';$19.55 ;', '; green&white&red ;', ';   09/15/17 ', ' Ross Lynch;', ';   $15.68;', ';   white ;', ';   09/15/17 ', ' Brandy Fu ;', ';$23.57;', ';   white&red   ;', ';09/15/17', ' \n Riley   ;', ';$29.32;', '; purple;', ';09/15/17 ', 'Mike    ;', '; $26.44 ;', ';   purple   ;', '; 09/15/17', ' \nJamie    ;', '; $17.24;', ';green ;', '; 09/15/17   ', ' \nNoah  ;', ';   $8.49   ;', ';green   ;', ';09/15/17   \n', 'Josephine Lim ;', ';$13.10 ;', ';green;', ';   09/15/17 ', '   Tracey ;', ';$20.39 ;', '; red   ;', '; 09/15/17 ', '\nIgnacio Parks;', ';$14.70   ;', '; white&red ;', ';09/15/17 \n', ' Beatrice  ;', ';$22.45   ;', ';white&purple&red \n;', ';   09/15/17', ' Andre    ;', ';   $28.46   ;', ';   \nred;', ';   09/15/17 ', '   Albert  ;', '; $23.89;', ';   \nblack&red;', '; 09/15/17', '   Javier    ;', ';   \n$24.49   ;', '; black&red ;', '; 09/15/17   ', ' Everett  ;', ';$1.81;', ';   black&red ;', '; 09/15/17 ', '   \nAbraham ;', '; $6.81   ;', ';green;', ';   09/15/17   \n', '   Traci  ;', ';$0.65;', '; green&yellow;', '; \n09/15/17 ', ' Jeffrey Seah   ;', ';$26.45;', '; \ngreen&yellow&blue   ;', ';   09/15/17', '    Wilson \n;', ';   $7.69 ;', '; purple;', '; 09/15/17', 'Janice   \n;', ';$8.74   ;', '; purple&black   ;', ';09/15/17 ', '  \nLeonard  ;', ';   $1.86   ;', ';yellow  \n;', ';09/15/17', 'Sanchez;', ';$14.75   ;', '; yellow;', ';   \n09/15/17   ', 'Donna ;', '; $28.10  ;', '; \nyellow&blue;', ';   09/15/17   ', ' Terrence   ;', '; \n$9.91   ;', '; green ;', ';09/15/17   ', 'Jody ;', '; \n$16.34 ;', '; green ;', ';   09/15/17', '   Daryl  \n;', ';$27.57;', '; white;', ';   09/15/17   ', ' Miguel ;', ';$5.25;', '; white&blue   ;', ';   09/15/17 ', '   \n Gonzalez;', '; $9.51;', ';   white&black&blue   \n;', ';   09/15/17   ', '   Lora  ;', ';$20.56 ;', '; \ngreen;', ';   09/15/17', 'Owena He ;', '; $21.64   ;', ';   \ngreen&yellow;', ';09/15/17', 'Malcolm  ;', ';   \n$24.99   ;', ';   green&yellow&black;', '; 09/15/17 ', '   \nEric  ;', ';$29.70;', '; green ;', '; 09/15/17 \n', 'Madeline ;', ';   $15.52;', ';green;', ';   09/15/17 \n', ' Leticia  ;', ';$15.70 ;', '; green&purple;', '; \n09/15/17 ', '   Mario  ;', '; $12.36 ;', ';green ;', '; \n09/15/17', 'Lewis ;', ';   $13.66   ;', ';   \ngreen&white;', ';09/15/17', '    Phelps Ng   ;', ';$30.52   \n;', '; green&white&blue   ;', '; 09/15/17 ', ' Myra Fernando\n;', ';   $22.66   ;', '; green&white&blue;', ';09/15/17']


**Lo and Behold!!!** We have successfully made our data more complicated HAHAHAHA. Alright, lets do it properly now! 


```python
# THE CORRECT WAY TO DO IT
# By using the .replace() and .split() string functions, we will get something like this:
daily_sales_replaced = daily_sales.replace(";,;", "+")
print(daily_sales_replaced)
```

    Lizanne   +$1.21   +   white + 
    09/15/17   ,Robert Tan   +   $7.29+ 
    white&blue+   09/15/17 ,Garrett Tan +$12.52 
    +   white&blue + 09/15/17 ,Lucia Tan  
    +   $5.13   + white   + 09/15/17,
    Edmund Lee   +$20.39+ white&yellow 
    +09/15/17   ,   Stacy Lim+$30.82+   
    purple +09/15/17 ,Verchelle+ $1.85   + 
    purple&yellow +09/15/17,   Shaun + 
    $17.98+purple&yellow + 09/15/17 , 
    Erick +$17.41+ blue + 09/15/17, 
    Michelle  +$28.59+ blue+   09/15/17   , 
    Carrolyn + $14.51+   purple&blue   +   
    09/15/17   , Teresa    + $19.64 + 
    white+09/15/17   ,   Jacob  + $11.40   
    + white&red   + 09/15/17, Cramery + 
    $8.79 + white&blue&red   +09/15/17   , 
    Peggy Soh+ $8.65 +blue   + 09/15/17,   Kenneth  +   $10.53+   green&blue   + 
    09/15/17   ,   Marvin +   $16.49+ 
    green&blue&red   +   09/15/17 , Russell 
    + $6.55 +   green&blue&red+   09/15/17 ,
    Ismail+   $11.86   +black+  
    09/15/17,   June   +   $22.29 +  
    black&yellow +09/15/17 , Jaime   +   
    $8.35+   white&black&yellow   +   09/15/17,   
    Rhonda +$2.91 +   white&black&yellow   
    +09/15/17, Darren  +$22.94+green 
    +09/15/17, Malone+$4.70   + green&yellow 
    + 09/15/17   , Miles+   $3.59   
    +green&yellow&blue+   09/15/17   , Joseph   +$5.66   + green&yellow&purple&blue 
    +   09/15/17 , Samantha  +$17.51   +   
    black   +   09/15/17 , Audrey  + 
    $5.54+black&blue   +09/15/17 , William + 
    $17.13+ black&blue+   09/15/17,   Randy +   $21.13 +black +09/15/17 ,Elissa + $0.35   + black&purple+   09/15/17   ,
    Ernest + $13.91   +   black&purple +   
    09/15/17,   Shannon    +$19.26   + 
    yellow+ 09/15/17   , Sammy Koh+ $5.45+   
    yellow&red +09/15/17 ,   Steven Roh +$5.50   
    +   yellow+   09/15/17, Ruben Ee   + 
    $14.56 +   yellow&blue+09/15/17 , Esmae Ping+   $7.33   +   yellow&blue&red
    + 09/15/17   ,   Rene Hardy   + $20.22   + 
    black +   09/15/17 ,   Lucy Ng   + $8.67   
    +black&red  + 09/15/17 ,Damien Tan +   
    $8.31+   black&red +   09/15/17,   Stacey Lim 
    +   $15.70   +   white&black&red +09/15/17   
    ,   Tanya Kim   +   $6.74   +yellow   + 
    09/15/17 , Melody Ho +   $30.84   
    +yellow&black+   09/15/17 , Louise    + 
    $12.31 + green&yellow&black+   09/15/17 ,
    Ryan tan+$2.94 + yellow + 09/15/17 
    ,Justin  + $22.46   +white&yellow +   
    09/15/17,   Benendict +   $6.60+   
    white&yellow&black +09/15/17   ,   Dorathy  
    +   $6.27 + yellow   +09/15/17 , Potter +$21.12   + yellow+ 09/15/17   , 
    Desiree Loh +$2.10   +white+ 09/15/17  
    , Garnett + $14.22 +white&black+   
    09/15/17, Angelica +$11.60+white&black   
    +   09/15/17   ,   Jamie Seah   + $25.27   + 
    white&black&red +09/15/17   ,   Randy Poh   
    +$8.26+   purple+ 09/15/17 ,   Nadia 
    +   $30.80 +   purple&yellow   + 09/15/17   , 
    Hannah +   $22.61   +   purple&yellow   
    +09/15/17, Richard+$22.19 + 
    green&purple&yellow +09/15/17   ,Stanley  
    + $7.47   + red + 09/15/17 , Anna +$5.49 + yellow&red +   09/15/17   ,
    Terrance Sim +   $23.70  +green&yellow&red 
    + 09/15/17 ,   Brandon + $26.66 + 
    red   +09/15/17 , Morgan Freeman + $25.95+ 
    green&red +   09/15/17   ,Irvin Hu 
    +$19.55 + green&white&red +   09/15/17 , Ross Lynch+   $15.68+   white +   09/15/17 , Brandy Fu +$23.57+   white&red   +09/15/17, 
     Riley   +$29.32+ purple+09/15/17 ,Mike    + $26.44 +   purple   + 09/15/17, 
    Jamie    + $17.24+green + 09/15/17   , 
    Noah  +   $8.49   +green   +09/15/17   
    ,Josephine Lim +$13.10 +green+   09/15/17 ,   Tracey +$20.39 + red   + 09/15/17 ,
    Ignacio Parks+$14.70   + white&red +09/15/17 
    , Beatrice  +$22.45   +white&purple&red 
    +   09/15/17, Andre    +   $28.46   +   
    red+   09/15/17 ,   Albert  + $23.89+   
    black&red+ 09/15/17,   Javier    +   
    $24.49   + black&red + 09/15/17   , Everett  +$1.81+   black&red + 09/15/17 ,   
    Abraham + $6.81   +green+   09/15/17   
    ,   Traci  +$0.65+ green&yellow+ 
    09/15/17 , Jeffrey Seah   +$26.45+ 
    green&yellow&blue   +   09/15/17,    Wilson 
    +   $7.69 + purple+ 09/15/17,Janice   
    +$8.74   + purple&black   +09/15/17 ,  
    Leonard  +   $1.86   +yellow  
    +09/15/17,Sanchez+$14.75   + yellow+   
    09/15/17   ,Donna + $28.10  + 
    yellow&blue+   09/15/17   , Terrence   + 
    $9.91   + green +09/15/17   ,Jody + 
    $16.34 + green +   09/15/17,   Daryl  
    +$27.57+ white+   09/15/17   , Miguel +$5.25+ white&blue   +   09/15/17 ,   
     Gonzalez+ $9.51+   white&black&blue   
    +   09/15/17   ,   Lora  +$20.56 + 
    green+   09/15/17,Owena He + $21.64   +   
    green&yellow+09/15/17,Malcolm  +   
    $24.99   +   green&yellow&black+ 09/15/17 ,   
    Eric  +$29.70+ green + 09/15/17 
    ,Madeline +   $15.52+green+   09/15/17 
    , Leticia  +$15.70 + green&purple+ 
    09/15/17 ,   Mario  + $12.36 +green + 
    09/15/17,Lewis +   $13.66   +   
    green&white+09/15/17,    Phelps Ng   +$30.52   
    + green&white&blue   + 09/15/17 , Myra Fernando
    +   $22.66   + green&white&blue+09/15/17


By using this method, we will be able to "categorize" the different data that belongs to the different individuals. So yes, this is a great start. Now, we will use the **.split()** string function to further split it up.


```python
daily_transactions = daily_sales_replaced.split(",")
print(daily_transactions)
```

    ['Lizanne   +$1.21   +   white + \n09/15/17   ', 'Robert Tan   +   $7.29+ \nwhite&blue+   09/15/17 ', 'Garrett Tan +$12.52 \n+   white&blue + 09/15/17 ', 'Lucia Tan  \n+   $5.13   + white   + 09/15/17', '\nEdmund Lee   +$20.39+ white&yellow \n+09/15/17   ', '   Stacy Lim+$30.82+   \npurple +09/15/17 ', 'Verchelle+ $1.85   + \npurple&yellow +09/15/17', '   Shaun + \n$17.98+purple&yellow + 09/15/17 ', ' \nErick +$17.41+ blue + 09/15/17', ' \nMichelle  +$28.59+ blue+   09/15/17   ', ' \nCarrolyn + $14.51+   purple&blue   +   \n09/15/17   ', ' Teresa    + $19.64 + \nwhite+09/15/17   ', '   Jacob  + $11.40   \n+ white&red   + 09/15/17', ' Cramery + \n$8.79 + white&blue&red   +09/15/17   ', ' \nPeggy Soh+ $8.65 +blue   + 09/15/17', '   Kenneth  +   $10.53+   green&blue   + \n09/15/17   ', '   Marvin +   $16.49+ \ngreen&blue&red   +   09/15/17 ', ' Russell \n+ $6.55 +   green&blue&red+   09/15/17 ', '\nIsmail+   $11.86   +black+  \n09/15/17', '   June   +   $22.29 +  \nblack&yellow +09/15/17 ', ' Jaime   +   \n$8.35+   white&black&yellow   +   09/15/17', '   \nRhonda +$2.91 +   white&black&yellow   \n+09/15/17', ' Darren  +$22.94+green \n+09/15/17', ' Malone+$4.70   + green&yellow \n+ 09/15/17   ', ' Miles+   $3.59   \n+green&yellow&blue+   09/15/17   ', ' Joseph   +$5.66   + green&yellow&purple&blue \n+   09/15/17 ', ' Samantha  +$17.51   +   \nblack   +   09/15/17 ', ' Audrey  + \n$5.54+black&blue   +09/15/17 ', ' William + \n$17.13+ black&blue+   09/15/17', '   Randy +   $21.13 +black +09/15/17 ', 'Elissa + $0.35   + black&purple+   09/15/17   ', '\nErnest + $13.91   +   black&purple +   \n09/15/17', '   Shannon    +$19.26   + \nyellow+ 09/15/17   ', ' Sammy Koh+ $5.45+   \nyellow&red +09/15/17 ', '   Steven Roh +$5.50   \n+   yellow+   09/15/17', ' Ruben Ee   + \n$14.56 +   yellow&blue+09/15/17 ', ' Esmae Ping+   $7.33   +   yellow&blue&red\n+ 09/15/17   ', '   Rene Hardy   + $20.22   + \nblack +   09/15/17 ', '   Lucy Ng   + $8.67   \n+black&red  + 09/15/17 ', 'Damien Tan +   \n$8.31+   black&red +   09/15/17', '   Stacey Lim \n+   $15.70   +   white&black&red +09/15/17   \n', '   Tanya Kim   +   $6.74   +yellow   + \n09/15/17 ', ' Melody Ho +   $30.84   \n+yellow&black+   09/15/17 ', ' Louise    + \n$12.31 + green&yellow&black+   09/15/17 ', '\nRyan tan+$2.94 + yellow + 09/15/17 \n', 'Justin  + $22.46   +white&yellow +   \n09/15/17', '   Benendict +   $6.60+   \nwhite&yellow&black +09/15/17   ', '   Dorathy  \n+   $6.27 + yellow   +09/15/17 ', ' Potter +$21.12   + yellow+ 09/15/17   ', ' \nDesiree Loh +$2.10   +white+ 09/15/17  \n', ' Garnett + $14.22 +white&black+   \n09/15/17', ' Angelica +$11.60+white&black   \n+   09/15/17   ', '   Jamie Seah   + $25.27   + \nwhite&black&red +09/15/17   ', '   Randy Poh   \n+$8.26+   purple+ 09/15/17 ', '   Nadia \n+   $30.80 +   purple&yellow   + 09/15/17   ', ' \nHannah +   $22.61   +   purple&yellow   \n+09/15/17', ' Richard+$22.19 + \ngreen&purple&yellow +09/15/17   ', 'Stanley  \n+ $7.47   + red + 09/15/17 ', ' Anna +$5.49 + yellow&red +   09/15/17   ', '\nTerrance Sim +   $23.70  +green&yellow&red \n+ 09/15/17 ', '   Brandon + $26.66 + \nred   +09/15/17 ', ' Morgan Freeman + $25.95+ \ngreen&red +   09/15/17   ', 'Irvin Hu \n+$19.55 + green&white&red +   09/15/17 ', ' Ross Lynch+   $15.68+   white +   09/15/17 ', ' Brandy Fu +$23.57+   white&red   +09/15/17', ' \n Riley   +$29.32+ purple+09/15/17 ', 'Mike    + $26.44 +   purple   + 09/15/17', ' \nJamie    + $17.24+green + 09/15/17   ', ' \nNoah  +   $8.49   +green   +09/15/17   \n', 'Josephine Lim +$13.10 +green+   09/15/17 ', '   Tracey +$20.39 + red   + 09/15/17 ', '\nIgnacio Parks+$14.70   + white&red +09/15/17 \n', ' Beatrice  +$22.45   +white&purple&red \n+   09/15/17', ' Andre    +   $28.46   +   \nred+   09/15/17 ', '   Albert  + $23.89+   \nblack&red+ 09/15/17', '   Javier    +   \n$24.49   + black&red + 09/15/17   ', ' Everett  +$1.81+   black&red + 09/15/17 ', '   \nAbraham + $6.81   +green+   09/15/17   \n', '   Traci  +$0.65+ green&yellow+ \n09/15/17 ', ' Jeffrey Seah   +$26.45+ \ngreen&yellow&blue   +   09/15/17', '    Wilson \n+   $7.69 + purple+ 09/15/17', 'Janice   \n+$8.74   + purple&black   +09/15/17 ', '  \nLeonard  +   $1.86   +yellow  \n+09/15/17', 'Sanchez+$14.75   + yellow+   \n09/15/17   ', 'Donna + $28.10  + \nyellow&blue+   09/15/17   ', ' Terrence   + \n$9.91   + green +09/15/17   ', 'Jody + \n$16.34 + green +   09/15/17', '   Daryl  \n+$27.57+ white+   09/15/17   ', ' Miguel +$5.25+ white&blue   +   09/15/17 ', '   \n Gonzalez+ $9.51+   white&black&blue   \n+   09/15/17   ', '   Lora  +$20.56 + \ngreen+   09/15/17', 'Owena He + $21.64   +   \ngreen&yellow+09/15/17', 'Malcolm  +   \n$24.99   +   green&yellow&black+ 09/15/17 ', '   \nEric  +$29.70+ green + 09/15/17 \n', 'Madeline +   $15.52+green+   09/15/17 \n', ' Leticia  +$15.70 + green&purple+ \n09/15/17 ', '   Mario  + $12.36 +green + \n09/15/17', 'Lewis +   $13.66   +   \ngreen&white+09/15/17', '    Phelps Ng   +$30.52   \n+ green&white&blue   + 09/15/17 ', ' Myra Fernando\n+   $22.66   + green&white&blue+09/15/17']


Our next step is to split each individual transaction into a list of its data points. To do this, we will use **For Loops** and **.split()** again to split up the "+" from each data point.


```python
# We will use For Loops and .splt() string function to split each individual transaction.

# Firstly, we will create an empty list to append our new data into it.
daily_transactions_split = []
# Next, we will use the For Loops to iterate through the daily_transaction list.
for transaction in daily_transactions:
    # Lastly, we will append the interated data to the empty daily_transaction_split after we use .split() on the "+"
    daily_transactions_split.append(transaction.split("+"))
        
print(daily_transactions_split)
```

    [['Lizanne   ', '$1.21   ', '   white ', ' \n09/15/17   '], ['Robert Tan   ', '   $7.29', ' \nwhite&blue', '   09/15/17 '], ['Garrett Tan ', '$12.52 \n', '   white&blue ', ' 09/15/17 '], ['Lucia Tan  \n', '   $5.13   ', ' white   ', ' 09/15/17'], ['\nEdmund Lee   ', '$20.39', ' white&yellow \n', '09/15/17   '], ['   Stacy Lim', '$30.82', '   \npurple ', '09/15/17 '], ['Verchelle', ' $1.85   ', ' \npurple&yellow ', '09/15/17'], ['   Shaun ', ' \n$17.98', 'purple&yellow ', ' 09/15/17 '], [' \nErick ', '$17.41', ' blue ', ' 09/15/17'], [' \nMichelle  ', '$28.59', ' blue', '   09/15/17   '], [' \nCarrolyn ', ' $14.51', '   purple&blue   ', '   \n09/15/17   '], [' Teresa    ', ' $19.64 ', ' \nwhite', '09/15/17   '], ['   Jacob  ', ' $11.40   \n', ' white&red   ', ' 09/15/17'], [' Cramery ', ' \n$8.79 ', ' white&blue&red   ', '09/15/17   '], [' \nPeggy Soh', ' $8.65 ', 'blue   ', ' 09/15/17'], ['   Kenneth  ', '   $10.53', '   green&blue   ', ' \n09/15/17   '], ['   Marvin ', '   $16.49', ' \ngreen&blue&red   ', '   09/15/17 '], [' Russell \n', ' $6.55 ', '   green&blue&red', '   09/15/17 '], ['\nIsmail', '   $11.86   ', 'black', '  \n09/15/17'], ['   June   ', '   $22.29 ', '  \nblack&yellow ', '09/15/17 '], [' Jaime   ', '   \n$8.35', '   white&black&yellow   ', '   09/15/17'], ['   \nRhonda ', '$2.91 ', '   white&black&yellow   \n', '09/15/17'], [' Darren  ', '$22.94', 'green \n', '09/15/17'], [' Malone', '$4.70   ', ' green&yellow \n', ' 09/15/17   '], [' Miles', '   $3.59   \n', 'green&yellow&blue', '   09/15/17   '], [' Joseph   ', '$5.66   ', ' green&yellow&purple&blue \n', '   09/15/17 '], [' Samantha  ', '$17.51   ', '   \nblack   ', '   09/15/17 '], [' Audrey  ', ' \n$5.54', 'black&blue   ', '09/15/17 '], [' William ', ' \n$17.13', ' black&blue', '   09/15/17'], ['   Randy ', '   $21.13 ', 'black ', '09/15/17 '], ['Elissa ', ' $0.35   ', ' black&purple', '   09/15/17   '], ['\nErnest ', ' $13.91   ', '   black&purple ', '   \n09/15/17'], ['   Shannon    ', '$19.26   ', ' \nyellow', ' 09/15/17   '], [' Sammy Koh', ' $5.45', '   \nyellow&red ', '09/15/17 '], ['   Steven Roh ', '$5.50   \n', '   yellow', '   09/15/17'], [' Ruben Ee   ', ' \n$14.56 ', '   yellow&blue', '09/15/17 '], [' Esmae Ping', '   $7.33   ', '   yellow&blue&red\n', ' 09/15/17   '], ['   Rene Hardy   ', ' $20.22   ', ' \nblack ', '   09/15/17 '], ['   Lucy Ng   ', ' $8.67   \n', 'black&red  ', ' 09/15/17 '], ['Damien Tan ', '   \n$8.31', '   black&red ', '   09/15/17'], ['   Stacey Lim \n', '   $15.70   ', '   white&black&red ', '09/15/17   \n'], ['   Tanya Kim   ', '   $6.74   ', 'yellow   ', ' \n09/15/17 '], [' Melody Ho ', '   $30.84   \n', 'yellow&black', '   09/15/17 '], [' Louise    ', ' \n$12.31 ', ' green&yellow&black', '   09/15/17 '], ['\nRyan tan', '$2.94 ', ' yellow ', ' 09/15/17 \n'], ['Justin  ', ' $22.46   ', 'white&yellow ', '   \n09/15/17'], ['   Benendict ', '   $6.60', '   \nwhite&yellow&black ', '09/15/17   '], ['   Dorathy  \n', '   $6.27 ', ' yellow   ', '09/15/17 '], [' Potter ', '$21.12   ', ' yellow', ' 09/15/17   '], [' \nDesiree Loh ', '$2.10   ', 'white', ' 09/15/17  \n'], [' Garnett ', ' $14.22 ', 'white&black', '   \n09/15/17'], [' Angelica ', '$11.60', 'white&black   \n', '   09/15/17   '], ['   Jamie Seah   ', ' $25.27   ', ' \nwhite&black&red ', '09/15/17   '], ['   Randy Poh   \n', '$8.26', '   purple', ' 09/15/17 '], ['   Nadia \n', '   $30.80 ', '   purple&yellow   ', ' 09/15/17   '], [' \nHannah ', '   $22.61   ', '   purple&yellow   \n', '09/15/17'], [' Richard', '$22.19 ', ' \ngreen&purple&yellow ', '09/15/17   '], ['Stanley  \n', ' $7.47   ', ' red ', ' 09/15/17 '], [' Anna ', '$5.49 ', ' yellow&red ', '   09/15/17   '], ['\nTerrance Sim ', '   $23.70  ', 'green&yellow&red \n', ' 09/15/17 '], ['   Brandon ', ' $26.66 ', ' \nred   ', '09/15/17 '], [' Morgan Freeman ', ' $25.95', ' \ngreen&red ', '   09/15/17   '], ['Irvin Hu \n', '$19.55 ', ' green&white&red ', '   09/15/17 '], [' Ross Lynch', '   $15.68', '   white ', '   09/15/17 '], [' Brandy Fu ', '$23.57', '   white&red   ', '09/15/17'], [' \n Riley   ', '$29.32', ' purple', '09/15/17 '], ['Mike    ', ' $26.44 ', '   purple   ', ' 09/15/17'], [' \nJamie    ', ' $17.24', 'green ', ' 09/15/17   '], [' \nNoah  ', '   $8.49   ', 'green   ', '09/15/17   \n'], ['Josephine Lim ', '$13.10 ', 'green', '   09/15/17 '], ['   Tracey ', '$20.39 ', ' red   ', ' 09/15/17 '], ['\nIgnacio Parks', '$14.70   ', ' white&red ', '09/15/17 \n'], [' Beatrice  ', '$22.45   ', 'white&purple&red \n', '   09/15/17'], [' Andre    ', '   $28.46   ', '   \nred', '   09/15/17 '], ['   Albert  ', ' $23.89', '   \nblack&red', ' 09/15/17'], ['   Javier    ', '   \n$24.49   ', ' black&red ', ' 09/15/17   '], [' Everett  ', '$1.81', '   black&red ', ' 09/15/17 '], ['   \nAbraham ', ' $6.81   ', 'green', '   09/15/17   \n'], ['   Traci  ', '$0.65', ' green&yellow', ' \n09/15/17 '], [' Jeffrey Seah   ', '$26.45', ' \ngreen&yellow&blue   ', '   09/15/17'], ['    Wilson \n', '   $7.69 ', ' purple', ' 09/15/17'], ['Janice   \n', '$8.74   ', ' purple&black   ', '09/15/17 '], ['  \nLeonard  ', '   $1.86   ', 'yellow  \n', '09/15/17'], ['Sanchez', '$14.75   ', ' yellow', '   \n09/15/17   '], ['Donna ', ' $28.10  ', ' \nyellow&blue', '   09/15/17   '], [' Terrence   ', ' \n$9.91   ', ' green ', '09/15/17   '], ['Jody ', ' \n$16.34 ', ' green ', '   09/15/17'], ['   Daryl  \n', '$27.57', ' white', '   09/15/17   '], [' Miguel ', '$5.25', ' white&blue   ', '   09/15/17 '], ['   \n Gonzalez', ' $9.51', '   white&black&blue   \n', '   09/15/17   '], ['   Lora  ', '$20.56 ', ' \ngreen', '   09/15/17'], ['Owena He ', ' $21.64   ', '   \ngreen&yellow', '09/15/17'], ['Malcolm  ', '   \n$24.99   ', '   green&yellow&black', ' 09/15/17 '], ['   \nEric  ', '$29.70', ' green ', ' 09/15/17 \n'], ['Madeline ', '   $15.52', 'green', '   09/15/17 \n'], [' Leticia  ', '$15.70 ', ' green&purple', ' \n09/15/17 '], ['   Mario  ', ' $12.36 ', 'green ', ' \n09/15/17'], ['Lewis ', '   $13.66   ', '   \ngreen&white', '09/15/17'], ['    Phelps Ng   ', '$30.52   \n', ' green&white&blue   ', ' 09/15/17 '], [' Myra Fernando\n', '   $22.66   ', ' green&white&blue', '09/15/17']]


Now, it looks like our data item has **inconsistent whitespace and newline (\n)** around it. To remove these really annoying spaces that we don't need, we will have to use For Loops iterate through daily_transactions_split. For each transaction, we will use For Loops again to iterate through the different data points and use .replace() to replace the /n to whitespaces and .strip() to remove all the unecessary whitespaces. I will show you what I mean. LETS GO!


```python
# We will use For Loops and .splt() string function to split each individual transaction.

# Firstly, we will create an empty list to append our new data into it.
clean_transactions = []
# Next, we will use the For Loops to iterate through the daily_transaction_split list
for transaction in daily_transactions_split:
    transaction_clean = []
    for data_points in transaction:
        # We use use .replace() to replace the /n to whitespaces and .strip() to remove all the unecessary whitespaces 
        transaction_clean.append(data_points.replace("\n", "").strip(" "))
    clean_transactions.append(transaction_clean)

print(clean_transactions)
```

    [['Lizanne', '$1.21', 'white', '09/15/17'], ['Robert Tan', '$7.29', 'white&blue', '09/15/17'], ['Garrett Tan', '$12.52', 'white&blue', '09/15/17'], ['Lucia Tan', '$5.13', 'white', '09/15/17'], ['Edmund Lee', '$20.39', 'white&yellow', '09/15/17'], ['Stacy Lim', '$30.82', 'purple', '09/15/17'], ['Verchelle', '$1.85', 'purple&yellow', '09/15/17'], ['Shaun', '$17.98', 'purple&yellow', '09/15/17'], ['Erick', '$17.41', 'blue', '09/15/17'], ['Michelle', '$28.59', 'blue', '09/15/17'], ['Carrolyn', '$14.51', 'purple&blue', '09/15/17'], ['Teresa', '$19.64', 'white', '09/15/17'], ['Jacob', '$11.40', 'white&red', '09/15/17'], ['Cramery', '$8.79', 'white&blue&red', '09/15/17'], ['Peggy Soh', '$8.65', 'blue', '09/15/17'], ['Kenneth', '$10.53', 'green&blue', '09/15/17'], ['Marvin', '$16.49', 'green&blue&red', '09/15/17'], ['Russell', '$6.55', 'green&blue&red', '09/15/17'], ['Ismail', '$11.86', 'black', '09/15/17'], ['June', '$22.29', 'black&yellow', '09/15/17'], ['Jaime', '$8.35', 'white&black&yellow', '09/15/17'], ['Rhonda', '$2.91', 'white&black&yellow', '09/15/17'], ['Darren', '$22.94', 'green', '09/15/17'], ['Malone', '$4.70', 'green&yellow', '09/15/17'], ['Miles', '$3.59', 'green&yellow&blue', '09/15/17'], ['Joseph', '$5.66', 'green&yellow&purple&blue', '09/15/17'], ['Samantha', '$17.51', 'black', '09/15/17'], ['Audrey', '$5.54', 'black&blue', '09/15/17'], ['William', '$17.13', 'black&blue', '09/15/17'], ['Randy', '$21.13', 'black', '09/15/17'], ['Elissa', '$0.35', 'black&purple', '09/15/17'], ['Ernest', '$13.91', 'black&purple', '09/15/17'], ['Shannon', '$19.26', 'yellow', '09/15/17'], ['Sammy Koh', '$5.45', 'yellow&red', '09/15/17'], ['Steven Roh', '$5.50', 'yellow', '09/15/17'], ['Ruben Ee', '$14.56', 'yellow&blue', '09/15/17'], ['Esmae Ping', '$7.33', 'yellow&blue&red', '09/15/17'], ['Rene Hardy', '$20.22', 'black', '09/15/17'], ['Lucy Ng', '$8.67', 'black&red', '09/15/17'], ['Damien Tan', '$8.31', 'black&red', '09/15/17'], ['Stacey Lim', '$15.70', 'white&black&red', '09/15/17'], ['Tanya Kim', '$6.74', 'yellow', '09/15/17'], ['Melody Ho', '$30.84', 'yellow&black', '09/15/17'], ['Louise', '$12.31', 'green&yellow&black', '09/15/17'], ['Ryan tan', '$2.94', 'yellow', '09/15/17'], ['Justin', '$22.46', 'white&yellow', '09/15/17'], ['Benendict', '$6.60', 'white&yellow&black', '09/15/17'], ['Dorathy', '$6.27', 'yellow', '09/15/17'], ['Potter', '$21.12', 'yellow', '09/15/17'], ['Desiree Loh', '$2.10', 'white', '09/15/17'], ['Garnett', '$14.22', 'white&black', '09/15/17'], ['Angelica', '$11.60', 'white&black', '09/15/17'], ['Jamie Seah', '$25.27', 'white&black&red', '09/15/17'], ['Randy Poh', '$8.26', 'purple', '09/15/17'], ['Nadia', '$30.80', 'purple&yellow', '09/15/17'], ['Hannah', '$22.61', 'purple&yellow', '09/15/17'], ['Richard', '$22.19', 'green&purple&yellow', '09/15/17'], ['Stanley', '$7.47', 'red', '09/15/17'], ['Anna', '$5.49', 'yellow&red', '09/15/17'], ['Terrance Sim', '$23.70', 'green&yellow&red', '09/15/17'], ['Brandon', '$26.66', 'red', '09/15/17'], ['Morgan Freeman', '$25.95', 'green&red', '09/15/17'], ['Irvin Hu', '$19.55', 'green&white&red', '09/15/17'], ['Ross Lynch', '$15.68', 'white', '09/15/17'], ['Brandy Fu', '$23.57', 'white&red', '09/15/17'], ['Riley', '$29.32', 'purple', '09/15/17'], ['Mike', '$26.44', 'purple', '09/15/17'], ['Jamie', '$17.24', 'green', '09/15/17'], ['Noah', '$8.49', 'green', '09/15/17'], ['Josephine Lim', '$13.10', 'green', '09/15/17'], ['Tracey', '$20.39', 'red', '09/15/17'], ['Ignacio Parks', '$14.70', 'white&red', '09/15/17'], ['Beatrice', '$22.45', 'white&purple&red', '09/15/17'], ['Andre', '$28.46', 'red', '09/15/17'], ['Albert', '$23.89', 'black&red', '09/15/17'], ['Javier', '$24.49', 'black&red', '09/15/17'], ['Everett', '$1.81', 'black&red', '09/15/17'], ['Abraham', '$6.81', 'green', '09/15/17'], ['Traci', '$0.65', 'green&yellow', '09/15/17'], ['Jeffrey Seah', '$26.45', 'green&yellow&blue', '09/15/17'], ['Wilson', '$7.69', 'purple', '09/15/17'], ['Janice', '$8.74', 'purple&black', '09/15/17'], ['Leonard', '$1.86', 'yellow', '09/15/17'], ['Sanchez', '$14.75', 'yellow', '09/15/17'], ['Donna', '$28.10', 'yellow&blue', '09/15/17'], ['Terrence', '$9.91', 'green', '09/15/17'], ['Jody', '$16.34', 'green', '09/15/17'], ['Daryl', '$27.57', 'white', '09/15/17'], ['Miguel', '$5.25', 'white&blue', '09/15/17'], ['Gonzalez', '$9.51', 'white&black&blue', '09/15/17'], ['Lora', '$20.56', 'green', '09/15/17'], ['Owena He', '$21.64', 'green&yellow', '09/15/17'], ['Malcolm', '$24.99', 'green&yellow&black', '09/15/17'], ['Eric', '$29.70', 'green', '09/15/17'], ['Madeline', '$15.52', 'green', '09/15/17'], ['Leticia', '$15.70', 'green&purple', '09/15/17'], ['Mario', '$12.36', 'green', '09/15/17'], ['Lewis', '$13.66', 'green&white', '09/15/17'], ['Phelps Ng', '$30.52', 'green&white&blue', '09/15/17'], ['Myra Fernando', '$22.66', 'green&white&blue', '09/15/17']]


#### After much effort, we have finally converted the initial list that we have to something more readable. **Hurray!!!!**

Before we continue to celebrate, lets not forget why we're doing this today. We'll need to help my god-grandmother with these tasks:

1. Keeping track of the name of our customers 
2. Calculating the total amount of money made
3. Tallying number of transactions for the day 
4. Number of fabrics sold

To accomplish the three tasks above, we will first need to create an empty list for each of the different categories.


```python
customer_names = []
sales = []
fabric_sold = []

# We will now seperate the data points from clean_transactions and append it into their respective lists. 
# Using For Loops will allow us to do this! 

for data_point in clean_transactions:
    customer_names.append(data_point[0])
    sales.append(data_point[1])
    fabric_sold.append(data_point[2])

print(customer_names) # Task 1 accomplished!! 
print(sales)
print(fabric_sold)

# We can now see that the data has been seperated into their respective lists.

```

    ['Lizanne', 'Robert Tan', 'Garrett Tan', 'Lucia Tan', 'Edmund Lee', 'Stacy Lim', 'Verchelle', 'Shaun', 'Erick', 'Michelle', 'Carrolyn', 'Teresa', 'Jacob', 'Cramery', 'Peggy Soh', 'Kenneth', 'Marvin', 'Russell', 'Ismail', 'June', 'Jaime', 'Rhonda', 'Darren', 'Malone', 'Miles', 'Joseph', 'Samantha', 'Audrey', 'William', 'Randy', 'Elissa', 'Ernest', 'Shannon', 'Sammy Koh', 'Steven Roh', 'Ruben Ee', 'Esmae Ping', 'Rene Hardy', 'Lucy Ng', 'Damien Tan', 'Stacey Lim', 'Tanya Kim', 'Melody Ho', 'Louise', 'Ryan tan', 'Justin', 'Benendict', 'Dorathy', 'Potter', 'Desiree Loh', 'Garnett', 'Angelica', 'Jamie Seah', 'Randy Poh', 'Nadia', 'Hannah', 'Richard', 'Stanley', 'Anna', 'Terrance Sim', 'Brandon', 'Morgan Freeman', 'Irvin Hu', 'Ross Lynch', 'Brandy Fu', 'Riley', 'Mike', 'Jamie', 'Noah', 'Josephine Lim', 'Tracey', 'Ignacio Parks', 'Beatrice', 'Andre', 'Albert', 'Javier', 'Everett', 'Abraham', 'Traci', 'Jeffrey Seah', 'Wilson', 'Janice', 'Leonard', 'Sanchez', 'Donna', 'Terrence', 'Jody', 'Daryl', 'Miguel', 'Gonzalez', 'Lora', 'Owena He', 'Malcolm', 'Eric', 'Madeline', 'Leticia', 'Mario', 'Lewis', 'Phelps Ng', 'Myra Fernando']
    ['$1.21', '$7.29', '$12.52', '$5.13', '$20.39', '$30.82', '$1.85', '$17.98', '$17.41', '$28.59', '$14.51', '$19.64', '$11.40', '$8.79', '$8.65', '$10.53', '$16.49', '$6.55', '$11.86', '$22.29', '$8.35', '$2.91', '$22.94', '$4.70', '$3.59', '$5.66', '$17.51', '$5.54', '$17.13', '$21.13', '$0.35', '$13.91', '$19.26', '$5.45', '$5.50', '$14.56', '$7.33', '$20.22', '$8.67', '$8.31', '$15.70', '$6.74', '$30.84', '$12.31', '$2.94', '$22.46', '$6.60', '$6.27', '$21.12', '$2.10', '$14.22', '$11.60', '$25.27', '$8.26', '$30.80', '$22.61', '$22.19', '$7.47', '$5.49', '$23.70', '$26.66', '$25.95', '$19.55', '$15.68', '$23.57', '$29.32', '$26.44', '$17.24', '$8.49', '$13.10', '$20.39', '$14.70', '$22.45', '$28.46', '$23.89', '$24.49', '$1.81', '$6.81', '$0.65', '$26.45', '$7.69', '$8.74', '$1.86', '$14.75', '$28.10', '$9.91', '$16.34', '$27.57', '$5.25', '$9.51', '$20.56', '$21.64', '$24.99', '$29.70', '$15.52', '$15.70', '$12.36', '$13.66', '$30.52', '$22.66']
    ['white', 'white&blue', 'white&blue', 'white', 'white&yellow', 'purple', 'purple&yellow', 'purple&yellow', 'blue', 'blue', 'purple&blue', 'white', 'white&red', 'white&blue&red', 'blue', 'green&blue', 'green&blue&red', 'green&blue&red', 'black', 'black&yellow', 'white&black&yellow', 'white&black&yellow', 'green', 'green&yellow', 'green&yellow&blue', 'green&yellow&purple&blue', 'black', 'black&blue', 'black&blue', 'black', 'black&purple', 'black&purple', 'yellow', 'yellow&red', 'yellow', 'yellow&blue', 'yellow&blue&red', 'black', 'black&red', 'black&red', 'white&black&red', 'yellow', 'yellow&black', 'green&yellow&black', 'yellow', 'white&yellow', 'white&yellow&black', 'yellow', 'yellow', 'white', 'white&black', 'white&black', 'white&black&red', 'purple', 'purple&yellow', 'purple&yellow', 'green&purple&yellow', 'red', 'yellow&red', 'green&yellow&red', 'red', 'green&red', 'green&white&red', 'white', 'white&red', 'purple', 'purple', 'green', 'green', 'green', 'red', 'white&red', 'white&purple&red', 'red', 'black&red', 'black&red', 'black&red', 'green', 'green&yellow', 'green&yellow&blue', 'purple', 'purple&black', 'yellow', 'yellow', 'yellow&blue', 'green', 'green', 'white', 'white&blue', 'white&black&blue', 'green', 'green&yellow', 'green&yellow&black', 'green', 'green', 'green&purple', 'green', 'green&white', 'green&white&blue', 'green&white&blue']


### Task 1 : Keeping Track of our Customer's name:


```python
# To look at all of our customer's names, we will simply print out the customer_name list

print(customer_names)

# Task 1 ACCOMPLISHED!!!
```

    ['Lizanne', 'Robert Tan', 'Garrett Tan', 'Lucia Tan', 'Edmund Lee', 'Stacy Lim', 'Verchelle', 'Shaun', 'Erick', 'Michelle', 'Carrolyn', 'Teresa', 'Jacob', 'Cramery', 'Peggy Soh', 'Kenneth', 'Marvin', 'Russell', 'Ismail', 'June', 'Jaime', 'Rhonda', 'Darren', 'Malone', 'Miles', 'Joseph', 'Samantha', 'Audrey', 'William', 'Randy', 'Elissa', 'Ernest', 'Shannon', 'Sammy Koh', 'Steven Roh', 'Ruben Ee', 'Esmae Ping', 'Rene Hardy', 'Lucy Ng', 'Damien Tan', 'Stacey Lim', 'Tanya Kim', 'Melody Ho', 'Louise', 'Ryan tan', 'Justin', 'Benendict', 'Dorathy', 'Potter', 'Desiree Loh', 'Garnett', 'Angelica', 'Jamie Seah', 'Randy Poh', 'Nadia', 'Hannah', 'Richard', 'Stanley', 'Anna', 'Terrance Sim', 'Brandon', 'Morgan Freeman', 'Irvin Hu', 'Ross Lynch', 'Brandy Fu', 'Riley', 'Mike', 'Jamie', 'Noah', 'Josephine Lim', 'Tracey', 'Ignacio Parks', 'Beatrice', 'Andre', 'Albert', 'Javier', 'Everett', 'Abraham', 'Traci', 'Jeffrey Seah', 'Wilson', 'Janice', 'Leonard', 'Sanchez', 'Donna', 'Terrence', 'Jody', 'Daryl', 'Miguel', 'Gonzalez', 'Lora', 'Owena He', 'Malcolm', 'Eric', 'Madeline', 'Leticia', 'Mario', 'Lewis', 'Phelps Ng', 'Myra Fernando']


### Task 2 : Calculating the Total Amount of Money Made

If you noticed, there is the dollar sign [$] and we won't be able to sum the total sales up till we remove it. To do this, we will have to convert the int into a float and use the .strip() string function to remove it.


```python
total_sales = 0

for sale in sales:
    # We convert the int into a float and use the .strip() string function to remove the dollar sign "$"
    total_sales += float(sale.strip("$"))

print("Total Sales for the day is: $" + str(total_sales))

# Task 2 ACCOMPLISHED!!!
```

    Total Sales for the day is: $1498.7400000000005


### Task 3 : Tallying number of Sales for the day

We can simply do this by using len() to find out the number of transactions regardless of name and price.


```python
num_of_transactions = len(sales)
print("Total Number of transactions is:", num_of_transactions)

# Task 3 ACCOMPLISHED!!!
```

    Total Number of transactions is: 100


### Task 4 : Number of Fabrics Sold for each Color

We want to determine how many of each color thread we sold today. Let’s start with a single color, and then we’ll generalize it. We can see that fabric_sold is a list of strings, some are single colors and some are multiple colors separated by the "&" character. We will remove the "&" using the .split() string function.


```python
fabric_sold_split = []
for fabric in fabric_sold:
    for color in fabric.split("&"):
        fabric_sold_split.append(color)
        
print(fabric_sold_split)
```

    ['white', 'white', 'blue', 'white', 'blue', 'white', 'white', 'yellow', 'purple', 'purple', 'yellow', 'purple', 'yellow', 'blue', 'blue', 'purple', 'blue', 'white', 'white', 'red', 'white', 'blue', 'red', 'blue', 'green', 'blue', 'green', 'blue', 'red', 'green', 'blue', 'red', 'black', 'black', 'yellow', 'white', 'black', 'yellow', 'white', 'black', 'yellow', 'green', 'green', 'yellow', 'green', 'yellow', 'blue', 'green', 'yellow', 'purple', 'blue', 'black', 'black', 'blue', 'black', 'blue', 'black', 'black', 'purple', 'black', 'purple', 'yellow', 'yellow', 'red', 'yellow', 'yellow', 'blue', 'yellow', 'blue', 'red', 'black', 'black', 'red', 'black', 'red', 'white', 'black', 'red', 'yellow', 'yellow', 'black', 'green', 'yellow', 'black', 'yellow', 'white', 'yellow', 'white', 'yellow', 'black', 'yellow', 'yellow', 'white', 'white', 'black', 'white', 'black', 'white', 'black', 'red', 'purple', 'purple', 'yellow', 'purple', 'yellow', 'green', 'purple', 'yellow', 'red', 'yellow', 'red', 'green', 'yellow', 'red', 'red', 'green', 'red', 'green', 'white', 'red', 'white', 'white', 'red', 'purple', 'purple', 'green', 'green', 'green', 'red', 'white', 'red', 'white', 'purple', 'red', 'red', 'black', 'red', 'black', 'red', 'black', 'red', 'green', 'green', 'yellow', 'green', 'yellow', 'blue', 'purple', 'purple', 'black', 'yellow', 'yellow', 'yellow', 'blue', 'green', 'green', 'white', 'white', 'blue', 'white', 'black', 'blue', 'green', 'green', 'yellow', 'green', 'yellow', 'black', 'green', 'green', 'green', 'purple', 'green', 'green', 'white', 'green', 'white', 'blue', 'green', 'white', 'blue']


With all the colors being seperated from each other, we can finally COUNT them!! However, instead of using .count(), we can ease this process by utilizing FUNCTIONS (def). Lets go ahead and try it out!


```python

# This list contains all the colors that are in the fabric_sold_split list so that we can iterate through it
colors = ['red','yellow','green','white','black','blue','purple']

def color_count(fabric_color):
    color_total = 0
    for color in fabric_sold_split:
        if fabric_color == color:
            color_total += 1
    return color_total
```


```python
# Instead of individually printing each color count, we can use For Loops and .format() to help us.

for fabric_color in colors:
    print(
        "Hello ahma! Today, your store sold {0} rolls of {1} colored fabric. Well done!".format(color_count(fabric_color), fabric_color)
        )

# Task 4 ACCOMPLISHED!!!
```

    Hello ahma! Today, your store sold 24 rolls of red colored fabric. Well done!
    Hello ahma! Today, your store sold 34 rolls of yellow colored fabric. Well done!
    Hello ahma! Today, your store sold 30 rolls of green colored fabric. Well done!
    Hello ahma! Today, your store sold 28 rolls of white colored fabric. Well done!
    Hello ahma! Today, your store sold 26 rolls of black colored fabric. Well done!
    Hello ahma! Today, your store sold 22 rolls of blue colored fabric. Well done!
    Hello ahma! Today, your store sold 17 rolls of purple colored fabric. Well done!


I hope that you enjoyed this mini project that I did to help ease the calculation portion for my god-grandmother. (sort of) I thoroughly enjoyed this mini-project as I this made my god-grandmother smile like crazy (she doesn't know what Python is, but I guess she's happy that I tried to help her).

Alright, enough of me talking! Stay safe, have fun and happy coding! 


