# ASU Rate My Professors

I made this because other Rate My Professors extensions for the ASU course catalog were only available on the Chrome web store and were extremely unreliable.

When a user hovers over a professor's name, the extension captures that name and begins the following process:

1. Use regular expressions to remove parentheticals from the name. Text within parenthesis could be preferred pronouns or a nickname.
2. Send name to the Rate My Professors GraphQL API and receive rating data.
3. Check if professor name that we got from the API is the same as the one we hovered over, this is to make sure the API actually returned the correct professor.
4. If the fetch failed, retry with possible nickname. This is done by keeping a hash table that maps names to common nicknames.
5. Display rating data in a small tooltip that appears over the professors name.

![ASU Rate My Professor extension being used to provide professor data](image.png)

In the end I decided to take this extension off of the Firefox add-on store because I felt that Rate My Professors was a terrible metric for determining how good or bad a professor is. Most of the reviews are left by frustrated students who simply found the class difficult. I also didn't want to condone the practice of rating instructors on a scale of 1 to 5. It's disrepectful and dehumanizing.