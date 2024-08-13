 Reddit API Project

This project interacts with the Reddit API to perform various tasks such as fetching the number of subscribers of a subreddit, retrieving the top 10 hot posts, and recursively fetching all hot posts.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
  - [Task 0: Number of Subscribers](#task-0-number-of-subscribers)
  - [Task 1: Top Ten](#task-1-top-ten)
  - [Task 2: Recurse It](#task-2-recurse-it)
- [Files](#files)
- [License](#license)

## Installation

To get started, ensure you have Python installed on your system. Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/yourusername/alx-system_engineering-devops.git
cd alx-system_engineering-devops/0x16-api_advanced
```

No additional libraries are required beyond the standard Python library.

## Usage

### Task 0: Number of Subscribers

**Function:** `number_of_subscribers(subreddit)`

This function queries the Reddit API and returns the total number of subscribers for a given subreddit. If the subreddit is invalid, it returns `0`.

**Example:**

```bash
$ python3 0-main.py programming
756024

$ python3 0-main.py this_is_a_fake_subreddit
0
```

### Task 1: Top Ten

**Function:** `top_ten(subreddit)`

This function queries the Reddit API and prints the titles of the first 10 hot posts listed for a given subreddit. If the subreddit is invalid, it prints `None`.

**Example:**

```bash
$ python3 1-main.py programming
Firebase founder's response to last week's "Firebase Costs increased by 7000%!"
How a 64k intro is made
HTTPS on Stack Overflow: The End of a Long Road
...


### Task 2: Recurse It

**Function:** `recurse(subreddit, hot_list=[])`

This recursive function queries the Reddit API and returns a list containing the titles of all hot articles for a given subreddit. If the subreddit is invalid or there are no results, it returns `None`.
