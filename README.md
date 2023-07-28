
# Job Recommendation System

Implementation of batch and real-time
recommendation systems using RP3Beta model, a simple scalable graph-based model that outperforms multiple more advanced models.

Currently, implemented model:
https://ieeexplore.ieee.org/document/10054029


## Requirements
    1. Python
    2. Networkx
## Data
The input data file interactions.csv should be stored in the same directory. The file is expected to contain the following columns: user, item, event, timestamp.

In order to use your own data, you have to provide a csv file with four columns:

    1. users : a numeric id representing the user who made the interaction
    2. jobs : a numeric id representing the item the user interacted with
    3. events : a type of interaction between the user and the item, possible values are:
        click: the user visited the item detail page
        bookmark: the user added the item to bookmarks
        chat_click: the user opened the chat to contact the item’s owner
        contact_phone_click_1: the user revealed the phone number attached to the item
        contact_phone_click_2: the user clicked to make a phone call to the item’s owner
        contact_phone_click_3: the user clicked to send an SMS to the item’s owner
        contact_partner_click: the user clicked to access the item’s owner external page
        contact_chat: the user sent a message to the item’s owner
    4. timestamps : the Unix timestamp of the interaction


In this example, we load OLX Jobs Interactions Dataset from Kaggle. The dataset can be found here: https://www.kaggle.com/datasets/olxdatascience/olx-jobs-interactions.

## Models
* RP3 batch recommendation model
* RP3 real-time recommendation model
## Job Recommendation System
![1-graph](https://github.com/Madhumitha1006/job-recommendation-system/assets/139626463/e081bc94-877e-4d0a-94e0-ad4fe5fbb9bc)

Let us denote the set of users by U and the set of items
by I. We represent our data as a bipartite graph in which the
parts are users and items, while edges represent interactions
between them. Let N (x) be the set of neighbours of the node
x.
The model calculates a score rui representing the relevance
of item i ∈ I for user u ∈ U, as the sum of the scores assigned to the paths of length 3 connecting u and i.

![1-realtime](https://github.com/Madhumitha1006/job-recommendation-system/assets/139626463/1b3e2d99-f5b6-45c0-9ca7-2cb5d0e01c64)

The interaction store – depending on implementation – can
reflect the most recent user behaviour in almost real time,
while the item-to-item recommendation store is updated only
after completion of the batch prediction step.
When requesting personalized recommendations for a user,
the aggregator component retrieves up to M most recent
interactions Iu = {ik : k ≤ M} from the interaction store.
Then for each of the unique returned items a list of similar
items S(Iu) is fetched
from the item-to-item recommendation store. The RP3Beta model recommends the items with the
highest score excluding the items with which the user has
interacted.
