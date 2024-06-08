# Spreadsheet Is All You Need
A nanoGPT pipeline packed in a spreadsheet

This is a project that I did to help myself learn the architecture of GPT.
It is pretty fun to play with, especially when you are trying to figure out what exactly is going on inside a transformer.
This helped me to visualize the entire structure and the dataflow with all the mechanisms inside it to be interactive.

While reading about LLMs, I realised that the internal mechanisms of a transformer is basically a lot of matrices calculation, so I thought why don't I try to visualize it in a spreadsheet.
Then with some trial and errors, I wrote the full inference pipeline of the nanoGPT project into a single spreadsheet.
Therefore **spreadsheet is all you need**.

![**spreadsheet is all you need**](https://github.com/dabochen/spreadsheet-is-all-you-need/blob/main/spreadsheetisallyouneed.jpg?raw=true)


## What components will you see
It contains all the transformer components including:
1. embedding
2. layer norm
3. self attention
4. projection
5. MLP
6. softmax
7. logits

It is based on Andrej Karpathy's NanoGPT structure which includes roughly 85000 parameters.
It is clearly a very small size, but it is both complex enough for me to understand how it works, and also not too big to crash my computer.

## What is included 
In the numbers file "nanoGPT.numbers", you will see two tabs, one called "no weights" and one called "random weights".
They are essentially the same thing, only that all the parameters in the "random weights" tab is randomly generated and the parameters in the "no weights tab" is too tidy it shows weird values down the pipeline, but it is also clearer to help you read it. That's why I kept both.
Due to the internal mechanism of spreadsheet softwares, everytime you update the spreadsheet, all the values will be regenerated again (a bit annoying, and you can avoid it by turning all the values into a static value).
Depending on the processor of your computer this may take a few seconds to update all the values on the page.

The spreadsheet doesn't contain actual trained weights and parameters, so you should not expect it to calculate the correct result for you before you update the parameters.

You might also be wondering if there is an excel version, unfortunately there isn't one yet.
It is simply because the whole pipeline is too large and I need multiple tables to organize everything, and only numbers can do this.
Although I will see if I can recreate this in excel at some point.

## How to read it/use it
Firstly, all the blocks are the values or parameters that is processed through the GPT architecture, they are being color coded as purple, green and orange.

Purple: these are parameters that are supposed be replaced by a trained model's parameter.
Green: these are the values that started from the input and gets transformed into the end results.
Orange: these are just intermediate values that are used for the calculation, they are here so it is less confusing.

Secondly, you should start from the top to the bottom, and there are labels on the left of the page showing what stages you are in.
There are three transformers 0/1/2, each have the same structure and should contain different parameters and data go through all of them in the sequential order.

Lastly, this demo is built with great help from the LLM visualization project (https://bbycroft.net/llm) which uses 3D animations to explain transformers.
I kept the example it used which is about sorting letters.

## What can you do with this
1. Read through the whole spreadsheet will help you to form a visual impression of what a transformer is.
2. Each block contains the actual calculation, which you can double click to watch the details.
3. By selecting the green cells (the values), you can see which other values or parameters are influencing this cell, so that you can get a sense of the mechanism.
4. Try to make changes to the parameters and see what might happen.
5. If you happen to have the weights of NanoGPT, you can replace the parameters in this spreadsheet to get it working properly.



Thanks to the following projects that helped me a lot when creating this spreasheet.
If you are interested in my project, the following links will also be very helpful, much more helpful than spreadsheet is all you need.

1. [Andrej Karpathy's youtube tutorial "Let's build GPT"]([URL](https://www.youtube.com/watch?v=kCc8FmEb1nY)): https://www.youtube.com/watch?v=kCc8FmEb1nY
2. [Andrej Karpathy's NanoGPT project](https://github.com/karpathy/nanoGPT): https://github.com/karpathy/nanoGPT
3. [Brendan Bycroft's 3D visualization of transformers](https://bbycroft.net/llm): https://bbycroft.net/llm
4. [3Blue1Brown's LLM course](https://youtu.be/eMlx5fFNoYc?si=k40zeuPdM_4cB88o): https://youtu.be/eMlx5fFNoYc?si=k40zeuPdM_4cB88o
