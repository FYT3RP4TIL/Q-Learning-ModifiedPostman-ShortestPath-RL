# Q-Learning-ModifiedPostman-ShortestPath-RL

The postman of a given city should get the letters at a given station and deliver them to the recipients.

In order to ensure maximum efficiency and productivity, the postman will need to learn the shortest path between the item packaging area and all other locations within the city where they are allowed to travel. In order to accomplish this task, we will use Q-learning to solve the problem.

The AI agent's goal is to learn the shortest path between the item packaging area and all of the other locations in the city where the postman is allowed to travel.


## 1. Define the Problem:

* State Space: In this context, the cities and the locations where the postman can travel represent the state space. Each location is a state.
  * City Boundaries (black squares)
  * Travel Spaces (white squares)
  * Item Packaging / Shipping Area (green squares)
* Action Space: Possible actions are movements from one location to another.
    * The actions that are available to the AI agent are to move the postman in one of four directions :
        * Up
        * Right
        * Down
        * Left

![Screenshot 2024-01-13 183818](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/e8ac7b4f-df28-4185-8d77-5d3b94142f4c)

* Reward Function: The reward is the negative distance traveled.The agent may begin at any white square, but its goal is always the same: *to maximize its total rewards*.

![Screenshot 2024-01-13 184441](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/3c537e43-c4ea-434e-bf10-828e097029d5)

## 2. Initialize Q-table:

* Creating a Q-table where the whole state space which is represented with rewards which are changable.
 
## 3. Define Parameters:

* Set parameters such as the learning rate (α), discount factor (γ), exploration-exploitation trade-off (ε-greedy strategy).

## 4. Q-learning Algorithm:

### Exploration vs. Exploitation:
* At each step, the postman chooses an action based on the current Q-values.
* With probability ε, the postman explores a random action.
* With probability 1-ε, the postman exploits the action with the highest Q-value.
    
    * Bellman Equation - \
      \
      ![image](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/afe3c2e2-e483-4ab2-808f-44e253bc62f2)

    * Markov’s Decision Process – \
      \
      ![image](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/fd52cf49-6656-46d3-9e9a-2a0082733d46)
      \
      ![image](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/3d3b62e0-13c2-46ec-8616-21ad7b59d286)

    * Q-learning Intuition - \
      \
      ![image](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/57da0036-b50a-4454-965b-110efd6346f5)


    * Temporal Difference - \
      \
      ![image](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/ee8b0cc2-8cb8-4378-863a-f3e49a821cfb)


    * Q-Leearning Algorithm - \
      \
      ![image](https://github.com/Sudhanshu21xx/Q-Learning-ModifiedPostman-ShortestPath-RL/assets/113416452/f3454f38-71e1-40fc-bb19-761287049e8d)




### Update Q-values:
* Use the Q-learning update rule to adjust the Q-values based on the observed reward and the estimated future rewards.
* Q(s, a) = (1-α) * Q(s, a) + α * (R + γ * max(Q(s', a')))

## 5. Training:

* Let the postman explore the city, updating Q-values as they go.
Repeat this process for a sufficient number of episodes until the Q-values converge.

## 6. Path Extraction:

* Once the Q-values have converged, the postman can choose the action with the highest Q-value at each state to determine the optimal path.

## 7. Testing:

* Deploy the learned Q-values in a real scenario to guide the postman in finding the shortest path efficiently.

## 8. Fine-Tuning:

* Periodically retrain the Q-learning model with new data to adapt to changes in the city layout or postal delivery requirements.

## 9. Considerations:

* The success of the algorithm depends on appropriate parameter tuning and the representation of the state and action spaces.
* Handling dynamic environments or changes in the city layout may require continuous learning or periodic updates to the Q-table.

By following these steps, the postman can efficiently learn the shortest paths between the item packaging area and all other locations within the city, optimizing the delivery process.





