# utl-solving-a-simple-and-complex-non-linear-equation-using-python-and-r
Solving a simple and complex non linear equation using python and R

    Solving a simple and complex non linear equation using python and R                                                           
                                                                                                                                  
      Two solutions for two different problems                                                                                    
                                                                                                                                  
           1. Numerical non-linear problem  (solve for MEAN(mean of a density?) because we have a grid of (x,y) to search over)   
                                                                                                                                  
               SOLVE FOR MEAN                                                                                                     
                                                                                                                                  
                    10                                                                                                            
                +------ +                                                                                                         
                \                                                                                                                 
                 \                                                        ___                                                     
                  \           (2*exp(-xi)-1) * (2*exp(-yi)-1)            / _ \                                                    
                  /    --------------------------------------------  =  | | | |                                                   
                 /     1 + MEAN * [(2*exp(-xi)-1) * (2*exp(-yi)-1)]     | |_| |                                                   
                /          ****                                          \___/                                                    
                +------+                                                                                                          
                  i=1                                                                                                             
                                                                                                                                  
           2. symPy solve 1- x**2/(1-x)**2 = 0  (find the roots)                                                                  
              symPy can do much more comples problems (but not as many as a numerical technique)                                  
                                                                                                                                  
                                                                                                                                  
    github                                                                                                                        
    http://tinyurl.com/y4nwwngf                                                                                                   
    https://github.com/rogerjdeangelis/utl-solving-a-simple-and-complex-non-linear-equation-using-python-and-r                    
                                                                                                                                  
    http://tinyurl.com/yxh7ma4l                                                                                                   
    https://stackoverflow.com/questions/44438646/solve-a-non-linear-equation-of-one-variable-but-written-in-a-summation-form-in   
                                                                                                                                  
    BHas profile                                                                                                                  
    https://stackoverflow.com/users/1119964/bhas                                                                                  
                                                                                                                                  
    Links to related repos                                                                                                        
                                                                                                                                  
    github                                                                                                                        
    https://tinyurl.com/y9em44x6                                                                                                  
    https://github.com/rogerjdeangelis/utl-sorting-the-roots-of-a-polynomial-in-ascending-order-of-the-imaginary-part             
                                                                                                                                  
    http://tinyurl.com/yydjaetr                                                                                                   
    https://github.com/rogerjdeangelis/utl_solving_a_system_of_nonlinear_equations                                                
                                                                                                                                  
    Sybolic calculus sympy repos                                                                                                  
    https://github.com/rogerjdeangelis?utf8=%E2%9C%93&tab=repositories&q=symPy+in%3Areadme&type=&language=                        
                                                                                                                                  
    Nonlinear or root solutions                                                                                                   
    https://github.com/rogerjdeangelis?utf8=%E2%9C%93&tab=repositories&q=solv+in%3Aname&type=&language=                           
                                                                                                                                  
    see github                                                                                                                    
    https://goo.gl/r1kjcN                                                                                                         
    https://github.com/rogerjdeangelis/utl_given_y_solve_for_x_in_y_equals_x_squared_divided_by_1_minus_x_squared                 
                                                                                                                                  
                                                                                                                                  
    *_                   _                                                                                                        
    (_)_ __  _ __  _   _| |_                                                                                                      
    | | '_ \| '_ \| | | | __|                                                                                                     
    | | | | | |_) | |_| | |_                                                                                                      
    |_|_| |_| .__/ \__,_|\__|                                                                                                     
            |_|                                                                                                                   
    ;                                                                                                                             
                                                                                                                                  
    -----------------------------------------------                                                                               
    1. Numerical non-linear problem solve for MEAN                                                                                
    -----------------------------------------------                                                                               
                                                                                                                                  
    The summation equation above and the (x,y) grid                                                                               
                                                                                                                                  
    options validvarname=upcase;                                                                                                  
    libname sd1 "d:/sd1";                                                                                                         
    data sd1.have;                                                                                                                
       input x y @@;                                                                                                              
    cards4;                                                                                                                       
    7.10322 3.30561 2.46137 4.39185 3.89634 4.45280 0.91384 2.83140 9.62065 2.96774                                               
    0.10933 1.82257 5.74295 1.78706 7.64398 2.95729 8.73382 4.32726 0.41063 3.40262                                               
    ;;;;                                                                                                                          
    run;quit;                                                                                                                     
                                                                                                                                  
    WORK.WANT total obs=10                                                                                                        
                                                                                                                                  
    Obs       X          Y                                                                                                        
                                                                                                                                  
      1    7.10322    3.30561                                                                                                     
      2    2.46137    4.39185                                                                                                     
      3    3.89634    4.45280                                                                                                     
      4    0.91384    2.83140                                                                                                     
      5    9.62065    2.96774                                                                                                     
      6    0.10933    1.82257                                                                                                     
      7    5.74295    1.78706                                                                                                     
      8    7.64398    2.95729                                                                                                     
      9    8.73382    4.32726                                                                                                     
     10    0.41063    3.40262                                                                                                     
                                                                                                                                  
                                                                                                                                  
    -----------------------------------------------------                                                                         
    2. symPy solve 1- x**2/(1-x)**2 = 0  (find the roots)                                                                         
    -----------------------------------------------------                                                                         
                                                                                                                                  
    Just the equation 1- x**2/(1-x)**2 = 0                                                                                        
                                                                                                                                  
     *            _               _                                                                                               
      ___  _   _| |_ _ __  _   _| |_                                                                                              
     / _ \| | | | __| '_ \| | | | __|                                                                                             
    | (_) | |_| | |_| |_) | |_| | |_                                                                                              
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                             
                    |_|                                                                                                           
    ;                                                                                                                             
                                                                                                                                  
    -----------------------------------------------                                                                               
    1. Numerical non-linear problem solve for MEAN                                                                                
    -----------------------------------------------                                                                               
                                                                                                                                  
    WORK.WANT total obs=1                                                                                                         
                                                                                                                                  
       MEAN     FVEC    TERMCD              MESSAGE               SCALEX    NFCNT    NJCNT    ITER                                
                                                                                                                                  
     1.42991      0        1      Function criterion near zero       1        7        1        7                                 
                                                                                                                                  
    CHECK IF substituting MEAN = 1.4299091071894 SUMS TO 0 WITH ADEQUATE CONVERGENCE                                              
                                                                                                                                  
    options validvarname=upcase;                                                                                                  
    libname sd1 "d:/sd1";                                                                                                         
    data check;                                                                                                                   
       retain convergence 0;                                                                                                      
       set sd1.have end=dne;                                                                                                      
       mean=1.4299091071894;                                                                                                      
       A = 2*exp(-x)-1;                                                                                                           
       B = 2*exp(-y)-1;                                                                                                           
       convergence= convergence + ((A*B)/(1+mean*A*B));                                                                           
       if dne then put mean= convergence=;                                                                                        
    run;quit;                                                                                                                     
                                                                                                                                  
    MEAN=1.4299091072 CONVERGENCE=2.3011759E-9                                                                                    
                                                                                                                                  
                                                                                                                                  
    -----------------------------------------------------                                                                         
    2. symPy solve 1- x**2/(1-x)**2 = 0  (find the roots)                                                                         
    -----------------------------------------------------                                                                         
                                                                                                                                  
      ROOT                                                                                                                        
      ----                                                                                                                        
                                                                                                                                  
      [1/2]                                                                                                                       
                                                                                                                                  
     This can be solved manually                                                                                                  
                                                                                                                                  
    *          _       _   _                                                                                                      
     ___  ___ | |_   _| |_(_) ___  _ __  ___                                                                                      
    / __|/ _ \| | | | | __| |/ _ \| '_ \/ __|                                                                                     
    \__ \ (_) | | |_| | |_| | (_) | | | \__ \                                                                                     
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|___/                                                                                     
                                                                                                                                  
    ;                                                                                                                             
                                                                                                                                  
                                                                                                                                  
    -----------------------------------------------                                                                               
    1. Numerical non-linear problem solve for MEAN                                                                                
    -----------------------------------------------                                                                               
                                                                                                                                  
    proc datasets lib=work;                                                                                                       
     delete want;                                                                                                                 
    run;quit;                                                                                                                     
                                                                                                                                  
    %utl_submit_r64('                                                                                                             
    library(nleqslv);                                                                                                             
    library(haven);                                                                                                               
    library(SASxport);                                                                                                            
    library(data.table);                                                                                                          
    have<-read_sas("d:/sd1/have.sas7bdat");                                                                                       
    have;                                                                                                                         
    f  function(MEAN){                                                                                                            
      A <- 2*exp(-have$X)-1;                                                                                                      
      B <- 2*exp(-have$Y)-1;                                                                                                      
      sum((A*B)/(1+MEAN*A*B));                                                                                                    
    };                                                                                                                            
    want<-as.data.table(nleqslv(0,f));                                                                                            
    write.xport(want,file="d:/xpt/want.xpt");                                                                                     
    ');                                                                                                                           
                                                                                                                                  
    libname xpt xport "d:/xpt/want.xpt";                                                                                          
    data want(rename=x=mean);                                                                                                     
      set xpt.want ;                                                                                                              
    run;quit;                                                                                                                     
    libname xpt clear;                                                                                                            
                                                                                                                                  
                                                                                                                                  
    -----------------------------------------------------                                                                         
    2. symPy solve 1- x**2/(1-x)**2 = 0  (find the roots)                                                                         
    -----------------------------------------------------                                                                         
                                                                                                                                  
    I like to try symPy first because it can give you either an closed form solution                                              
    or an infinite precision solution.                                                                                            
                                                                                                                                  
      Given                                                                                                                       
                                                                                                                                  
       y = ax**2/(1-x)**2                                                                                                         
                                                                                                                                  
       a=1                                                                                                                        
       y=1                                                                                                                        
                                                                                                                                  
      Calulate x for y=0 and a=1                                                                                                  
                                                                                                                                  
      This can be solved algebracally using sympy                                                                                 
                                                                                                                                  
      Here is the manual solution                                                                                                 
                                                                                                                                  
      1 - x**2/(1-x)**2                                                                                                           
                                                                                                                                  
      sqrt(1) = x/(1-x)                                                                                                           
       x = 1-x                                                                                                                    
       1=2*x                                                                                                                      
                                                                                                                                  
       x = 1/2                                                                                                                    
                                                                                                                                  
       * here is sympy solution;                                                                                                  
                                                                                                                                  
       %utl_submit_py64("                                                                                                         
       import pyperclip;                                                                                                          
       from sympy import *;                                                                                                       
       x, y, z = symbols('x y a');                                                                                                
       y=1;                                                                                                                       
       a=2;                                                                                                                       
       r=solve(y - x**2/((1-x)**2));                                                                                              
       print 'ROOT';                                                                                                              
       print  r;                                                                                                                  
       ");                                                                                                                        
                                                                                                                                  
                                                                                                                                  
       lets check  [1/2] = .5                                                                                                     
                                                                                                                                  
         1 - .5**2/(1-.5)**2  = 1 -1 =0                                                                                           
