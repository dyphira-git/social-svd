Explanation of Initial SVD

1. We load the plain Twitter data.
2. Select features upon which to conduct the SVD. For now, it’s just some simple data, like whether the user is verified or a user's follower count.
3. We filter based on the selected features
4. We create another feature, called Nested Followers, where we just add up the followers of the followers for each user and append that to the data frame. This will be replaced with more complicated social graph data in the future
5. We hand-label scores for some users. For now, we give every user with > 1m followers a dummy score of 1 and all with less than 100 followers a dummy score of 0.
6. These features are used to impute a component of an SVD. This imputed component is our _actual_ score. We replace the dummy scores with this.
7. We then find the score of the top and bottom 10 users and print them out.
8. Finally, we write a helper function to query the score of a user given a screen name.
