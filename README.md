# File-Compression System Using Huffman Coding in C++:

In this project, I use huffman Coding to compress and decompress the file.The idea is to assign variable length codes to input characters based on their frequencies. The more the frequency of the character the shorter the code assigned to it.
By this idea we compress the file in more efficient and Huffman coding is a lossless data compression algorithm which means we can restores and rebuilds file data in its original form after the file is decompressed.


#Implementation:

The program has been implemented in C++ language. The idea is to reduce the weighted expected storage by means of assigning shorter codes to frequently occurring characters.


#Working:

The following steps are followed to build and traverse the HUFFMAN TREE

1. Find the frequency of each unique character present in the input file and maintain a hashmap.
2. Create a minheap based on the frequencies of characters found out in the previous step. This minheap acts as a priority queue wherein the node containing the character with the least frequency is present at the root (is the root node). The number of independent nodes in this minheap will be equal to the number of unique character present in the input file.
3. Until the number of independent nodes of minheap (it's size) becomes 1, -> keep popping 2 nodes one after the other from the minheap and create a parent node for these nodes -> the first popped node becoming the left child and then -> insert the parent node back into the minheap and run the heapify function.
4 .Now traverse the Huffman Tree in such a way that for every left, take 0 and similarly 1 for right until we reach a node having a character (or a leaf node which won't be having children. The string of 0s and 1s generated now becomes the prefix code of the character.
5 .Create a hashmap mapping each character with its prefix code and this hashmap is written at the start of the compressed/encoded file.


#Output:
<img width="162" alt="image" src="https://user-images.githubusercontent.com/88614647/220401719-c9c2ff24-2b3e-424b-ad7d-7cc69ca8c105.png">
<img width="947" alt="image" src="https://user-images.githubusercontent.com/88614647/220401852-c57d2d11-e889-4575-bf1a-4f108b30b971.png">





#Conclusion:
We can arrive at the conclusion that this lossless data compression algorithm based on HUFFMAN CODING is one of the most efficient ways of encoding and compressing data. Using this, we are able to represent characters that occur more frequently with possibly lesser than 8 bits or 1 byte. Therefore, the number of bits saved by these characters greatly surpasses the extra bits which might possibly be used to represent characters that occur very rarely. This causes the compressed file to occupy (in best cases) less than 50 percent of the original file size that too without losing any kind of data !
