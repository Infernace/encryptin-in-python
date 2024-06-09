# encrypting



from cryptography.fernet import Fernet

# Function to generate a key and save it to a file
def generate_key():
    key = Fernet.generate_key()
    with open("secret.key", "wb") as key_file:
        key_file.write(key)

# Function to load the key from a file
def load_key():
    return open("secret.key", "rb").read()

# Function to encrypt a message
def encrypt_message(message):
    key = load_key()
    f = Fernet(key)
    encrypted_message = f.encrypt(message.encode())
    return encrypted_message

# Function to decrypt a message
def decrypt_message(encrypted_message):
    key = load_key()
    f = Fernet(key)
    decrypted_message = f.decrypt(encrypted_message)
    return decrypted_message.decode()

if __name__ == "__main__":
    generate_key()  # Generate and save the key

    message = "This is a secret message"
    print(f"Original message: {message}")

    encrypted_message = encrypt_message(message)
    print(f"Encrypted message: {encrypted_message}")

    decrypted_message = decrypt_message(encrypted_message)
    print(f"Decrypted message: {decrypted_message}")

