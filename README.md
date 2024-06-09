Key Generation:

The generate_key function generates a new key using Fernet.generate_key() and saves it to a file named secret.key. You need to run this function only once to generate and save the key.
Load Key:

The load_key function reads the key from the secret.key file and returns it.
Encrypt Message:

The encrypt_message function takes a plaintext message, loads the key, and encrypts the message using Fernet.encrypt(). The encrypted message is returned.
How to Use:
Generate Key:

Run the script to generate a key and save it to a file. You only need to do this step once. You can comment out or remove the generate_key() call after the key is generated.
Encrypt Message:

The script encrypts a sample message and prints the encrypted message.

You can modify the message variable to any message you want to encrypt.






