## The complexity of methylation sequencing

```
          *
5' ATGATTGCGAAAATTGCGTTTAACG 3'              ref:  ATGATTGCGAAAATTGCGTTTAACG                              
   |||||||||||||||||||||||||              ref CT:  ATGATTGTGAAAATTGTGTTTAATG                                                           
3' TACTAACGCTTTTAACGCAAATTGC 5'           ref GA:  ATAATTACAAAAATTACATTTAACA                                                                                                                             
         *                                                             
|                                                                   
|  conversion C > T                                                             
V                                                                        
          *                                                                      
5' ATGATTGCGAAAATTGTGTTTAATG 3'                                                   
   |||||||||||||||||||||||||                                               
3' TATTAACGTTTTTAATGTAAATTGT 5'                                                             
         *                                                                           
|                                                                                 
|  1st PCR cycle                                    Generating reads from both:                       
V                                                   
          *                                                *                               R1:ATGATTGCGAAAATTGTGT                                               
5' ATGATTGCGAAAATTGTGTTTAATG 3' OT > CT          5' ATGATTGCGAAAATTGTGTTTAATG 3' OT > CT   R2:CATTAAACACAATTTTCGC                                                
   |||||||||||||||||||||||||                        |||||||||||||||||||||||||                                                                
3' TACTAACGCTTTTAACACAAATTAC 5' CTOT > GA        3' TACTAACGCTTTTAACACAAATTAC 5' CTOT > GA R1:CATTAAACACAATTTTCGC                                                           
         *                                                *                                R2:ATGATTGCGAAAATTGTGT                                              
                                           --->                                                                                                
          *                                                *                               R1:ATAATTGCAAAAATTACAT                                      
5' ATAATTGCAAAAATTACATTTAACA 3' CTOB > GA        5' ATAATTGCAAAAATTACATTTAACA 3' CTOB > GA R2:TGTTAAATGTAATTTTTGC
   |||||||||||||||||||||||||                        |||||||||||||||||||||||||                                                                  
3' TATTAACGTTTTTAATGTAAATTGT 5' OB > CT          3' TATTAACGTTTTTAATGTAAATTGT 5' OB > CT   R1:TGTTAAATGTAATTTTTGC                                                               
         *                                                *                                R2:ATAATTGCAAAAATTACAT                                                  
|
|  Alignment
V
                                         ref_CT: ATGATTGTGAAAATTGTGTTTAATG                                                                           
    OT:       R1:ATGATTGCGAAAATTGTGT     R1_CT:  ATGATTGTGAAAATTGTGT                                                                                                             
              R2:CATTAAACACAATTTTCGC     rcR2_GA:      GTGAAAATTGTGTTTAATG                                                                                                  

                                         ref_CT: ATGATTGTGAAAATTGTGTTTAATG                                                                                                          
    CTOT:     R1:CATTAAACACAATTTTCGC     rcR1_GA:      GTGAAAATTGTGTTTAAT                                                                                    
              R2:ATGATTGCGAAAATTGTGT     R2_CT:  ATGATTGTGAAAATTGTGT                                                                                                            

                                         ref_GA: ATAATTACAAAAATTACATTTAACA                                                                                                          
    CTOB:     R1:ATAATTGCAAAAATTACAT     R1_GA:  ATAATTACAAAAATTACAT                                                                                                             
              R2:TGTTAAATGTAATTTTTGC     rcR2_CT       ACAAAAATTACATTTAACA                                                                                                              

                                         ref_GA: ATAATTACAAAAATTACATTTAACA                                                                                                          
    OB:       R1:TGTTAAATGTAATTTTTGC     rcR1_CT:      ACAAAAATTACATTTAACA                                                                                                              
              R2:ATAATTGCAAAAATTACAT     R2_GA:  ATAATTACAAAAATTACAT                                                                                                         
```
