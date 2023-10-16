# ChatGPT Dynamic Programming Solution Analysis 

## Synopsis:

ChatGPT is a powerful tool that allows users to prompt a LLM (Large Language Model) about any questions that they may have. One way this AI is used in the Computer Science sector to produce solutions to various algoirhtmic problems. One category of problems that ChatGPT is still not proficient in generating solutions to is DP (Dynamic Programming). This blog post will analyze basic to advanced DP problems and analyze ChatGPT's solutions to them. 

## House Robbers:

The house robeers problem is a simple DP problem where you have to find the maximum sum of non-adjacent elements of a list. So, for example, if you have a list that contains [2, 10, 12, 5, 20], then the maximum sum will be 34. 

### ChatGPT's Solution

    def rob(nums):
        if not nums:
            return 0
    
        if len(nums) == 1:
            return nums[0]
    
        # Initialize an array to store the maximum money that can be robbed
        # at each house.
        max_money = [0] * len(nums)
    
        # Base cases
        max_money[0] = nums[0]
        max_money[1] = max(nums[0], nums[1])
    
        # Fill the array using a bottom-up approach
        for i in range(2, len(nums)):
            max_money[i] = max(max_money[i - 1], max_money[i - 2] + nums[i])
    
        # The maximum money that can be robbed is in the last cell of the array
        return max_money[-1]


    - Example usage
    nums = [1, 2, 3, 1]  # Houses with money in each
    print("Maximum amount of money that can be robbed:", rob(nums))  # Output: 4



