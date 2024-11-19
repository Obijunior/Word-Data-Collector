def clean_word(word):
    chars_to_remove = '!?:;,|.[]()-"'
    word = word.lower()
    word = word.strip()
    for x in chars_to_remove:
        word = word.replace(x, "")
    return word

def build_count(text):
    contents = {}
    with open(text, "r") as file:
        for x in file:
            for word in x.split():
                word = clean_word(word)
            if word:
                if word in contents:
                    contents[word] += 1
                else:
                    contents[word] = 1
    return contents

def main():
    print(" Welcome to the Word Counter! ".center(40, "="))
    file = input("Enter a file name: ")
    word_count = build_count(file)
    print(f"The file '{file}' has been processed.")
    with open("word_data.txt", "w") as word_count_file:
        for i in word_count:
            word_count_file.write(f"{i} : {word_count[i]}\n")
    with open("unique_words.txt", "w") as unique_words_file:
        unique_words_file.write("This is a list of all words that appear exactly once in the file:\n\n")
        for i in word_count:
            if word_count[i] == 1:
                unique_words_file.write(i+'\n')
    print("Output stored in word_data.txt and unique_words.txt")
    print("Exiting...")


main()
