import random
stars = 0
print("===================================")
print("        HACKER TERMINAL GAME V2      ")
print("===================================")

wrongans = 0
userpass = input("Login or Create new account: ").lower()

while userpass not in ["login", "create", "create account", "create new account"]:
    print("Invalid reply")
    userpass = input("Login or Create new account: ").lower()

name = ""
username = ""
password = ""

if userpass == "login":
    name = input("What is your name - ")
    username = input("Username - ")
    password = input("Password - ")
    print("ACCESS GRANTED")
else:
    print("Create your account")
    name = input("What is your name - ")
    username = input("Username - ")

    while True:
        password = input("Password (min 8 chars, 1 number) - ")

        if len(password) < 8:
            print("Too short!")
            continue

        has_number = False
        for n in "0123456789":
            if n in password:
                has_number = True

        if not has_number:
            print("Must include a number!")
        else:
            print("Account created!")
            break

money = 0
de = False
num123 = 0  # FIX: prevents NameError

print("\nYou are an undercover hacker.")
print("Make money by hacking systems.\n")


while True:
    print("==============================")
    print("Money: $", money)
    print("Double Earnings:", de)
    print("Options: CALL | BUY | BALANCE | QUIT")
    if wrongans >= 100:
        wrongstar = 5
    elif wrongans >= 50:
        wrongstar = 4
    elif wrongans >= 25:
        wrongstar = 3
    elif wrongans >= 10:
        wrongstar = 2
    elif wrongans >= 5:
        wrongstar = 1
    else:
        wrongstar = 0

    if money >= 2000:
        moneystar = 5
    elif money >= 1000:
        moneystar = 4
    elif money >= 750:
        moneystar = 3
    elif money >= 500:
        moneystar = 2
    elif money >= 250:
        moneystar = 1
    else:
        moneystar = 0

    stars = max(wrongstar, moneystar)
        
    if stars == 1:
        print("Bounty is ★")
    if stars == 2:
        print("Bounty is ★★")
    if stars == 3:
        print("Bounty is ★★★")
    if stars == 4:
        print("Bounty is ★★★★")
    if stars == 5:
        print("Bounty is ★★★★★")
    print("==============================")

    response = input("What do you want to do? ").lower()


    if response == "call":
        print("\nCalling...\n")
        print("Say your name")

        who = input("Who is this? ").lower()

        if who == name.lower():

            num123 = random.randint(1, 5)  # 1-4 normal calls, 5 = suspicious guy event

            if num123 == 1:
                print("You are a Virgin Media employee")

                reason = input("Why are you calling? ").lower()

                if "internet" in reason or "virgin" in reason or "media" in reason:
                    print("They trust you.")

                    code = random.randint(100000, 999999)
                    print("Ask them for a code")

                    ask = input("What do you say? ").lower()

                    if any(word in ask for word in ["code", "access", "number", "card"]):
                        print("Access code:", code)

                        entered = input("Enter code: ")

                        if entered.isdigit() and int(entered) == code:
                            print("Hack successful!")
                            money += 200 if de else 100
                        else:
                            print("Wrong code!")
                            wrongans = wrongans + 1
                    else:
                        print("They refuse to help")
                        wrongans = wrongans + 1
                else:
                    print("They don't trust your reason")
                    wrongans = wrongans + 1

            elif num123 == 2:
                print("You are a fake lawyer and you are going in court")

                reason = input("Why are you calling? ").lower()

                if "court" in reason or "money" in reason or "lawyer" in reason:
                    print("They trust you.")

                    code = random.randint(100000, 999999)
                    print("Ask them for a code")

                    ask = input("What do you say? ").lower()

                    if any(word in ask for word in ["code", "access", "number", "card"]):
                        print("Access code:", code)

                        entered = input("Enter code: ")

                        if entered.isdigit() and int(entered) == code:
                            print("Hack successful!")
                            money += 200 if de else 100
                        else:
                            print("Wrong code!")
                            wrongans = wrongans + 1
                    else:
                        print("They refuse to help")
                        wrongans = wrongans + 1
                else:
                    print("They don't trust your reason")
                    wrongans = wrongans + 1
                    

            elif num123 == 3:
                print("You are a fake banker")

                reason = input("Why are you calling? ").lower()

                if "bank" in reason or "money" in reason:
                    print("They trust you.")

                    code = random.randint(100000, 999999)
                    print("Ask them for a code")

                    ask = input("What do you say? ").lower()

                    if any(word in ask for word in ["code", "access", "number", "card"]):
                        print("Access code:", code)

                        entered = input("Enter code: ")

                        if entered.isdigit() and int(entered) == code:
                            print("Hack successful!")
                            money += 200 if de else 100
                        else:
                            print("Wrong code!")
                            wrongans = wrongans + 1
                    else:
                        print("They refuse to help")
                        wrongans = wrongans + 1
                else:
                    print("They don't trust your reason")
                    wrongans = wrongans + 1

            elif num123 == 4:
                print("You are an architect")
                print("Say how their house is weakening")

                reason = input("Why are you calling? ").lower()

                if "architect" in reason or "fragile" in reason or "house" in reason or "weak" in reason:

                    housecode = random.randint(1, 2)

                    if housecode == 1:
                        print("I just bought the house")

                        print("They are suspicious but continue...")

                        reasonhouse = input("Are you lying? ").lower()

                        if "no" in reasonhouse:
                            print("They trust you.")

                            code = random.randint(100000, 999999)
                            print("Ask them for a code")

                            ask = input("What do you say? ").lower()

                            if any(word in ask for word in ["code", "access", "number", "card"]):
                                print("Access code:", code)

                                entered = input("Enter code: ")

                                if entered.isdigit() and int(entered) == code:
                                    print("Hack successful!")
                                    money += 200 if de else 100
                                else:
                                    print("Wrong code!")
                                    wrongans = wrongans + 1
                            else:
                                print("They refuse to help")
                                wrongans = wrongans + 1
                        else:
                            print("They don't trust you")
                            wrongans = wrongans + 1
                    else:
                        print("Call failed. They are suspicious.")
                        wrongans = wrongans + 1
                else:
                    print("They don't trust your reason")
                    wrongans = wrongans + 1

            elif num123 == 5:
                yesno = random.randint(1, 2)
                if stars == 1:
                    print("Hello how are you")

                print("Say, I need your digital code to see your virtual activities ")
                bountystar11 = input("Why are you calling? ").lower()
                if "digital" in bountystar11 or "code" in bountystar11 or "vistual" in bountystar11 or "activtys" in bountystar11:
                    print("Something about you doesn't seem right.")
                    print("You called me out of nowhere")
                    print("now you're asking for a verification code?")
                    question1 = input("Mind if I ask you a few questions? ").lower()
                    if "yes" in question1 or "sure" in question1:
                        pass
                    else:
                        print("Dialing police")
                        stars += 1
                        wrongans += 1

                    qbounty1 = input("Why are you calling me out of nowhere? ").lower()
                    if "verify" in qbounty1 or "code" in qbounty1 or "digital" in qbounty1 or "vistual" in qbounty1:
                        print("Oh... I see.")
                        bountystar12 = input("How did you get my phone number? ").lower()
                        bountystar13 = ""
                        if "company" in bountystar12 or "database" in bountystar12 or "business" in bountystar12:
                            print("I see, understood.")

                            bountystar13 = input("What if I don't give you my verification code? ").lower()
                        if "have" in bountystar13 or "to" in bountystar13 or "dont" in bountystar13:
                            if yesno == 1:
                                print("Okay.")

                        else:
                            print("Nice talking to you.")

                        bountystar14 = input("Why do you need my verification code? ").lower()
                        if "account" in bountystar14 or "owner" in bountystar14 or "confirm" in bountystar14:
                            print("Okay, I trust you.")
                            code = random.randint(100000, 999999)
                            print("Access code:", code)
                            entered = input("Enter code: ")
                            if entered == str(code):
                                print("Hack successful!")
                                money += 600 if de else 300
                    else:
                        print("They didn't ask about a verification code.")
                else:
                    print("They don't trust you")
                    wrongans = wrongans + 1

        else:
            print("They don't trust you")
            wrongans = wrongans + 1

    elif response == "buy":
        print("\n===== SHOP =====")
        print("Double Earnings - $150")

        if de:
            print("Already owned")
        elif money < 150:
            print("Not enough money")
        else:
            choice = input("BUY or PASS: ").lower()

            if choice == "buy":
                money -= 150
                de = True
                print("Double earnings activated!")
            else:
                print("Cancelled")

    elif response == "balance":
        print("Money:", money)

    elif response == "quit":
        print("Exiting game...")
        break
    else:
        print("Invalid option")



