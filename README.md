- 👋 Hi, I’m @78954202
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
78954202/78954202 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
**// app.convex

// Define the User data type
type User {
  id: Int
  username: String
  email: String
  password: String
}

// Define the Post data type
type Post {
  id: Int
  title: String
  content: String
  author: User
  comments: [Comment]
  createdAt: DateTime
}

// Define the Comment data type
type Comment {
  id: Int
  content: String
  author: User
  post: Post
  createdAt: DateTime
}

// Initialize the users array
users: [User] = [
  { id: 1, username: "admin", email: "admin@example.com", password: "password" }
]

// Initialize the posts array
posts: [Post] = []

// Initialize the comments array
comments: [Comment] = []

// Function to create a new user
create_user(username: String, email: String, password: String): User {
  let new_user = { id: users.length + 1, username, email, password }
  users.push(new_user)
  return new_user
}

// Function to create a new post
create_post(title: String, content: String, author: User): Post {
  let new_post = { id: posts.length + 1, title, content, author, comments: [], createdAt: now() }
  posts.push(new_post)
  return new_post
}

// Function to create a new comment
create_comment(content: String, author: User, post: Post): Comment {
  let new_comment = { id: comments.length + 1, content, author, post, createdAt: now() }
  comments.push(new_comment)
  post.comments.push(new_comment)
  return new_comment
}

// Function to get all posts
get_posts(): [Post] {
  posts
}

// Function to get all comments for a post
get_comments(post: Post): [Comment] {
  post.comments
}

// Function to get a user by username
get_user(username: String): User {
  users.find(u => u.username == username)
}**
