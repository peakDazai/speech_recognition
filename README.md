# speech_recognition
speech_recognition doesn't work

    import speech_recognition as sr

    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("Say something!")
        r.record(source, duration=2)
        audio = r.listen(source)

    try:
        print("Google Speech Recognition thinks you said " + r.recognize_google(audio))
    except sr.UnknownValueError:
        print("Google Speech Recognition could not understand audio")
    except sr.RequestError as e:
        print("Could not request results from Google Speech Recognition service; {0}".format(e))
