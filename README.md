import random
import string
def password_generator(length, complexity):
    lowercase = string.ascii_lowercase
    uppercase = string.ascii_uppercase
    digits = string.digits
    special_chars = string.punctuation
    if complexity == "low":
        chars = lowercase
    elif complexity == "medium":
        chars = lowercase + uppercase
    elif complexity == "high":
        chars = lowercase + uppercase + digits + special_chars
        password = ''.join(random.choice(chars) for _ in range(length))
        return password
def main():
    print("Password Generator Application")
    length = int(input("Enter password length: "))
    print("Select password complexity:")
    print("1. Low (lowercase only)")
    print("2. Medium (lowercase + uppercase)")
    print("3. High (lowercase + uppercase + digits + special characters)")
    complexity_choice = input("Enter complexity (1/2/3): ")
    if complexity_choice == "1":
        complexity = "low"
    elif complexity_choice == "2":
        complexity = "medium"
    elif complexity_choice == "3":
        complexity = "high"
    else:
        print("Invalid complexity choice. Defaulting to medium.")
        complexity = "medium"
        password = password_generator(length, complexity)
        print("Generated Password : ", password)
if __name__ == "__main__":
    main()
