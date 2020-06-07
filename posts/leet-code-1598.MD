---
title: "#1598 [从尾到头打印链表]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","链表"]
draft: false
---

## 题目

````
输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。
````

## **示例**

````
输入：head = [1,3,2]
输出：[2,3,1]
````

## **限制**

````
0 <= 链表长度 <= 10000
````

## 思路

`核心在于不知道链表的元素的长度`

`如果使用栈的话，可以直接仅遍历一次，直接返回。`

````
1 遍历链表到向量中
  再将向量的元素进行交换
````



## 实现

````go
func reversePrint(head *ListNode) []int {
    if head == nil {
        return []int{}
    }
    res := make([]int,0)
    for head != nil {
        res = append(res,head.Val)
        head = head.Next
    }
    //元素交换
    for i := 0; i < len(res) /2; i++ {
        res[i],res[len(res)-i-1] =  res[len(res)-i-1],res[i]
    }
    return res
}
````

