# Define emotional ranges for each condition
condition_ranges = {
    1: {"min": -5, "max": 5, "emotions": ["Panic", "Terror", "Anxiety", "Stress", "Concern", "Neutral", "Calm", "Relief", "Contentment", "Confidence", "Optimism"]},
    2: {"min": -5, "max": 5, "emotions": ["Despair", "Depression", "Melancholy", "Blue", "Nostalgia", "Neutral", "Satisfaction", "Happiness", "Joy", "Elation", "Euphoria"]},
    3: {"min": -5, "max": 5, "emotions": ["Violence", "Fury", "Anger", "Frustration", "Annoyance", "Neutral", "Understanding", "Compassion", "Love", "Peace", "Serenity"]},
    # Conditions 4, 5, 6 would be similarly defined...
}

# Define emotional responses for each condition and intensity level
emotional_responses = {}
for condition, details in condition_ranges.items():
    emotions = details["emotions"]
    for intensity, emotion in enumerate(emotions):
        emotional_responses[(condition, intensity + details["min"])] = emotion

# Get user input for condition and intensity level
condition = int(input("Enter condition (1-6): "))
intensity = int(input("Enter intensity level (-5 to 5): "))

# Look up emotional response for given condition and intensity level
if (condition, intensity) in emotional_responses:
    emotion = emotional_responses[(condition, intensity)]
    print("Emotion: ", emotion)
else:
    print("Invalid input.")
