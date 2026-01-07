# Simple-login-system-
A simple login system that I coded


# Sample user database
users_db = {}

def hash_password(password):
    return hashlib.sha256(password.encode()).hexdigest()

def register(username, password):
    if username in users_db:
        return "Username already exists."
    users_db[username] = hash_password(password)
    return "User registered successfully."

def login(username, password):
    if username not in users_db:
        return "Username not found."
    if users_db[username] == hash_password(password):
        return "Login successful."
    return "Invalid password."

# Example usage
print(register("user1", "password123"))
print(login("user1", "password123"))
print(login("user1", "wrongpassword"))
