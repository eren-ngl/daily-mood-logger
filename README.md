# daily-mood-logger
A simple Python terminal app to log daily moods and track emotional history (AI-assisted project).
import datetime

FILE_NAME = "moods.txt"

def save_mood(mood):
    today = datetime.date.today().strftime("%Y-%m-%d")
    with open(FILE_NAME, "a") as file:
        file.write(f"{today} | {mood}\n")

def show_moods():
    try:
        with open(FILE_NAME, "r") as file:
            print("\n📖 Your Mood History:\n")
            print(file.read())
    except FileNotFoundError:
        print("\nNo moods logged yet 😌")

def main():
    print("🧠 Daily Mood Logger")
    print("1. Add today's mood")
    print("2. View mood history")

    choice = input("\nChoose an option (1/2): ")

    if choice == "1":
        mood = input("How are you feeling today? 😊 😐 😔 : ")
        save_mood(mood)
        print("✅ Mood saved successfully!")
    elif choice == "2":
        show_moods()
    else:
        print("❌ Invalid choice")

if __name__ == "__main__":
    main()
