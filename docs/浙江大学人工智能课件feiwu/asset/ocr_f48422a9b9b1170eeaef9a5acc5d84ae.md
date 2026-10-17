# # Monte-Carlo Planning

There are two distinct policies:

+   • Tree Policy: Select or create a leaf node from the nodes already contained within the search tree (selection and expansion). The tree policy must trade off exploration and exploitation.

+   • Default Policy: Play out the domain from a given non-terminal state to produce a value estimate (simulation).