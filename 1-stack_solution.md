```
"""
One way to reverse a sentence in Python using stacks.
"""

def reverse_sentence(original_sentence, reverse_stack, result):
    # reverse the sentence
    for char in range(len(original_sentence)):
        # by taking the last character in the original stack
        last_char = original_sentence.pop()
        # and appending it to the reverse stack
        reverse_stack.append(last_char)

    # build reverse sentence from reverse stack
    for char in range(len(reverse_stack)):
        # by looping through reverse stack to build reverse sentence
        result = result + reverse_stack[char]

    # show the reversed sentence
    print(result)
    
# Three sentences to reverse
sentence_1 = ".gnitseretni efil sekam taht eurt emoc maerd a gnivah fo ytilibissop eht s'tI"
sentence_2 = ".ssendlob ,namow gnuoy a ni ,ytidimit si nam a ni evol eurt fo motpmys tsrif ehT"
sentence_3 = ".eveileb uoy tahw rof gnireffus dna gnivil ni si egaruoc laer ehT .nommoc etiuq yllautca s'ti ;sfeileb rieht rof deid evah elpoep ynam taht dnim ni peeK"

# Reverse the first sentence
reverse_stack = []                      # provide empty stack
result = ""                             # provide placeholder for the reversed sentence
original_sentence = list(sentence_1)    # convert the original sentence into a list/stack
reverse_sentence(original_sentence, reverse_stack, result)

# Reverse the second sentence
reverse_stack = []                      # provide empty stack
result = ""                             # provide placeholder for the reversed sentence
original_sentence = list(sentence_2)    # convert the original sentence into a list/stack
reverse_sentence(original_sentence, reverse_stack, result)

# Reverse the third sentence
reverse_stack = []                      # provide empty stack
result = ""                             # provide place holder for the reversed sentence
original_sentence = list(sentence_3)    # convert the original sentence into a list/stack
reverse_sentence(original_sentence, reverse_stack, result)
```
