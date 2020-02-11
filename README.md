# Writing C# Code using Jupyter Notebooks

## Installation

Follow the instructions [from Microsoft here.](https://github.com/dotnet/interactive)

## What is Jupyter?
Jupyter is a web based interactive environment for combining code execution, human readable text and other media. 
Jupyter is often used for science based applications, since it can show the computing logic behind a calculation. It is stored as a JSON object,
allowing a Jupyter Notebook to be checked in to source control and shared with others collaboratively.

Jupyter Notebooks allow you to create three types of cells, `Code`, `Markdown` and `Raw`. This allows the user to create documentation for their code while writing it.

In addition to this, Jupyter supports outputting formats such as standard output from the kernel, images and graphs. 

## Jupyter Uses in this Project
My first use of Jupyter was for work, and I used it to send events to an Evwnt Hubs instance, so I extended that use for this project. If you would like to use this
project for that purpose, you can simply change the connection strings in this project to accomodate your conneciton strings and hub names and you can try it yourself!

## Jupyter & .NET
The preview version of .NET Jupyter notebooks supports both the C# and F# kernels, allowing prospective users either language to code.

## Pitfalls

The .NET version of Jupyter has a couple of pitfalls:

- Lack of code completion/Intellisense
    - This one is pretty self explanatory, if you don't have a strong grasp of what you're doing without some form of code completion, it may be easier to use an IDE.
    One example I had of this was writing fake data using the Bogus package. I ended up importing my code into Visual Studio for the code completion, then
    moving that code back to Jupyter for the execution. 
- Inability to create listener blocks without a loop
    - For example, I tried to create an Event Hubs listener using a Jupyter C# notebook and was unable to listen to the events in the manner that I expected initially.
    This seems to be by design, as each code block runs until completion.
- Inability to use some features in .NET
    - In this project, I am unable to access `System.Configuration.ConfigurationManager` even though I included a reference to it, therefore I was unable to successfully
    create a Cosmos DB based project in Jupyter

## Considerations

The .NET Jupyter notebook is still in Preview, so it can have some undesired bugs and behaviors. Hopefully these issues are smoothed as the project matures. But until then, it is a neat little tool!

## Other Resources

- [Jupyter Documentation](https://jupyter-notebook.readthedocs.io/en/latest/index.html)
- [Announcing .NET Jupyter Notebooks by Scott Hanselman](https://www.hanselman.com/blog/AnnouncingNETJupyterNotebooks.aspx)