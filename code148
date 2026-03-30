/**
 * Definition for singly-linked list.
 * struct ListNode {
 * int val;
 * ListNode *next;
 * ListNode() : val(0), next(nullptr) {}
 * ListNode(int x) : val(x), next(nullptr) {}
 * ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* sortList(ListNode* head) {
        if (!head || !head.next) return head;

        ListNode* slow = head;

        ListNode* fast = head->next;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        ListNode* mid = slow->next;
        slow->next = nullptr;
        ListNode* left = sortList(head);
        ListNode* right = sortList(mid);
        return merge(left, right);
    }

private:
    ListNode* merge(ListNode* i, ListNode* x) {
        ListNode dummy(0);
        ListNode* t = &dummy;

        while (i && x) {
            if (i->val < x->val) {
                t->next = i;
                i = i->next;
            } else {
                t->next = x;
                x = x->next;
            }
            t = t->next;
        }
        t->next = i ? i : x;
        return dummy.next;
    }
};
