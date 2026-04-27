# Instructions for Student B

Repository: https://github.com/Endsieg1997/exp

This repository is used for Exercise 1 and Exercise 3.

## Exercise 1: Within-Team Pull Request

Student B should do:

```bash
git clone https://github.com/Endsieg1997/exp.git
cd exp
git checkout main
git pull origin main
git checkout -b feature/add-b-name
```

Make a small change, for example create a file named `student-b.txt`:

```text
Student B: your name here
```

Then commit and push:

```bash
git add .
git commit -m "Add Student B file"
git push origin feature/add-b-name
```

Open a pull request on GitHub:

- base repository: `Endsieg1997/exp`
- base branch: `main`
- compare branch: `feature/add-b-name`

Student A will review and merge it.

## Exercise 3: Conflict Resolving

After Exercise 1 is merged, Student B should update local `main`:

```bash
git checkout main
git pull origin main
git checkout -b feature/b-conflict-change
```

Edit `conflict.txt`. Change the line that starts with `Shared line:` to your own text.

Then commit:

```bash
git add conflict.txt
git commit -m "Change conflict line as Student B"
```

Wait until Student A has merged their conflicting change first. Then update your branch:

```bash
git fetch origin
git merge origin/main
```

Git should report a conflict in `conflict.txt`. Open the file, remove the conflict markers, keep the final agreed text, then run:

```bash
git add conflict.txt
git commit
git push origin feature/b-conflict-change
```

Finally, create a pull request to `Endsieg1997/exp:main`.
