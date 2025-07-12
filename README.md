# Classical-Cipher-Cryptanalysis
A  Python tool to break a columnar transposition cipher using brute-force key permutation and frequency analysis heuristics
Classical Cipher Cryptanalysis Tool (English)
This project is a Python-based tool designed to break a Columnar Transposition Cipher through a combination of brute-force attack and frequency analysis heuristics. Given a ciphertext, the script systematically tests all possible keys of a predefined length to find the original plaintext.

The Cipher: Columnar Transposition
A columnar transposition cipher is a classical cipher where the plaintext is written into a grid of a fixed width (determined by the key length), and the ciphertext is read out column by column. The order in which the columns are read is determined by a keyword. This project aims to reverse this process without prior knowledge of the keyword.

The Attack Method
The core of this project is a known-plaintext attack that leverages statistical properties of the English language. The attack proceeds as follows:

Brute-Force Key Permutation: The script assumes a fixed key length (e.g., 7) and generates every possible permutation of the key sequence (e.g., all 7! = 5,040 permutations).

Decryption with Each Key: For each potential key, the script decrypts the entire ciphertext.

Heuristic Scoring: Each resulting plaintext is "scored" based on how "English-like" it is. This implementation uses a simple yet effective heuristic: it counts the occurrences of the most common English word, "the".

Identifying the Correct Key: The plaintext that yields the highest score (i.e., the most occurrences of "the") is assumed to be the correct one. The script then outputs the key that produced this plaintext.

The project also includes a JSON file (Problem3_Freqs.json) containing digram (two-letter) frequencies of the original plaintext, which can be used for more advanced frequency analysis scoring.

🛠️ Technologies Used
Python 3

Standard libraries: itertools (for permutations), collections (for frequency counting).

🚀 How to Use
Run the script from your terminal:

python cryptanalysis.py

(Assuming you have renamed app2 (1).py to cryptanalysis.py)

The script will wait for you to paste the ciphertext. Paste the entire ciphertext as a single line and press Enter.

The script will process all key permutations and then print the most likely key length and the decrypted plaintext.
