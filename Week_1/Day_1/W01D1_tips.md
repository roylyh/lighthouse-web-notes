# Roy's Note W01D1

## Gist

A *gist* is just another git repository, except that its interface on GitHub's website is designed specifically for quickly and easily sharing code snippets. 

A **fork** is a GitHub operation (not strictly a git command or feature) by which one GitHub user creates their own copy of another GitHub user's existing repository. It can be done with Gists as well.

The forked repo or gist links back to the original one but the difference is that the forked one is fully controllable by the user that created the fork.
```
git clone git@gist.github.com:YOUR_FORKS_ID.git <your own name>
```

## Git and Dev Workflow

```
mkdir lighthouse-web-notes
cd lighthouse-web-notes
git init
git add README.md
git commit -m  "Blank README.md added"
```

create a new and completely empty repository with the same on GitHub 

Get URL of SSH Link

```
git remote add origin <URL>
git push -u origin master
```

note *` is called backtick character*

## Command Line Args
```
const args = process.argv;
console.log(args);

> node sum.js 10 25
[ 'node',
  '/vagrant/focal/sum.js',
  '10',
  '25' ]
```
suggestion how to get the args
```
args.slice(2);
```

## AssertEqual

```
const errorMsg = "the # is not even";
for (let number = 2; number <= 5; number++) {
  console.log(`the # is ${number}`);
  console.assert(number % 2 === 0, '%o', { number, errorMsg });
}
// output:
// the # is 2
// the # is 3
// Assertion failed: {number: 3, errorMsg: "the # is not even"}
// the # is 4
// the # is 5
// Assertion failed: {number: 5, errorMsg: "the # is not even"}
```