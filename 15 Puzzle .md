We used [dnSpy](https://github.com/0xd4d/dnSpy) to decompile `Harekaze15Puzzle.exe`.

In `Form1` instance, `this.rnd` is a random number generator that was initialized with a seed.
The seed is `-24110677` that was found by setting a breakpoint.

To get the flag, `this.rnd` have to generate a random number 1001 times.
Perform `FlagGenerator.ShowFlag` with `this.rnd` shows the flag.

 ```
this.rnd = new Random(-24110677);

for (int i = 0; i < 1001; i ++) {
     this.rnd.Next(16);
 }

FlagGenerator.ShowFlag(this.rnd);
```
