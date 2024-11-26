<h1 align="center" style="color:blue;">Reinforcement Learning</h1>

## **Why Reinforcement Learning?**

Imagine you're shopping online for clothes, and the website starts suggesting exactly what you’re looking for—styles, colors, and brands you love. The more you browse, the better the suggestions get, almost like the website is reading your mind.

This is **Reinforcement Learning (RL)** in action. It learns from your choices and improves with every click, making your shopping experience faster and more personalized.

### **So, why should you care?**

Because RL is behind the technology that’s making your favorite apps smarter, and it’s shaping the future of how machines understand us.

---

## Let's Explore Reinforcement Learning

---

### **Exploration vs Exploitation**
<div align="center">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/guwahati.jpg" width="45%" height="200px" style="margin-right: 5%;">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/Momo.jpg" width="45%" height="200px">
</div>


> Imagine you’re in **Guwahati**, walking down **Paltan Bazaar**, deciding where to grab a quick bite.

- **Exploitation**: You’ve been to the same **momos** stall for a long time, and you know their momos are always fresh and delicious. You choose to go there again because you know you’ll enjoy them every time.
  
- **Exploration**: But there’s another **momos** stall nearby that you’ve never tried before. You’re not sure if their momos are as good, but you decide to give them a try, hoping to discover something new and maybe even better.

At first, you might explore and try the new stall, but after a few visits, you’ll start to notice which momos taste better or have a better price. Eventually, you’ll start going to the stall that you like the most. Over time, you’ll strike the perfect balance between exploring new momos stalls to discover hidden gems and sticking to the one that consistently delivers the best taste and satisfaction.

In **Reinforcement Learning**, this process is similar. Initially, the algorithm might try different actions (exploration) to learn about possible outcomes. But as it learns from the feedback, it starts to focus on the actions that give the best results (exploitation). As the learning process continues, the algorithm converges to a point where it consistently makes the best choices, just like you will keep going to the momos stall that suits your taste the most!

---

## **Epsilon-Greedy Approach**

Imagine this: Every Sunday, you eat momos, and you’ve decided to make this a weekly ritual—52 times a year. Over time, you've built a preference for a particular momos stall that consistently serves the best momos. However, you don’t want to miss out on the possibility of discovering a better stall, so you decide to balance exploration and exploitation.

### **Decision-Making Process (Using the Cheat Sheet)**
<div align="center">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/paper_sheet_game.png" width="45%" height="200px">
</div>

Imagine every Sunday, you have to decide whether to visit your favorite momos stall or explore a new one. You’ve created a cheat sheet with **5 numbers** (1 to 5), and here's the rule:

- If the number you draw is **5**, you explore a new momos stall.
- For any number between **1 to 4**, you exploit your favorite, trusted momos stall.

In this case, **80% of the time** (when you draw a number between 1 and 4), you stick to your best-known momos stall (exploitation). But **20% of the time** (when you draw number 5), you venture out and explore a new stall (exploration).

### **How It Works Over Time:**

- **When Numbers 1 to 4 (80% Chance)**: You stick to your favorite momos stall. This is your **exploitation phase**, where you know exactly what to expect—tasty momos and satisfaction every time.
  
- **When Number 5 (20% Chance)**: Occasionally, you draw the number 5, and you decide to try a new momos stall. This is your **exploration phase**, where you step out of your comfort zone, hoping to find something even better.

By following this method, you're creating a healthy balance between **exploration** and **exploitation**. Over time, you get to enjoy the best-known option while also keeping your choices fresh by trying new places now and then.

---

### **In Reinforcement Learning Terms:**

This is similar to the **epsilon-greedy strategy** in Reinforcement Learning:

- **Epsilon (ε)** is the **probability of exploration**. In this case, **20%** (1 out of 5).
- **Exploit**: **80% of the time** (numbers 1–4), you choose the best-known action (your favorite momos stall).
- **Explore**: **20% of the time** (number 5), you try something new, hoping to discover a better reward (a better momos stall).

As time goes on, you find a good balance between **exploration** and **exploitation**, much like how RL algorithms learn to explore new options while exploiting the best-known ones to maximize overall rewards.

---

### **Here's how you set it up:**

- **Exploitation**: You know that one particular stall consistently serves the best momos, and you're confident that you'll enjoy their food every time. So, you decide to exploit your knowledge and visit that stall **80% of the time**.
  
- **Exploration**: However, there's always the chance that another stall might be serving even better momos. To make sure you're not missing out, you decide to explore other stalls **20% of the time** to see if there's a hidden gem you haven’t discovered yet.

---
So here :
- **Environment:**  
  The environment consists of **momos stalls in Paltan Bazaar**, each offering a variety of momos with different tastes, prices, and quality.
  
- **Actions:**  
  Actions refer to the choices you can make within the environment:
  - **Explore**: Try a new momos stall to discover potentially better options.
  - **Exploit**: Stick with the known best momos stall that consistently serves delicious momos.

