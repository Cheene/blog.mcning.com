---
title: "#1611[删除链表的节点]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","链表"]
draft: false
---

## 题目

````
给定单向链表的头指针和一个要删除的节点的值，定义一个函数删除该节点。

返回删除后的链表的头节点。

注意：此题对比原题有改动
````

## **示例**

````
输入: head = [4,5,1,9], val = 5
输出: [4,1,9]
解释: 给定你链表中值为 5 的第二个节点，那么在调用了你的函数之后，该链表应变为 4 -> 1 -> 9.
````

## **限制**

````

````

## 思路

````
双指针实现
碰到值相等的时候，将该值对应节点的父元素的下一个位置设置为当前节点的下一个位置。
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
func deleteNode(head *ListNode, val int) *ListNode {
    //头为空
    if head == nil {
        return head
    }
    //首元素的时候
    if head.Val == val {
        if head.Next == nil {
            return &ListNode{}
        } else {
            head = head.Next
        }
    }
    p := head
    q := head.Next
    for q != nil && q.Val != val {
        p = q
        q = p.Next
    }
    if q != nil {
        p.Next = q.Next
    }
    return head
}
````
