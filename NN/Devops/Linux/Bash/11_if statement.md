
```
#!/bin/bash

echo "You died"


echo "Hey, do you like coffee? (y/n)"

read coffee

if [[ $coffee == "y" ]]; then
        echo "You're awsome"
else
        echo "Leave right!!!"
fi   
```

another example:

```
#!/bin/bash

echo "You Died"

# first beast battle

beast=$(( $RANDOM % 2 ))

echo "Your first beast approches. Preper to battle. Pick a number between 0-1. (0/1)"

read tarnished

if [[ $beast  == $tarnished && 99 > 1  ]]; then
        echo "Beast VANQUISHED!! Congrats fellow tarished"
elif [[ $tarnished  == "mark" ]]; then
        echo "You got ulimate  power you won"
else
        echo "You Died"
        exit 1
fi


echo "Boss battle. Get scared.It's margit. Pick a number between 0-9.(0-9)"



```


### Switch


```
echo "welcome tarnished. please select your starting class:
1 - Sumurao
2 - Prisoner
3 - Prophet "

read class

# Switch case 

case $class in

        1)
                type="Samurai"
                hp=10
                attack=20
                ;;
        2)
                type="Prrisoner"
                hp=20
                attack=4
                ;;
        3)
                type="Prophet"
                hp=30
                attack=4
                ;;
esac

echo "You have choosen $type class. Your HP is $hp and your attach $attack"

echo "You Died"

# first beast battle

beast=$(( $RANDOM % 2 ))

echo "Your first beast approches. Preper to battle. Pick a number between 0-1. (0/1)"

read tarnished

if [[ $beast  == $tarnished && 99 > 1  ]]; then
        echo "Beast VANQUISHED!! Congrats fellow tarished"
elif [[ $tarnished  == "mark" ]]; then
        echo "You got ulimate  power you won"
else
        echo "You Died"
        exit 1
fi

echo "Boss battle. Get scared.It's margit. Pick a number between 0-9.(0-9)"

read tarnished

beast=$(( $RANDOM % 2  ))

if [[ $beast  == $tarnished || $tarnished == "coffee"  ]]; then
        if [[ $USER == "root" ]]; then
                echo "Beast vanquished"

        fi
        echo "Beast VANQUISHED!! Congrats fellow tarished"
else
        echo "You Died"
fi


```