# commit hook usage guidelines
 
#### what is it?
- Generally we follow 'feature/\<feature-name>' branching style to name our branches.
- It really helps if you include \<feature-name> in the commit message too as a practice. 
- Adding <feature-name> manually requires a lot of efforts. This post will help you add that with a simple commit hook.

### Steps

1. Firstly, set up a git template directory using the git config command. In this example we’re using the .git-templates folder we’ve created in our home directory:

    ```git config --global init.templatedir '~/.git-templates'```

2. Then create the hooks directory for global hooks in your template folder:

    ```mkdir -p ~/.git-templates/hooks```

3. Afterwards, copy your hooks into this newly created directory and ensure permissions are correctly set on the file. Use ```commit-msg``` file as a hook.

    ```chmod a+x ~/.git-templates/hooks/commit-msg```

4. Done! Now whenever you run git commit, it will prepend the first segments of the branch to the commit message! For existing projects, you just need to reinit the git directory (don’t worry, it won’t break anything!) by running the following in the project root directory:

    ```git init```

5. Example : branch name 'feature/ABC-123'.  After you add a commit, generated message will have a structure [ABC-123] \<commit-message> 

6. If you ever want to stop using this hook just go to ```/.git/hooks``` of your project and remove commit-msg file.
