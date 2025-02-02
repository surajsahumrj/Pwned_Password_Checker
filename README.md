# Pwned Password Checker

This script checks if a given password has been exposed in a data breach using the [Have I Been Pwned API](https://haveibeenpwned.com/Passwords).

## Features
- Uses the SHA-1 hashing algorithm to securely query the API.
- Implements k-Anonymity by only sending the first 5 characters of the hashed password.
- Provides a count of how many times a password has appeared in breaches.

## Prerequisites
- Python 3.x
- `requests` module (install with `pip install requests` if not already installed)

## Installation
1. Clone the repository:
   ```sh
   git clone <repository-url>
   cd <repository-folder>
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

## Usage
Run the script from the command line and provide one or more passwords as arguments:
```sh
python pwned_password_checker.py <password1> <password2> ...
```

### Example:
```sh
python pwned_password_checker.py password123
```
Output:
```
password123 was found 300123 times... you should probably change your password
```

## How It Works
1. The script converts the password into a SHA-1 hash.
2. It sends the first 5 characters of the hash to the Have I Been Pwned API.
3. The API returns all hashes with the same first 5 characters.
4. The script checks if the full hash is in the returned list and reports how many times it has appeared in breaches.

## Security Considerations
- Your full password is **never** sent to the API.
- The script only transmits the first 5 characters of the SHA-1 hash, preserving privacy.
- However, avoid using this script with highly sensitive passwords on shared or untrusted machines.

## License
This project is licensed under the MIT License.

