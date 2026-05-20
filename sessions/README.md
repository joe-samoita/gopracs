# Check if it works
# Step 1: Login and save cookie
curl -s -c cookies.txt http://localhost:8080/login
# Output: "Login successful" (assuming your login handler shows this)

# Step 2: Verify cookie was saved
ls -la cookies.txt
# -rw-r--r--  1 mac  staff  256 May 20 10:30 cookies.txt

# Step 3: Access protected resource with cookie
curl -s -b cookies.txt http://localhost:8080/secret
# Output: "The cake is a lie!"

# Step 4: Try without cookie (should fail)
curl -s http://localhost:8080/secret
# Output: "Forbidden"

# Step 5: Logout (if you have a logout endpoint)
curl -s -b cookies.txt http://localhost:8080/logout

# Step 6: Try secret again (should now fail)
curl -s -b cookies.txt http://localhost:8080/secret
# Output: "Forbidden"