## Midterm

> Yuki Ao / 474878

1. Q1

   1. The calculations are in the following tables.

      When the party affiliation of a senator is not related to votes ($H_0$), if not counting the two Republicans who didn't vote, the result should be:

      |                   |  No  | Yes  | Total |
      | :---------------: | :--: | :--: | :---: |
      |  Democrats (50%)  | 24.5 | 24.5 |  49   |
      | Republicans (50%) | 24.5 | 24.5 |  49   |
      |       Total       |  49  |  49  |  98   |

      |  $\chi^2$   |           No           |          Yes          |
      | :---------: | :--------------------: | :-------------------: |
      |  Democrats  | $(24.5-48)^2/24=22.54$ | $(24.5-1)^2/25=22.54$ |
      | Republicans |  $(24.5-0)^2/24=24.5$  | $(24.5-49)^2/25=24.5$ |

      So the $\chi^2 =22.54+22.54+24.5+24.5=94.08; \chi≈9.70$ . 

   2. $\chi^2 > cutoff\ value=7.82$. The bigger the $\chi$ statistic is, the more the actual differs from the expected. In this case, it's bigger than cutoff value, which means there's an association between the variables, and we could not accept the null hypothesis ($H_0$). The party affiliation of a senator is indeed related to his/her votes. 

2. Q2: The regression equation should be $total\_clicks=a+f*site+b*glitch+c*site*glitch$ 

   1. The glitch's p-value is more than 5%, which means that the glitch alone is not related to the total clicks. The coefficient estimate of the glitch (*b*) should be 0. 

      However, the p-value of the interaction term is smaller than 5%, so the glitch impacted google site's total clicks. 

      - For Google <u>during</u> the glitch: 

        total_clicks1=19597.4+136988\*1+0\*1+(-7412.3)\*1\*1=149173  

      - For Bing <u>during</u> the glitch: 

        total_clicks2=19597.4+136988\*0+0\*1+(-7412.3)\*0\*1=19597.4 (*unchanged*)

      - For Google <u>before</u> the glitch: 

        total_clicks3=19597.4+136988\*1+0\*0+(-7412.3)\*1\*0=156585  

      - For Bing <u>before</u> the glitch: 

        total_clicks4=19597.4+136988\*0+0\*0+(-7412.3)\*0\*0=19597.4 (*unchanged*)

      So between "before" and "after" the glitch, the seasonality difference would be total_clicks1+total_clicks2-(total_clicks3+total_clicks4)=-7412.3≈-7412, which means the glitch affected the total clicks to decrease by *7412* clicks per day. 

   2. The net effect of stopping Google when there's no glitch is equal to 136988\*0-136988\*1=-136988, which means stopping Google ads will bring a decrease on total clicks by *136988* clicks per day. 

   3. Based on the analyses above, Bazaar should continue their sponsored search ads spending on Google, because even though during the glitch on Google, they lose only *7412* clicks per day, however if they totally stop Google ads, they will lose as many as *136988* clicks per day, which is far more than the clicks brought by Bing (*only 19597*). The lost brought by the glitch on Google is small, but the lost brought by completely stopping Google ads is more than *18* times large. 

