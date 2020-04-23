4/19 [
  - how to navigate with the command line
      -cd, pwd, ls, man, head, tail, more, wc
  - how to interact with files and directories
      -mkdir, echo, cut, cp, grep, awk
  - using nano for scripting within a bash terminal
      - #!/bin/bash for the hashbang to open a bash script
      - "" double quotes allowing for variables in strings
      - '' (strong quotes) nothing within them is interpreted
      - no quotes literal interpretation and need to use escape characters
  - command subsitution
      - x=$([command])
          - ie -> x=$(ping -c 1 [file] | grep 'bytes from' | cut -d = -f 4)
  - interpret variables "$variable" 
  - arithmatic, logical and comparison operators
      - comparison operators return 0: true 1: false
  - string null values
  - string manipulation
      - length ${#str}
      - substring ${str:#}
          - ${str:#:count} 
      - replace 
          only first instance -> ${str/replace/replacement}
          all instances -> ${str//replace/replacement}
          only if first element -> ${str/#replace/replacement}
          only if last element -> ${str/%replace/replacement}
          if matches x -> ${str/*x/replacement}
      - colors 
          '\033[style;foreground;background m TEXT HERE \033[0m'
              style -> text style
              foreground -> foreground (text) color
              background -> background color
              0 -> resets color to normal
          -tput can be used for colors as well
  - handy helpers
      - date: returns dd mm hh:mm:ss timezone yyyy
          - can be formatted -> date +"%d-%m-%Y -> dd-mm-yyyy
      - printf: format strings 
          ie -> "Name: \t%s\nID: \t%s\n" "string_1" string_2"
              -> Name:  string_1
                 ID:    string_2
  - arrays
      arr[n]=item_n -> adds item_n at nth position in the array
      arr+=item -> addes item to the end of the array
      arr[@] -> returns the whole array
      arr[@:-1] -> returns the last element of the array
      - do not use commas in array declaration 
          - arr=("item_1" "item_2" "item_3")
      - can make key:value arrays
          declare -A arr
          arr[key]=value
          arr["key space"]=value
  - working with files
      - echo "some text" > file.txt -> writes text to a text file and over writing the file if it exists
      - echo "some more text" >> file.txt -> adds text to a text file does not overwrite
      - > file.txt -> empties a file of all text
  - while loop
      while [condition]; do
        [command]
      done
  - for loop
      for ((i=0; i<=n; i++)) 
      do
        [command(s)]
      done
  - reading files with loops
      while read var; do
        [command]
      done < [file_to_read]
      ie -> while read ln; do
        echo $f 
      done < file.txt 
  - Here document
      - specify input freely to a given limit or specify options to an interactive command
]