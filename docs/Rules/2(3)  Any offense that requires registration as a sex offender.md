# 2 (3)  Any offense that requires registration as a sex offender



## Law

610.140.2(5)  Any felony offense of assault; misdemeanor or felony offense of domestic assault; or felony offense of kidnapping;

Is the statute for assult?
   Is charges.conviction_charge_type a misdemeanor or felony
       Cannot be expunged

Is the statute domestic assault?
   Is charges.conviction_charge_type a felony
       Cannot be expunged
       
       
       
565.130.  Kidnapping, third degree, penalty. — 1.  A person commits the offense of kidnapping in the third degree if he or she knowingly restrains another unlawfully and without consent so as to interfere substantially with his or her liberty.

  2.  The offense of kidnapping in the third degree is a class A misdemeanor unless the person unlawfully restrained is removed from this state, in which case it is a class E felony.


Is the statue a kidnapping. any in  (565.130, .....)?
   Is charges.conviction_charge_type a felony
       Cannot be expunged
       
       
## Pattern

If statute is a YYY
and charges.conviction_charge_type is a WWW
Then not elegiable.

1. Create list of the statute numbers that match YYY
2. Apply flag to statutes that YYY
3. 

## Plan Speak

## Training

*What we need to tell pro bono attornies* 

They need to do a sanity check on the resultes.


## Information Needed

Need three list of statutes,  

1. offense of assault
2. offense of domestic assault
3. offense of kidnapping

How do we find these statues, for example kidnapping when kidnapping is not in the name?



We neet to know:

1. If the charge is convicted as a felony.


Assumptions:

* This applies to the charge and does not disqualify the case.
  
Senario:

If they are recklessly  driving their motor scooter and kill someone, they would be charged with:
* Recklessly driving their motor scooter (Felony). does not mention anything about death
* One of the "causes the death of..." from 565.020 through .034

What happens if they "Down Grade" to a M?


## UX

* Explain why it is not expungable and what the logic is.
* Have a button to submit an issue or question.


## Database




### Add  flag



How to initalize?



How to maintain?

1. Have someone watch the changes in law
2. Have lawyers look for errors (sanity check)

## Logic

```
if charges.conviction_charge_type == Felony

`
