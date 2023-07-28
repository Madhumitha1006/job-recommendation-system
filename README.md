
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
