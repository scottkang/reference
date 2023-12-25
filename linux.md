# Exit code
$?
128 + N = signal N으로 종료
137 = 128 + 9

# if then
#!/bin/sh
num=10
if [ $num == 10 ]
then
    echo "Match"
fi
num=10
if [ $num -eq 10 ]
then
    echo "Match"
fi

If not enclosed with [], $num replaced with 10, and treated as a command - 10: command not found 
