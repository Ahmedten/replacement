# replacement
parts_of_speech  = ["PLACE", "PERSON", "PLURALNOUN", "NOUN"]
pofspeech  = ["IDKU", "MOhamed", "Cats", "Tower"]
ahmed = """This is PLACE, no NOUN named PERSON, We have so many PLURALNOUN around here."""

def loword(word,parts_of_speech):
    for toto in parts_of_speech:
        if toto in word:
            return toto
    return None

def game_play(ahmed,pofspeech):
    replaced = []
    ahmed = ahmed.split()
    for word in ahmed:
        replacement = loword(word,parts_of_speech)

        if replacement != None:
            i = parts_of_speech.index(replacement)
            word = word.replace(replacement,pofspeech[i])
            replaced.append(word)
        else:
            replaced.append(word)
    replaced = " ".join(replaced)
    return replaced

print game_play(ahmed,pofspeech)
