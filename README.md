# -utl-creating-a-crosstab-dataset-that-looks-like-proc-freq-printed-
Create a SAS dataset that looks like proc freq outptut 
    Problem: Create a SAS dataset that looks like proc freq outptut                                                                     
                                                                                                                                        
    SOAPBOX ON                                                                                                                          
      SAS needs fix ODS so it honors all listing output                                                                                 
      Or rename ODS SODS(Sometimes Output Delivering Sysyem)                                                                            
      Fails with 'proc report' and 'proc tabulate'                                                                                      
    SOAPBOX OFF                                                                                                                         
                                                                                                                                        
    SAS forum                                                                                                                           
    https://tinyurl.com/yxseg74k                                                                                                        
    https://communities.sas.com/t5/SAS-Procedures/Proc-freq-equivalent-in-Proc-report/m-p/580114                                        
                                                                                                                                        
    *    _           _                                                                                                                  
      __| | ___  ___(_)_ __ ___                                                                                                         
     / _` |/ _ \/ __| | '__/ _ \                                                                                                        
    | (_| |  __/\__ \ | | |  __/                                                                                                        
     \__,_|\___||___/_|_|  \___|                                                                                                        
                                                                                                                                        
    ;                                                                                                                                   
                                                                                                                                        
    * Want output dataset that looks like the fre=q output below;                                                                       
                                                                                                                                        
    proc freq data=sashelp.shoes ;                                                                                                      
    tables region * product/ nocol nocum nopercent;                                                                                     
    run;                                                                                                                                
                                                                                                                                        
    Table of REGION by PRODUCT                                                                                                          
                                                                                                                                        
    REGION            PRODUCT                                                                                                           
                                                                                                                                        
    Frequency        |                                                                                                                  
    Row Pct          |Boot    |Men's Ca|Men's Dr|Sandal  |Slipper |Sport Sh|Women's |Women's |  Total                                   
                     |        |sual    |ess     |        |        |oe      |Casual  |Dress   |                                          
    -----------------+--------+--------+--------+--------+--------+--------+--------+--------+                                          
    Africa           |      8 |      5 |      7 |      8 |      8 |      8 |      4 |      8 |     56                                   
                     |  14.29 |   8.93 |  12.50 |  14.29 |  14.29 |  14.29 |   7.14 |  14.29 |                                          
    -----------------+--------+--------+--------+--------+--------+--------+--------+--------+                                          
    Asia             |      2 |      1 |      2 |      2 |      2 |      2 |      2 |      1 |     14                                   
                     |  14.29 |   7.14 |  14.29 |  14.29 |  14.29 |  14.29 |  14.29 |   7.14 |                                          
    -----------------+--------+--------+--------+--------+--------+--------+--------+--------+                                          
                                                                                                                                        
    *                    _                                                                                                              
    __      ____ _ _ __ | |_                                                                                                            
    \ \ /\ / / _` | '_ \| __|                                                                                                           
     \ V  V / (_| | | | | |_                                                                                                            
      \_/\_/ \__,_|_| |_|\__|                                                                                                           
                                                                                                                                        
    ;                                                                                                                                   
                                                                                                                                        
    WORK.WANT total obs=21                                                                                                              
                                                                                                                                        
                                            MEN_S_    MEN_S_                         SPORT_    WOMEN_S_    WOMEN_S_                     
     LABEL                          BOOT    CASUAL    DRESS     SANDAL    SLIPPER     SHOE      CASUAL      DRESS       SUM             
                                                                                                                                        
     Africa_cnt                      8.0      5.0       7.0       8.0       8.0        8.0        4.0         8.0       56.0            
     Africa_pct                     14.3      8.9      12.5      14.3      14.3       14.3        7.1        14.3      100.0            
     Asia_cnt                        2.0      1.0       2.0       2.0       2.0        2.0        2.0         1.0       14.0            
     Asia_pct                       14.3      7.1      14.3      14.3      14.3       14.3       14.3         7.1      100.0            
     Canada_cnt                      5.0      4.0       4.0       5.0       5.0        5.0        4.0         5.0       37.0            
     Canada_pct                     13.5     10.8      10.8      13.5      13.5       13.5       10.8        13.5      100.0            
     Central America/Caribbean_cnt   4.0      4.0       4.0       4.0       4.0        4.0        4.0         4.0       32.0            
     Central America/Caribbean_pct  12.5     12.5      12.5      12.5      12.5       12.5       12.5        12.5      100.0            
     Eastern Europe_cnt              4.0      4.0       4.0       3.0       4.0        4.0        4.0         4.0       31.0            
     Eastern Europe_pct             12.9     12.9      12.9       9.7      12.9       12.9       12.9        12.9      100.0            
     Middle East_cnt                 3.0      3.0       3.0       3.0       3.0        3.0        3.0         3.0       24.0            
     Middle East_pct                12.5     12.5      12.5      12.5      12.5       12.5       12.5        12.5      100.0            
     Pacific_cnt                     6.0      5.0       6.0       6.0       6.0        5.0        5.0         6.0       45.0            
     Pacific_pct                    13.3     11.1      13.3      13.3      13.3       11.1       11.1        13.3      100.0            
     South America_cnt               7.0      6.0       7.0       7.0       7.0        7.0        6.0         7.0       54.0            
     South America_pct              13.0     11.1      13.0      13.0      13.0       13.0       11.1        13.0      100.0            
     United States_cnt               5.0      5.0       5.0       5.0       5.0        5.0        5.0         5.0       40.0            
     United States_pct              12.5     12.5      12.5      12.5      12.5       12.5       12.5        12.5      100.0            
     Western Europe_cnt              8.0      8.0       8.0       6.0       8.0        8.0        8.0         8.0       62.0            
     Western Europe_pct             12.9     12.9      12.9       9.7      12.9       12.9       12.9        12.9      100.0            
     Sum_cnt                        52.0     45.0      50.0      49.0      52.0       51.0       45.0        51.0      395.0            
                                                                                                                                        
    *          _       _   _                                                                                                            
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                                 
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                                
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                               
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                               
                                                                                                                                        
    ;                                                                                                                                   
                                                                                                                                        
    proc corresp data=sashelp.shoes;                                                                                                    
                                                                                                                                        
    ods exclude all;                                                                                                                    
    ods output rowprofilespct=wantpct ;                                                                                                 
    ods output observed=wantcnt;                                                                                                        
    proc corresp data=sashelp.shoes dim=1 observed missing all print=both;;                                                             
    tables region, product;                                                                                                             
    run;quit;                                                                                                                           
    ods select all;                                                                                                                     
                                                                                                                                        
    proc datasets lib=work;                                                                                                             
     delete want;                                                                                                                       
    run;quit;                                                                                                                           
                                                                                                                                        
    data want / view=want;                                                                                                              
       set wantcnt;label=cats(label,'_cnt');output;                                                                                     
       set wantpct;label=cats(label,'_pct');sum=100;output;                                                                             
       format _numeric_ 7.1;                                                                                                            
    run;quit;                                                                                                                           
                                                                                                                                        
                                                                                                                                        
