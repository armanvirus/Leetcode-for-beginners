# Leetcode-for-beginners
A repo that provides solutions to leetcode beginners guide challenge problems
### Sum of 1D array
Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

 

Example 1:

Input: nums = [1,2,3,4]
Output: [1,3,6,10]
Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].

Example 2:

Input: nums = [1,1,1,1,1]
Output: [1,2,3,4,5]
Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].

Example 3:

Input: nums = [3,1,2,10,1]
Output: [3,4,6,16,17]
#### Solution

```
 var runningSum = function(nums) {
var currentSum = 0;
var sumArray = [];
    for(let i = 0; i < nums.length; i++){
    currentSum += nums[i];
    sumArray.push(currentSum)
    }
    return sumArray
};

runningSum([1,2,3,4,5])
```


### Riches customer wealth
You are given an m x n integer grid accounts where accounts[i][j] is the amount of money the i​​​​​​​​​​​th​​​​ customer has in the j​​​​​​​​​​​th​​​​ bank. Return the wealth that the richest customer has.

A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.

 

Example 1:

Input: accounts = [[1,2,3],[3,2,1]]
Output: 6
Explanation:
1st customer has wealth = 1 + 2 + 3 = 6
2nd customer has wealth = 3 + 2 + 1 = 6
Both customers are considered the richest with a wealth of 6 each, so return 6.

Example 2:

Input: accounts = [[1,5],[7,3],[3,5]]
Output: 10
Explanation: 
1st customer has wealth = 6
2nd customer has wealth = 10 
3rd customer has wealth = 8
The 2nd customer is the richest with a wealth of 10.

Example 3:

Input: accounts = [[2,8,7],[7,1,3],[1,9,5]]
Output: 17

#### Solution

```
var maximumWealth = function(accounts) {
    flats = []
    for(let i = 0; i < accounts.length; i++){
 var sums = 0;
        for(let j = 0; j < accounts[i].length; j++){
            sums += accounts[i][j]
        }
        flats.push(sums)
    }
        return Math.max(...flats)
    
};

maximumWealth([[1,2,3],[3,2,1]])

```

### FizzBuzz
Given an integer n, return a string array answer (1-indexed) where:

    answer[i] == "FizzBuzz" if i is divisible by 3 and 5.
    answer[i] == "Fizz" if i is divisible by 3.
    answer[i] == "Buzz" if i is divisible by 5.
    answer[i] == i (as a string) if none of the above conditions are true.

 

Example 1:

Input: n = 3
Output: ["1","2","Fizz"]

Example 2:

Input: n = 5
Output: ["1","2","Fizz","4","Buzz"]

Example 3:

Input: n = 15
Output: ["1","2","Fizz","4","Buzz","Fizz","7","8","Fizz","Buzz","11","Fizz","13","14","FizzBuzz"]

#### Solution
```
ar fizzBuzz = function(n) {
 var answer = []
    for(let i = 1; i < n + 1; i++){
        if((i % 3 == 0) && (i % 5 == 0)){
            answer.push("FizzBuzz")
        }else if(i % 3 == 0){
            answer.push("Fizz")
        }else if(i % 5 == 0){
            answer.push("Buzz")
        }else{
            answer.push(String(i))
        }
    }
    console.log(answer)
    return answer;
};

fizzBuzz(3)
```

### Number of steps to reduce a number
Given an integer num, return the number of steps to reduce it to zero.

In one step, if the current number is even, you have to divide it by 2, otherwise, you have to subtract 1 from it.

 

Example 1:

Input: num = 14
Output: 6
Explanation: 
Step 1) 14 is even; divide by 2 and obtain 7. 
Step 2) 7 is odd; subtract 1 and obtain 6.
Step 3) 6 is even; divide by 2 and obtain 3. 
Step 4) 3 is odd; subtract 1 and obtain 2. 
Step 5) 2 is even; divide by 2 and obtain 1. 
Step 6) 1 is odd; subtract 1 and obtain 0.

Example 2:

Input: num = 8
Output: 4
Explanation: 
Step 1) 8 is even; divide by 2 and obtain 4. 
Step 2) 4 is even; divide by 2 and obtain 2. 
Step 3) 2 is even; divide by 2 and obtain 1. 
Step 4) 1 is odd; subtract 1 and obtain 0.

Example 3:

Input: num = 123
Output: 12

```
var numberOfSteps = function(num) {
    var reduced = num
    var steps = 0;
    while(reduced !== 0){
        if(reduced % 2 == 0){
            reduced /= 2
            steps += 1
        }else{
            reduced -= 1
            steps += 1
        }
    }
    return steps
    
};

numberOfSteps(20)
```

### Middle of the Linked List

#### Solution
```
ar middleNode = function(head) {
    var slow = head;
    var fast = head;

    // Use a two-pointer approach to find the middle node
    while (fast && fast.next) {
        slow = slow.next;
        fast = fast.next.next;
    }

    // 'slow' will be at the middle node
    return slow;
};

// Define a linked list
class ListNode {
    constructor(val) {
        this.val = val;
        this.next = null;
    }
}

const head = new ListNode(1);
head.next = new ListNode(2);
head.next.next = new ListNode(3);
head.next.next.next = new ListNode(4);
head.next.next.next.next = new ListNode(5);

const middle = middleNode(head);
console.log(middle.val);
```


