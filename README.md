<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>You’ll Be In My Heart - NIKI Chords</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background-color: #f9f9f9;
            color: #333;
        }
        h1 {
            text-align: center;
        }
        select {
            margin: 20px 0;
            padding: 5px;
            font-size: 16px;
            display: block;
            width: 100%;
        }
        pre {
            font-family: monospace;
            background-color: #f4f4f4;
            padding: 20px;
            border-radius: 5px;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        footer {
            text-align: center;
            margin-top: 20px;
            font-size: 12px;
            color: #777;
        }
    </style>
</head>
<body>

    <h1>You’ll Be In My Heart (NIKI)</h1>
    <label for="transpose">Pilih Transposisi:</label>
    <select id="transpose" onchange="transpose(this.value)">
        <option value="0">Asli</option>
        <option value="1">+1</option>
        <option value="-1">-1</option>
        <option value="2">+2</option>
        <option value="-2">-2</option>
    </select>

    <pre id="chords">
C       G      Am      F
Come stop your crying, it'll be alright
C       G       Am        F
Just take my hand, hold it tight
C        G       Am         F
I will protect you from all around you
C        G       Am          F
I will be here, don't you cry

C        G        Am       F
For one so small, you seem so strong
C        G        Am         F
My arms will hold you, keep you safe and warm
C        G        Am      F
This bond between us can't be broken
C        G        Am       F
I will be here, don't you cry

C          G         Am         F
'Cause you'll be in my heart
C         G         Am          F
Yes, you'll be in my heart
C       G         Am        F
From this day on, now and forever more

C          G         Am         F
You'll be in my heart
C         G         Am         F
No matter what they say
C         G         Am         F
You'll be here in my heart, always
C          G         Am         F
You'll be in my heart
C         G         Am         F
Always

C        G        Am       F
Why can't they understand the way we feel?
C        G        Am      F
They just don't trust what they can't explain
C         G        Am         F
I know we're different, but deep inside us
C        G        Am      F
We're not that different at all

C          G         Am         F
And you'll be in my heart
C         G         Am         F
Yes, you'll be in my heart
C        G         Am       F
From this day on, now and forever more

C          G         Am         F
You'll be in my heart
C         G         Am         F
No matter what they say
C         G         Am         F
You'll be here in my heart, always
C          G         Am         F
You'll be in my heart
C         G         Am         F
Always

C       G        Am        F
Don't listen to them, 'cause what do they know?
C         G        Am         F
We need each other, to have, to hold
C          G        Am        F
They'll see in time, I know
C         G        Am        F
When destiny calls you, you must be strong
C        G        Am        F
I may not be with you, but you've got to hold on
C       G        Am         F
They'll see in time, I know
C          G        Am        F
We'll show them together, 'cause you'll be in my heart

C          G         Am         F
You'll be in my heart
C         G         Am         F
Yes, you'll be in my heart
C        G         Am        F
From this day on, now and forever more

C          G         Am         F
You'll be in my heart
C         G         Am         F
No matter what they say
C         G         Am         F
You'll be here in my heart, always
C          G         Am         F
You'll be in my heart
C         G         Am         F
Always
    </pre>

    <footer>
        <p>&copy; 2025 All Rights Reserved. This is a non-commercial educational use of the song "You’ll Be In My Heart" by NIKI. All copyrights to the original work belong to their respective owners.</p>
    </footer>

    <button onclick="downloadFile()">Download HTML</button>

    <script>
        const originalChords = ["C", "C#", "D", "D#", "E", "F", "F#", "G", "G#", "A", "A#", "B"];

        function transpose(step) {
            const lines = document.getElementById("chords").innerText.split("\n");
            const transposedLines = lines.map(line => {
                return line.replace(/\b[A-G][#b]?m?\b/g, chord => {
                    let isMinor = chord.includes("m") && !chord.includes("maj");
                    let base = chord.replace("m", "");
                    let index = originalChords.indexOf(base);
                    if (index === -1) return chord; // chord not found
                    let newIndex = (index + parseInt(step) + 12) % 12;
                    let newChord = originalChords[newIndex];
                    return isMinor ? newChord + "m" : newChord;
                });
            });
            document.getElementById("chords").innerText = transposedLines.join("\n");
        }

        function downloadFile() {
            const content = document.documentElement.outerHTML;
            const blob = new Blob([content], { type: 'text/html' });
            const link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.download = 'Youll_Be_In_My_Heart_NIKI_Chords.html';
            link.click();
        }
    </script>

</body>
</html>
