---
title: "#1617 [合并两个排序的链表]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","链表"]
draft: false
---

## 题目

````
输入两个递增排序的链表，合并这两个链表并使新链表中的节点仍然是递增排序的
````

## **示例**

````
输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4
````

## **限制**

````
0 <= 链表长度 <= 1000
````

## 思路

````
三个指针 P，Q,R
P 为主线。QR 分别代表 L1，L2 
每一次判断 QR 对应值的大小来确定主线的走势
再返回 主线 P
````



## 实现

````go
func mergeTwoLists(l1 *ListNode, l2 *ListNode) *ListNode {
    var p,q,r *ListNode
    if l1 == nil {
        return l2
    }
    if l2 == nil {
        return l1
    }
    q,r = l1,l2
    if q.Val <= r.Val {
        p = q
        q = q.Next
    } else {
        p = r
        r = r.Next
    }
    t := p
    for (r != nil && q != nil) {
        fmt.Println(q.Val, r.Val)
        if q.Val <= r.Val {
            p.Next = q
            p = q
            q = q.Next
        } else {
            p.Next = r
            p = r
            r = r.Next
        }  
    }
    if q != nil {
        p.Next = q
    }
    if r != nil {
        p.Next = r
    }
    return t
}
````

