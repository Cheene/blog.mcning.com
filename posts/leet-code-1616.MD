---
title: "# 1616 [反转链表]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","链表"]
draft: false
---

## 题目

````
定义一个函数，输入一个链表的头节点，反转该链表并输出反转后链表的头节点。
````

## **示例**

````
输入: 1->2->3->4->5->NULL
输出: 5->4->3->2->1->NULL
````

## **限制**

````
0 <= 节点个数 <= 5000
````

## 思路

````
指针类
三个指针 pre cur next
每次的反转
	next = cur.Next
	cur.Next = pre
	pre = cur
	cur = next
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
func reverseList(head *ListNode) *ListNode {

    if head == nil || head.Next == nil {
        return head
    }
    /**
    为何在 pre = head; cur = head.Next 的时候就会无限循环？
    */
    var pre *ListNode
    cur := head

    var r *ListNode
    for cur != nil {
       r = cur.Next
       cur.Next = pre
       pre = cur
       cur = r
    }
    return pre

}
````

