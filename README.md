# ChatBots-Deep NLP
Goal is to construct a Chatbot that is learnt to have textual conversation like humans using Deep NLP and Seq2Seq Architecture (Bidirectional RNN, TensorFlow, LSTM and end to end memory layers). Applied Beam Search Decoding &amp; Attention mechanisms. 

## Install Anaconda an Getting the DataSet
DataSet: Cornell Movie DataSet: set of 600 movies containing thousands of conversation between lots of characters. 
* 220,579 conversational exchanges between 10,292 pairs of movie characters
* involves 9,035 characters from 617 movies
* in total 304,713 utterances
* movie metadata included: genres, release year, IMDB rating, number of IMDB votes, IMDB rating
* character metadata included: gender (for 3,774 characters) and position on movie credits (3,321 characters)

## Data Preprocessing:

Download two dataset: 1. Lines.txt: that has each line as a record with its line id, user id and movie id.
2. Conversation.txt: This has each conversation as a record. This has line ids, user ids and movie id for that conversation in each row. 

* Creating a dictionary that maps each line and its id.
* Creating a list of all of the conversations.
* Getting separately the questions and the answers
* Clean text
* Creating a dictionary that maps each word to its number of occurrences
* Creating two dictionaries that map the questions words and the answers words to a unique integer: 
This process excludes the words that have occurences below a threshold value and then tokenize the remaining words.
* Adding the last tokens to these two dictionaries: PAD, EOS, OUT, SOS
* Creating the inverse dictionary of the answerswords2int dictionary
* Adding the End Of String token to the end of every answer
* Translating all the questions and the answers into integers and Replacing all the words that were filtered out by OUT
* Sorting questions and answers by the length of questions.

## Building the Seq2Seq model:

Build the brain composed of an encoder and then a decoder and will assemble all of them to build the final brain, which is not trained yet. 

## Training the Seq2Seq model
Set the loss function, the optimizer and then apply stochastic gradient descent to update the weight of the neurons of the brain so it improve the ability to talk with us. 

## Test the Seq2Seq Model
