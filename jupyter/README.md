## Jupyter Notebook and GitHub

Jupyter Notebook doesn't have a dedicated Git or GitHub integration, but that isn't a bad thing. Without an integration for Git and GitHub, Jupyter Notebook enables you to pick how you want to interact with Git and GitHub. Your interactions with Git and GitHub will occur in an application outside of the Jupyter Notebook, which is where Git really shines.

Git doesn't care _how_ you create or edit files, it tracks the changes regardless of if it happens in a basic text editor or a fully integrated IDE (Integrated development environment) like Eclipse or Microsoft Visual Studio. After you make your desired changes to your `git init`'d notebook, enter `git status` in your command line application and Git will display all of the files you modified.

Create your commits, like you might have done in the Foundation course, and the changes you made to your notebook will now exist within the history of the repository. Let's breakdown what the whole process looks like using Jupyter Notebook.

### Jupyter Notebook flow

Before you can begin making changes, it is important to identify how your Jupyter Notebook currently exists.

- **Not a Git project:** If your project hasn't been initialized as a Git repository, navigate to the repository using a command line application and enter `git init` in the command line. This initializes your existing project as a Git repository.

- **A Git project:** If the notebook project you are using _already_ has been initialized as a Git repository or exists on GitHub, you need to clone it to your local machine.

Now that you have the project on your local machine, it is important to create a `branch` _before_ you create changes. If you started making changes before you created a branch, you can fix that mistake, but ideally you want to create a branch off of the `master` branch before you begin making changes. Your feature branch should have use a naming convention that looks like `username/feature_description`. Create your branch with the following command:

```shell
git checkout -b username/feature_description
```

After creating your branch, open your notebook and make your desired change. Once you have made your desired change, it is back to the command line application. Run the following command:

```shell
git status
```

You will see the file or files that you modified printed out in the command line application. Now you need to stage the changes you made so you can create a commit. To stage the file, run the following command:

```shell
git add filename
```

> NOTE: You can run `git add filename` for each changed file to stage it.

Your file or files have now all moved to the staging area and can be commited to your project history. To create your commit, run the following command:

```shell
git commit -m "a commit message that describes your changes"
```

> NOTE: If you don't use the `-m` modfifier, you can enter a more detailed commit message in a preferred text editor like Atom or Vi.

With your local changes added to a commit, it is time to share your changes with the rest of your team by sending your changes to the GitHub repository. Run the following command:

```shell
git push
```

#### It isn't on GitHub yet

To add an existing project on your local drive to GitHub, see the following documentation: [Adding your project to GitHub](advanced/00-adding-github.md)

#### I get an error when I try to push

If you get an error when you try to push, it is most likely because the branch doesn't exist on GitHub and you need to create a connection between your feature branch and what the feature branch is on the GitHub repository. Run the following command:

```shell
git push --set-upstream origin your-branch-name
```

### Helpful tips for working with Jupyter Notebooks and GitHub

- [GitHub Help: Working with Jupyter Notebook files](https://help.github.com/en/articles/working-with-jupyter-notebook-files-on-github)
- [Nextjournal: How to version control Jupyter Notebooks](https://nextjournal.com/schmudde/how-to-version-control-jupyter)
- [nbdime: tool for diffing and merging Jupyter Notebooks](https://github.com/jupyter/nbdime)
- [Jupyter Notebook Post-save Hook: Auto-convert a Python script and a HTML from the notebook](https://gist.github.com/ceshine/2a68a96e7a9f72551d00c5578249340f)
