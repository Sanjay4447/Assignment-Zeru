# Aave V2 Wallet Credit Scoring using ML

This project assigns credit scores (0 to 1000) to DeFi wallets based on their historical behavior on the Aave V2 protocol. A score closer to 1000 means responsible and trustworthy activity, while a low score may indicate risky behavior (e.g., liquidations, inactivity).

Objective

- Analyze raw Aave transaction data for multiple wallets.
- Extract behavioral features like deposit count, repay count, total transactions, etc.
- Train a simple ML model to predict a credit score between 0 and 1000.
- Save the scores and visualize their distribution.

Project Structure

Assignment@Zeru/
├── user-transactions.json # Input dataset (100K+ records)
├── wallet_scoring.ipynb # Main code
├── wallet_scores_ml.json # Final wallet 
├── score_distribution_ml.png #  histogram
├── README.md # This file
└── analysis.md # Wallet behavior analysis

# Method Chosen

- We used a Decision Tree Regressor from `scikit-learn`

# Processing Flow

1. Load Data
   
2. Feature Engineering
   - For each wallet, we need to count:
     - Number of deposits, borrows, repays, redeems, liquidations
     - Total number of transactions

3. Simulate Labels
   - Created a `simulated_score` for each wallet using a basic weighted formula.

4. Train ML Model
   - Used `DecisionTreeRegressor` to learn from the behavior and simulated scores.

5. Predict Scores
   - Applied the model to all wallets and generate a final `predicted_score` (0–1000).

6. Save Output
   - Output saved in `wallet_scores_ml.json`.

7. Visualize Distribution
   - Created a histogram showing score from 0–1000.

# Features Used for Training

- deposit   
- repay      
- borrow      
- redeem      
- liquidation 
- total_txns

# Tools & Libraries

- Python
- Jupyter Notebook
- pandas
- scikit-learn
- matplotlib
- json

# Results

- `wallet_scores_ml.json` contains the predicted credit score for each wallet.
- `score_distribution_ml.png` visualizes how many wallets fall into different score ranges.