- **Reward:**  
  The reward is the feedback you receive from the environment based on your actions:
  - **Positive reward**: A new momos stall serves better momos than your favorite one, leading to higher satisfaction.
  - **Negative reward**: The new stall doesn’t meet expectations, or the momos aren't as good as you thought, resulting in dissatisfaction.
----

Great, so we have become fimilar with certain terms ,now lets see how a rl agent can be modeled :
> Key terms :
1. **Agent**: The decision-maker or learner.
2. **Environment**: The world the agent interacts with.
3. **State**: The current situation the agent is in.
4. **Action**: The set of moves the agent can take.
5. **Reward**: Feedback received after an action, guiding the agent.
6. **Policy**: The agent’s strategy to choose actions based on the state.
7. **Reward Function**: Maps state-action pairs to a reward signal.
8. **Value Function**: Estimates future rewards starting from a specific state.

## Aim of a Reinforcement Learning (RL) Agent

The aim of a Reinforcement Learning (RL) agent is:

**To maximize the cumulative reward over time.**

This means the agent learns to take actions that result in the highest possible long-term reward, not just immediate rewards, by interacting with the environment and improving its policy (strategy) through experience.

<div align="center">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/rl_agent.webp" width="45%" height="200px">
</div>

<h1>How a Reinforcement Learning (RL) Model Works</h1>

<ol>
    <li>
        <strong>Initialization:</strong> 
        The agent starts with no knowledge and initializes a policy or value function.
    </li>
    <li>
        <strong>Interaction with Environment:</strong> 
        The agent takes an <em>action</em> in the <em>environment</em> based on its current <em>state</em>.
    </li>
    <li>
        <strong>Receive Feedback:</strong> 
        The environment provides a <em>reward</em> and transitions the agent to a new <em>state</em>.
    </li>
    <li>
        <strong>Policy Update:</strong> 
        The agent updates its policy using the reward signal to improve future actions.
    </li>
    <li>
        <strong>Repeat:</strong> 
        Steps 2–4 are repeated over many episodes until the agent learns an optimal policy to maximize cumulative rewards.
    </li>
</ol>

<p>The RL model continuously refines its strategy, balancing exploration (trying new actions) and exploitation (choosing known rewarding actions) to achieve its goal.</p>
<h1 style="color:red; text-align:center;"><strong>Tic-Tac-Toe Game</strong></h1>

<ul>
    <li>
        <strong>Environment:</strong> A 3x3 board where the game is played. The environment changes as the agent (player) and opponent place their marks (X or O) on the board.
    </li>
    <li>
        <strong>State:</strong> The current configuration of the 3x3 board. For example, an empty board at the start, or a partially filled board during the game.
    </li>
    <li>
        <strong>Action:</strong> The agent’s move—choosing an empty cell to place its mark (X or O).
    </li>
    <li>
        <strong>Reward:</strong> Feedback for the agent:
        <ul>
            <li><strong>+1:</strong> If the agent wins the game.</li>
            <li><strong>0:</strong> If the game ends in a draw (tie).</li>
            <li><strong>-1:</strong> If the agent loses the game.</li>
        </ul>
    </li>
    <li>
        <strong>Aim:</strong> To learn an optimal strategy that maximizes rewards by winning as many games as possible or minimizing losses.
    </li>
</ul>
<div align="center">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/game_board.png" width="45%" height="200px">
</div>

# Architecture of RL Agent Framework for Tic-Tac-Toe

Below is the architecture of the RL agent framework for the game:

<div align="center">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/model_art_full.png" 
       alt="RL Framework" width="50%" height="200px">
</div>

## Steps to Follow:

1. **Define the 3x3 Game Board (Environment):**  
   - Represented as a numpy array of size 9 (3x3), all initialized with zeros.

2. **Define the Action Space:**  
   - All possible moves in the game, represented as tuples of row and column indices.

   <div align="center">
     <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/intital_board.png" 
          alt="Initial Game Board" width="50%" height="200px">
   </div>

3. **Define Moves on the Board:**  
   - All values in the board start as 0.  
   - Mark `-1` if AI chooses a position, and `1` if the Human chooses a position.

4. **Define a Function to Check the Game Status:**  
   - Check rows, columns, and diagonals for a win (all `1` or all `-1`).  
   - Check if the game ends in a draw (no possible moves left).

5. **Initialize a Q-Table:**  
   - The Q-table is a dictionary.  
   - **Keys:** Board representation (state).  
   - **Values:** Associated rewards.

6. **Define Epsilon-Greedy Approach:**  
   - A strategy to balance exploration (random moves) and exploitation (using learned Q-values).

7. **Define a Function to Update Q-Values:**  
   - Use the Bellman Equation to update Q-values based on the reward and the next state.
<div align="center">
  <img src="https://github.com/Amitkupadhyay0/reinforcement-learning/blob/main/images/bellman_equation.png"  width="50%" height="200px">
</div>
8. **Train the Model:**  
   - Train over a certain number of episodes where AI plays against itself.  
   - Continuously update the Q-table during training.

9. **Play HUMAN vs AI:**  
   - Use the trained Q-table for the AI to take actions.  
   - While playing with a human, the AI continues to update the Q-table to improve further.









