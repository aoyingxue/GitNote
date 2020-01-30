#### Approach 1: Stacks

An interesting property about a valid parenthesis expression is that a sub-expression of a valid expression should also be a valid expression. (Not every sub-expression) e.g.

![img](20_Valid%20Parentheses.assets/20-Valid-Parentheses-Recursive-Property.png)

Also, if you look at the above structure carefully, the color coded cells mark the opening and closing pairs of parenthesis. The entire expression is valid, but sub portions of it are also valid in themselves. This lends a sort of a recursive structure to the problem. For e.g. Consider the expression enclosed within the two green parenthesis in the diagram above. The opening bracket at index `1` and the corresponding closing bracket at index `6`.

> What if whenever we encounter a matching pair of parenthesis in the expression, we simply remove it from the expression?

Let's have a look at this idea below where remove the smaller expressions one at a time from the overall expression and since this is a valid expression, we would be left with an empty string in the end.

> The stack data structure can come in handy here in representing this recursive structure of the problem. We can't really process this from the inside out because we don't have an idea about the overall structure. But, the stack can help us process this recursively i.e. from outside to inwards.

**Algorithm**

1. Initialize a stack S.
2. Process each bracket of the expression one at a time.
3. If we encounter an opening bracket, we simply push it onto the stack. This means we will process it later, let us simply move onto the **sub-expression** ahead.
4. If we encounter a closing bracket, then we check the element on top of the stack. If the element at the top of the stack is an opening bracket `of the same type`, then we pop it off the stack and continue processing. Else, this implies an invalid expression.
5. In the end, if we are left with a stack still having elements, then this implies an invalid expression.

We'll have a look a dry run for the algorithm and then move onto the implementation.

```python
class Solution:
    def isValid(self, s: str) -> bool:
        ## stack
        while "()" in s or "[]" in s or "{}" in s:
            s=s.replace("()","").replace("[]","").replace("{}","")
        return s==""
```

