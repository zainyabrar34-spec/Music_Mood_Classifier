# Music_Mood_Classifier
A Python tool that suggests songs based on your mood. Choose from moods like happy, sad, focus, party, relax, or romantic, and get curated song links instantly.

# Mood dictionary with Hindi + English song links
import random
mood_songs = {
    "happy": [
        "https://youtu.be/WxtJqyIyThU?si=7LLwCCKGeURMAPa2",#kashmir mein tu kanya kumari
       "https://youtu.be/rwn0Zs7ELzc?si=yUfPZWzHhoatnD8V",  # love you zindagi
        "https://youtu.be/6Vbgeiu9AIU?si=5DzrfWX4GTAP06bn"   # wo din bhi kya din the
    ],
    "sad": [
        "https://youtu.be/V0Z75MbFWsg?si=PpW25gdLvU96t41O",  # Toota hua saaz hu mein
        "https://youtu.be/6qwect3_VSE?si=bu4iRTqd0TVKVF0G",  # Banjaara
        "https://youtu.be/KkbUhfIsS0A?si=eCrPegUj7ixirAR-"   #jo tu mera humdard hai
    ],
    "focus": [
        "https://youtu.be/2OEL4P1Rz04",  # Instrumental
        "https://youtu.be/5qap5aO4i9A",  # Lofi Study
        "https://youtu.be/wp43OdtAAkM"   # Piano
    ],
    "party": [
        "https://youtu.be/d1ldnvNoAE4?si=EcUPKzZO2nSXdoyQ",  # suraj dooba hai yaaro
        "https://youtu.be/09R8_2nJtjg",  # Sugar (English)
        "https://youtu.be/fRh_vgS2dFE"   # Sorry (English)
    ],
    "relax": [
        "https://youtu.be/HCWvgoTfUjg?si=Sy_UK4BH57kGe29H",  # mein rang sharbato ka
        "https://youtu.be/pEaY7tryLXM?si=br4B8e2wdxmq5875",  # Raanjhana ve
        "https://youtu.be/O1L80Cw7q3Y?si=hBvqf9nYGMsubFEO"   #jeene laga hu
    ],
    "romantic": [
        "https://youtu.be/shgvjwXZ2nc?si=oWVenPt9a0pSIZfz",  # kaun tujhe
        "https://youtu.be/vEe-UgJvUHE?si=vO7h-QRYml8sKZ8f",  # Raabta
        "https://youtu.be/YQZMG-4gcdQ?si=SYblONF18ycUX3VB"   # hawayein
    ]
}

print("🎵 Welcome to Music Mood Classifier 🎵")
print("Moods available: happy, sad, focus, party, relax, romantic")
print("Type 'exit' to quit\n")

while True:
    mood = input("Enter your mood: ").lower()

    if mood == "exit":
        print("Goodbye! 🎧 Keep enjoying your music.")
        break

    if mood in mood_songs:
        try:
            count = int(input("How many songs do you want? (1-3): "))
        except:
            count = 1

        if count < 1:
            count = 1
        if count > len(mood_songs[mood]):
            count = len(mood_songs[mood])

        songs = random.sample(mood_songs[mood], count)
        print(f"\n🎶 Suggested song(s) for your mood ({mood}):")
        for i, s in enumerate(songs, 1):
            print(f"{i}. {s}")
    else:
        print("😕 Sorry, mood not found. Try again with: happy/sad/focus/party/relax/romantic")

    print("-" * 50)
