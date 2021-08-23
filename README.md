# Notes syncing across machines

[Original article](https://www.atlassian.com/git/tutorials/notes)

## Set up the system (first time)
```bash
git init --bare $NOTES_DIR/.cfg
alias notes='/usr/bin/git --git-dir=$NOTES_DIR/.cfg/ --work-tree=$NOTES_DIR'
echo "alias notes='/usr/bin/git --git-dir=$NOTES_DIR/.cfg/ --work-tree=$NOTES_DIR'" >> $NOTES_DIR/.zshrc
```

## Set up the system (with existing notes repo)

```bash
cd $NOTES_DIR
echo "alias notes='/usr/bin/git --git-dir=$NOTES_DIR/.cfg/ --work-tree=$NOTES_DIR'" >> $NOTES_DIR/.zshrc
source .zshrc
echo ".cfg" >> .gitignore
git clone --bare git@github.com:mvezer/notes.git $NOTES_DIR/.cfg
notes checkout
```

