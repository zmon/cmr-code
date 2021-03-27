# 2(4) Any felony offense where death is an element of the offense

## Law

610.140.2(4) Any felony offense where death is an element of the offense


## Plain Speak

## Training

*What we need to tell pro bono attornies* 


## Information Needed

We neet to know:

1. If the charge is convicted as a felony.
2. If the charge resulted in a death.  

Assumptions:

* This applies to the charge and does not disqualify the case.
  
Senario:

If they are recklessly  driving their motor scooter and kill someone, they would be charged with:
* Recklessly driving their motor scooter (Felony). does not mention anything about death
* One of the "causes the death of..." from 565.020 through .034

- [x] What happens if they "Down Grade" to a M?  What is entered is what they were convicted of with, so it is already down graded.


## UX

When displaying a statute that is not elagible 

"Can not expunge since charge is a felony and death is a element 610.140.2(4)"

## Database

* Charge is a felony.  The database currently has 
   * [`charges.conviction_charge_type`](https://github.com/codeforkansascity/clear-my-record-law-codification/tree/main/database-elements): Felony, Misdemeanor, ...
* The statute has death as an element
   * ADD `statute.death_is_a_element`


### Add `statues.death_is_a_element` flag

Statutes that death is a element of will most likly have the text "causes the death of..." and be in the range of from 565.020 through .034 (Beth)

Flag has the following options:

* death is an element
* death is NOT an element
* Not determined

How to initalize?

1. Set all statutes to death is NOT an element
2. Set known statutes with death is an element to true.

How to maintain?

1. Have someone watch the changes in law
2. Have lawyers look for errors (sanity check)

## Logic

```
if charges.conviction_charge_type == Felony
and statute.death_is_a_element is true
Then
   Charge cannot be expunged
```

