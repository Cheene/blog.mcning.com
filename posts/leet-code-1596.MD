---
title: "#1596 [二维数组中的查找]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","数组"]
draft: false
---

## 题目

````
在一个 n * m 的二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。
````

## **示例**

````
现有矩阵 matrix 如下：

[
  [1,   4,  7, 11, 15],
  [2,   5,  8, 12, 19],
  [3,   6,  9, 16, 22],
  [10, 13, 14, 17, 24],
  [18, 21, 23, 26, 30]
]
给定 target = 5，返回 true。

给定 target = 20，返回 false。
````

## **限制**

````
0 <= n <= 1000

0 <= m <= 1000
````

## 思路

````
暴力破解
````



## 实现

````go
func findNumberIn2DArray(matrix [][]int, target int) bool {
    //边界条件
    n := len(matrix)
    if n == 0 {
        return false
    }
    
    m := len(matrix[0])
    if m == 0 {
        return false
    }
    //暴力破解
    for i := 0; i < n; i++ {
        for j := 0; j < m; j++ {
            if matrix[i][j] == target {
                return true
            }
        }
    }
    return false
}
````
