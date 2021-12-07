# Assignment - 4

# Aniruddha Narkhede and Surbhi Dogra

## Anniruddha's Contribution
I added the code to print the exit count for each exit number when Nested Paging is enabled, ran demsg command and took screenshots for the same.

## Surbhi's Contribution
I made changes to the configuration and enabled Shadow Paging, ran the demsg command in nested VM to view the count of each exit and took screenshots for it.

## Observations
We observed that the exit count for each and every exit number is low and ranging between 0 and xx when nested paging is enabled. After enabling shadow paging 
the exit count for every exit number shoots up and increases to a million exits in certain exit cases. 

Screenshot with Nested Paging
<img width="958" alt="NestedPaging" src="https://user-images.githubusercontent.com/25512807/144956900-81e79f25-6aa7-417e-b2d5-2c5ffe78c16f.png">


Screenshot with Shadow Paging
<img width="958" alt="ShadowPaging" src="https://user-images.githubusercontent.com/25512807/144956917-98b906ae-4a86-423b-aa0c-ee6f75bc332e.png">
