# Multimedia-Encryption

This project presents a novel encryption and decryption algorithm inspired by the randomization properties of a shuffled deck of cards. The algorithm encrypts and decrypts images by applying a complex permutation technique using S-Boxes and P-Boxes derived from card decks.

Algorithm Overview
1. Conceptual Basis
Permutation & Randomization: The algorithm leverages the vast number of permutations in a deck of 52 cards (52!), translating this into a robust randomization mechanism for encryption.
S-Box and P-Box Generation: A single S-Box is generated, representing a 4x13 matrix corresponding to a deck of cards. For larger images, multiple decks are used, ensuring no values are repeated.
2. Image Preparation
Image Resizing: Input images are resized to 512x512 pixels.
Channel Separation: The image matrix is split into three separate matrices corresponding to the red, green, and blue channels.
3. Encryption Process
Card Selection: Randomly selects cards from a deck by choosing a deck number, a card value, and a suit. These selections form the basis for the P-Box creation.
S-Box Creation: The S-Box is populated with all possible card values for each deck, organized by suit, ensuring no duplicates.
P-Box Creation: For each pixel in the image, a P-Box is generated using the S-Box, ensuring a unique mapping for the red, green, and blue channels.
Pixel Rearrangement: The encryption function rearranges the pixels in each channel based on the P-Box, creating an encrypted image.
4. Decryption Process
Channel Decryption: The encrypted image is split into its RGB channels, and the corresponding P-Box for each channel is used to reverse the encryption process.
Pixel Reordering: Pixels are reordered based on the original positions specified by the P-Box to retrieve the original image.
Final Image Reconstruction: The decrypted matrices of each channel are merged to obtain the final decrypted image.

**RESULTS**

![image](https://github.com/user-attachments/assets/390048bc-27f8-4f2b-8721-fcfba1c72d1e) <br/>
Fig : Original Image <br/>

![image](https://github.com/user-attachments/assets/aeb04dde-9cf4-4509-b10e-4c0f048a12da)
Fig : Encrypted Image <br/>

![image](https://github.com/user-attachments/assets/71bd8f06-37f7-4498-9e46-43867b8e284a)
Fig : Decrypted Image <br/>
