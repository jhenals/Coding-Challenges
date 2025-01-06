# 605. Can Place Flowers

## Problem Definition
You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in adjacent plots.

Given an integer array flowerbed containing 0's and 1's, where 0 means empty and 1 means not empty, and an integer n, return true if n new flowers can be planted in the flowerbed without violating the no-adjacent-flowers rule and false otherwise.

Example 1:

Input: flowerbed = [1,0,0,0,1], n = 1
Output: true
Example 2:

Input: flowerbed = [1,0,0,0,1], n = 2
Output: false

## My Solution 1: Bruteforce Approach
```
public boolean canPlaceFlowers(int[] flowerbed, int n) {
        int len=flowerbed.length;

        for(int i=0;i<len;i++){
            if( n>0 && flowerbed[i]==0 ){
                boolean leftEmpty= (i==0 || flowerbed[i-1]==0);
                boolean rightEmpty= (i ==len-1 || flowerbed[i+1]==0);

                if(leftEmpty && rightEmpty){
                    flowerbed[i]=1;
                    n--;
                    if(n==0){
                        return true;
                    }
                }

            }
        }
        return n==0;
    }
    }
```
