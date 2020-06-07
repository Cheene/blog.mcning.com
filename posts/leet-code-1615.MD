---
title: "#1615 [链表中倒数第k个节点]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","链表"]
draft: false
---

## 题目

````
输入一个链表，输出该链表中倒数第k个节点。为了符合大多数人的习惯，本题从1开始计数，即链表的尾节点是倒数第1个节点。例如，一个链表有6个节点，从头节点开始，它们的值依次是1、2、3、4、5、6。这个链表的倒数第3个节点是值为4的节点
````

## **示例**

````
给定一个链表: 1->2->3->4->5, 和 k = 2.

返回链表 4->5.
````

## **限制**

````

````

## 思路

````
设置一个队列
每次更新队列的值
````

## 实现

````go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func getKthFromEnd(head *ListNode, k int) *ListNode {

    if head == nil {
        return nil
    }

    queue := make([]*ListNode,k)
    for i := 0; i < k; i++ {
        queue[i] = head
        head = head.Next
    }

    for head != nil {
        for i := 0; i < k-1; i++ {
            queue[i] = queue[i+1]
        }
        queue[k-1] = head
        head = head.Next
    }
    return queue[0]    
}
````

