# Global versus local representations

+   - Tanh function (shifting the center of sigmoid to 0) has all the properties above
+     - It has large response for input in a large range. Any particular input x is likely to yield activity through several hidden units. This affords a distributed or global representation of the input.
+     - If hidden units have activation functions that have significant response only for input within a small range, then an input x generally leads to fewer hidden units being active - a local representation.
+   - Distributed representations are superior because more of the data influences the posteriors at any given input region.
+   - The global representation can be better achieved with more layers