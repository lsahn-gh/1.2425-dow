# 1.2425 Day of Week method.

This dow(day of week) algorithm is based on [Sakamoto's methods](https://en.wikipedia.org/wiki/Determination_of_the_day_of_the_week#Sakamoto's_methods).  
Let's take a look at the Sakamoto's codes.
```
dayofweek(y, m, d)  /* 1 <= m <= 12,  y > 1752 (in the U.K.) */
{
    static int t[] = {0, 3, 2, 5, 0, 3, 5, 1, 4, 6, 2, 4};
    y -= m < 3;
    return (y + y/4 - y/100 + y/400 + t[m-1] + d) % 7;
}
```

The part of ![equation](https://latex.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20y%20&plus;%20%5Cfrac%7By%7D%7B4%7D%20-%20%5Cfrac%7By%7D%7B100%7D%20&plus;%20%5Cfrac%7By%7D%7B400%7D) could be ![equation](https://latex.codecogs.com/gif.latex?1.2425%20*%20y) as below,
```
dayofweek(y, m, d)  /* 1 <= m <= 12,  y > 1752 (in the U.K.) */
{
    static int t[] = {0, 3, 2, 5, 0, 3, 5, 1, 4, 6, 2, 4};
    y -= m < 3;
    return (1.2425 * y + t[m-1] + d) % 7;
}
```

# Proof
![equation](https://latex.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20y%20&plus;%20%5Cfrac%7By%7D%7B4%7D%20-%20%5Cfrac%7By%7D%7B100%7D%20&plus;%20%5Cfrac%7By%7D%7B400%7D%20%3D%20%5Cfrac%7B400y%20&plus;%20100y%20-%204y%20&plus;%20y%7D%7B400%7D%20%3D%20%5Cfrac%7B497y%7D%7B400%7D%20%3D%20%28497%29%280.0025%29y)  

![equation](https://latex.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%3D%201.2425y)
