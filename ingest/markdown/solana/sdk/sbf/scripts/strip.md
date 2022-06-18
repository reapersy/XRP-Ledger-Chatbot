[View code on GitHub](https://github.com/solana-labs/solana/blob/master/sdk/sbf/scripts/strip.sh)

The `strip.sh` script is a bash script that takes in two arguments: an unstripped shared object file (`$so`) and a stripped shared object file (`$so_stripped`). The purpose of this script is to strip all symbols from the unstripped shared object file and output the result to the stripped shared object file.

The script first checks if the unstripped shared object file exists and is readable. If it is not, the script outputs an error message and exits with a status code of 1. If the unstr