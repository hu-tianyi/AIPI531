## HW3
Here we evaluate the performance of product recommendataion recommenders with different settings (With/Without side information).

## Dataset
Download the full dataset and save it to `HW3/SA2C_code/Kaggle/data`
Retailrocket: https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset

## Performance Comparison

- Table 1. Cumulative Reward Comparison

| Method | W.O. feature | W. Feature<br> $\lambda=0.1$ | W. Feature<br> $\lambda=0.2$ | W. Feature<br> $\lambda=0.5$ |
|---|---|---|---|---|
| Cumulative<br>Reward @ 5 | 9069.8 | 7546.6 | 6623.2 | 4745.6 |
| Cumulative<br>Reward @ 10 | 10542.0 | 9155.0 | 8318.8 | 6250.0 |
| Cumulative<br>Reward @ 15 | 11349.6 | 10042.8 | 9292.4 | 7248.0 |
| Cumulative<br>Reward @ 20 | 11877.6 | 10660.2 | 9965.8 | 7928.2 |

<br>
- Table 2. Click Performance Comparison

| Method | W.O. feature | W. Feature<br> $\lambda=0.1$ | W. Feature<br> $\lambda=0.2$ | W. Feature<br> $\lambda=0.5$ |
|---|---|---|---|---|
| Click HR/NDCG @ 5 | 0.265/0.205 | 0.222/0.167 | 0.194/0.143 | 0.139/0.100 |
| Click HR/NDCG @ 10 | 0.315/0.221 | 0.275/0.184 | 0.248/0.160 | 0.188/0.116 |
| Click HR/NDCG @ 15 | 0.343/0.229 | 0.305/0.192 | 0.280/0.169 | 0.219/0.124 |
| Click HR/NDCG @ 20 | 0.362/0.233 | 0.326/0.197 | 0.302/0.174 | 0.241/0.129 |

<br>
- Table 3. Purchase Performance Comparison

| Method | W.O. feature | W. Feature<br> $\lambda=0.1$ | W. Feature<br> $\lambda=0.2$ | W. Feature<br> $\lambda=0.5$ |
|---|---|---|---|---|
| Purchase HR/NDCG @ 5 | 0.527/0.443 | 0.435/0.348 | 0.385/0.299 | 0.274/0.209 |
| Purchase HR/NDCG @ 10 | 0.582/0.461 | 0.502/0.370 | 0.461/0.324 | 0.340/0.230 |
| Purchase HR/NDCG @ 15 | 0.609/0.468 | 0.535/0.379 | 0.502/0.335 | 0.390/0.243 |
| Purchase HR/NDCG @ 20 | 0.625/0.472 | 0.557/0.384 | 0.531/0.342 | 0.419/0.250 |


## Conclusion
Based on the comparison results under different settings shown in the above tables, we found that adding side information as features does not yield better performance in terms of accumulative reward, click HR, click NDCG, purchase HR, purchase NDCG, especially when the weight of side information $\lambda$ has a larger value. 

Furthen investioation is required to find out the reason of performance degration after mixing side information. One reason might be the side information is not helpful/irrelevant to task. Another reason might be the way that combines the side information is not well-designed. In current approach, the combination is done via a linear fucntion, which might limit the learning capability. A better approach might be concatenating two tensors and using a fully-connected layer to combine the information within the two information channels.
