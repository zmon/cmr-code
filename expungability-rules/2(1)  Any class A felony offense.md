# 2(1)  Any class A felony offense;

We will look at the Charge Type & Class to determine how the coniction was clasified

## Data Source

MSHP - is the best source of what is charged.
[PLEASE VERIFY]

## Database

* charges.conviction_charge_type: Felony, Misdemeanor, ...
* charges.conviction_class_type: A through X

## Code

```
if charges.conviction_charge_type == Felony
and charges.conviction_class_type == A
Then
   Charge is NOT expungable
```

# Other

## Law

610.140.2(2) Any dangerous felony as that term is defined in section 556.061;

## Plan Speak

## Training

*What we need to tell pro bono attornies* 


## Information Needed

We neet to know:

1. If the charge is convicted as a felony.
2. If the charge is a "dangerous felony" under 556.061.(19) - verify law citation

Assumptions:

* This applies to the charge and does not disqualify the case.
  
Senario:

What happens if they "Down Grade" to a M?


## UX

When displaying a statute that is not elagible 

"Can not expunge since charge due to 610.140.2(2 as the charge is a dangerous felony."

## Database

* Charge is a felony.  The database currently has 
   * [`charges.conviction_charge_type`](https://github.com/codeforkansascity/clear-my-record-law-codification/tree/main/database-elements): Felony, Misdemeanor, ...
* The statute is a dangerous felony
   * ADD `statute.dangerous_felony`


### Add `statues.dangerous_felony` flag

Flag has the following options:

* is a dangerous felony
* is NOT a dangerous felony
* Not determined

How to initalize?

1. Set all statutes to NOT a dangerous felony.
2. Set known statutes that are a dangerous felony to true.

How to maintain?

1. Have someone watch the changes in law
2. Have lawyers look for errors (sanity check)

## Logic

```
if charges.conviction_charge_type == Felony
and statute.dangerous_felony is true
Then
   Charge cannot be expunged
```
