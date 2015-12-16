#! /bin/bash

RANGE=$(grep -o 'lose' $1 | wc -l)
number=$RANDOM
loops=$2
count=0

text=$(tr '\n' '§' < $1)

while [ $count -lt $loops ]
do 
    count=$[ $count + 1 ]

    if [ $RANGE -eq 0 ] 
    then 
        echo "'lose' not found :/"
        exit 0;
    fi

    let "number = number % $RANGE + 1"
        echo "'lose' at index $number changed to 'loose'"
        RANGE=$[ $RANGE -1 ]
        text=$(echo ${text} | sed s/lose/loose/$number)
done

echo $text | tr '§' '\n'
