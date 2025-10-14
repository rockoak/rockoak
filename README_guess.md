from ast import Break
import random


def main() -> None:
    while True:
        target = random.randint(0, 100)
        attempts = 0

        while True:
            attempts += 1
            user_input = input(f"第{attempts}次 - 請輸入 0 到 100 的整數來猜測：")

            try:
                guess = int(user_input)
            except ValueError:
                print("請輸入有效的整數。")
                continue

            if guess > target:
                print("..太大了")
            elif guess < target:
                print(".太小了")
            else:
                print(f"恭喜你，猜對了！答案是 {target}")
                break

        retry = input("要再玩一次嗎？(y/n)：").strip().lower()
        if retry != "y":
            print("遊戲結束，再見！")
            break
           
if __name__ == "__main__":
    main()
