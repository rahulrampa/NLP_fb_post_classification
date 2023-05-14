# NLP-Facebook-Post-Classification
Conducted transfer learning with HuggingFace's Transformer model to classify more than 2,000 Facebook posts into three distinct categories.

## Background

As one of the largest social media websites in the world, Facebook is an attractive platform for businesses to reach their consumers. Almost all consumer-facing businesses have virtual presence on Facebook, in the form of Facebook business pages (e.g., see [here](https://www.facebook.com/target/) for Target's Facebook business page). Everyday, Facebook users who visit these business pages generate a large amount of posts. These user posts may represent customer complains, questions, or appreciations directed towards the focal businesses. 

For businesses, these user posts contain valuable information about customers' needs and preferences, and understanding what the user posts are talking about represents an important opportunity to get to know your customers in real-time.

## Dataset and Task

I have used **labeled dataset** named "FB_posts_labeled.txt". It is a **tab-delimited** file with the following fields:
- postId: this is a unique identifier for each user post. There are 7961 posts in total;
- message: this is the text of each post;
- Appreciation: this is a binary (0/1) indicator of whether a post is an appreciation;
- Complaint: this is a binary (0/1) indicator of whether a post is a customer complaint;
- Feedback: this is a binary (0/1) indicator of whether a post is a customer feedback (e.g., questions and suggestions).

Appreciation, Complaint, and Feedback are the three mutually exclusive content categories / classes in this dataset. They were labeled by humans, and the labeling isn't perfect (i.e., there may be ambiguous cases where the labels are not appropriate). However, for the sake of this assignment, let's treat them as the ground truth. **Your task is to build a text classifier to predict the content category of a post based on its textual content.** 

To evaluate the out-of-sample performance of your model, you will use it to make predictions for 2039 posts in an **unlabeled dataset** named "FB_posts_unlabeled.txt". It is also a tab-delimited file, but only has postId and message fields. I keep the ground truth labels for these posts in a private place, in order to objectively evaluate your model's performance. The performance metric I will use is **averaged F-measure** across the three categories.
