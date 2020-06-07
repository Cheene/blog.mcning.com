---
title: "#1610 [打印从1到最大的n位数]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","数组"]
draft: false
---

## 题目

````
输入数字 n，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。
````

## **示例**

````
输入: n = 1
输出: [1,2,3,4,5,6,7,8,9]
````

## **限制**

````

````

## 思路

````
1 根据 n 得到最大值
2 新建数组并初始化
3 返回数组
````

## 实现

````go
func printNumbers(n int) []int {
    if n == 0 {
        return []int{}
    }

    max := 0
    for i := 0; i < n; i++ {
        max *= 10
        max += 9
    }

    nums := make([]int,max)
    for i := 0; i < len(nums); i++ {
        nums[i] = i+1
    }
    return nums
}
````

