---
title: Boyer-Moore String Search Visualization
layout: default
---

# 🔍 Boyer-Moore String Search Algorithm

The **Boyer-Moore algorithm** is an efficient way to find a substring within a larger text. Instead of checking every character one by one, it **skips sections** of the text to speed up searching.

## ✨ Try It Out! Enter text & pattern below:
<form>
    <label>Text:</label> 
    <input type="text" id="text" placeholder="Enter text" size="50"><br>
    <label>Pattern:</label> 
    <input type="text" id="pattern" placeholder="Enter pattern"><br>
    <button type="button" onclick="search()">Search</button>
</form>

<p id="output"></p>
<p id="visualization"></p>

---

## 📜 How It Works:
1️⃣ Start by aligning the **pattern** with the text.  
2️⃣ Check from the **end** of the pattern backward.  
3️⃣ Use the **bad character rule** to skip unnecessary comparisons.  
4️⃣ Shift the pattern and repeat until a match is found.  

---

## 📌 Example:
```
Text: "The quick brown fox jumps over the lazy dog."
Pattern: "fox"
```
✅ **Pattern found at index `16`**!

---

✅ **Pattern found at index `16`**!

---

## ⚡ Live JavaScript Code (Runs Below)
<script>
    function search() {
        let text = document.getElementById("text").value;
        let pattern = document.getElementById("pattern").value;
        let output = document.getElementById("output");
        let visualization = document.getElementById("visualization");

        if (!text || !pattern) {
            output.textContent = "⚠️ Please enter both text and pattern.";
            return;
        }

        let index = boyerMoore(text, pattern);
        if (index !== -1) {
            output.innerHTML = `✅ Pattern found at index <b>${index}</b>`;
            visualizeMatch(text, pattern, index);
        } else {
            output.innerHTML = "❌ Pattern not found.";
            visualization.innerHTML = "";
        }
    }

    function visualizeMatch(text, pattern, index) {
        let highlightedText = text.substring(0, index) +
            `<span style="background-color: yellow; font-weight: bold;">${text.substring(index, index + pattern.length)}</span>` +
            text.substring(index + pattern.length);

        document.getElementById("visualization").innerHTML = `Result: ${highlightedText}`;
    }

    function boyerMoore(text, pattern) {
        let m = pattern.length;
        let n = text.length;
        let badChar = badCharacterTable(pattern);

        let s = 0;
        while (s <= (n - m)) {
            let j = m - 1;
            while (j >= 0 && pattern[j] === text[s + j])
                j--;

            if (j < 0) {
                return s;
            } else {
                let shift = Math.max(1, j - (badChar[text[s + j]] || -1));
                s += shift;
            }
        }
        return -1;
    }

    function badCharacterTable(pattern) {
        let badChar = {};
        let m = pattern.length;
        for (let i = 0; i < m; i++) {
            badChar[pattern[i]] = i;
        }
        return badChar;
    }
</script>
