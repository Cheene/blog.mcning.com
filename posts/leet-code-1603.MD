---
title: "#1603 [旋转数组的最小数字]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","数组"]
draft: false
---

## 题目

````
把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。输入一个递增排序的数组的一个旋转，输出旋转数组的最小元素。例如，数组 [3,4,5,1,2] 为 [1,2,3,4,5] 的一个旋转，该数组的最小值为1。  
````

## **示例**

````
输入：[3,4,5,1,2]
输出：1

输入：[2,2,2,0,1]
输出：0
````

## **限制**

````

````

## 思路

````
1 寻找第一个逆序对
````

## 实现

````go
func minArray(numbers []int) int {
    
  i := 0
  j := len(numbers)-1
  
  for i < j {
      mid := (i + j)/2
      if numbers[mid] < numbers[j] {
          i = mid
      } else if numbers[mid] > numbers[j]{
          j = mid + 1
      } else {
          j -= 1
      }
  }
  return numbers[i]


}
````

