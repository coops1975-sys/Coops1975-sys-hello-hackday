# Dojo Home – MVP Design Brief

*Hackathon MVP · Owner: Nicola · Status: Draft v0.2 · working demo live on GitHub Pages*

## 1. Summary

A mobile companion guide that helps beginner JKA karateka feel connected to their practice outside the dojo. By learning the kata sequence at home, students free up class time for the sensei to focus on technique, stance, strength and good basic form. It supports the sensei rather than replacing them.

The app is called **Dojo Home**: plain English, so beginners know what it is without knowing the Japanese. A working demo is live at [coops1975-sys.github.io/Coops1975-sys-hello-hackday](https://coops1975-sys.github.io/Coops1975-sys-hello-hackday/).

## 2. Problem

Beginners often treat kata like **a dance with steps** rather than a fight against invisible opponents. A lot of class time goes on remembering the moves, which leaves less time for what makes kata good: intent, technique, stance, balance and power. Students also lack the space to practise physically, and have no structured way to rehearse in spare moments. If karateka can learn the sequence at home, they can spend class time thinking about form.

## 3. Target user

**Primary:** kyu grade beginners preparing for their first three gradings.

- Teenagers and young adults (no children in the club)
- Practise in two modes: **physically** at home (living room, garden) when space allows, and **mentally** on the bus or during breaks
- Mixed motivations: adults tend to want to feel prepared, younger students respond better to streaks and visible progress

**Secondary (future):** the sensei, who sets drills and focus areas. Senior black belts could act as mentors or demonstrators.

## 4. Goals and success measures

| Goal | Measure |
| --- | --- |
| Practice happens outside the dojo | Active users; sessions per week per student; streak retention |
| Class time shifts from sequence to form | Sensei goes over the kata sequence fewer times with beginners |
| Better quality kata | Sensei sees better balance, stance and intent, with kata performed against imagined opponents rather than as steps |
| Connection to practice and community | Students report feeling more connected to their karate between classes |

## 5. Principles

- **Support the sensei, never replace them.** The app reinforces what is taught in the dojo.
- **Aligned to the JKA syllabus.**
- **Works in a living room and on a bus.** Hands-free follow-along for the living room, a quiz for the bus.
- **Mature tone.** Nothing childish. It should suit teenagers and adults.
- **Train against an opponent, not a dance.** Every move says what the imagined attacker is doing, so students practise intent, not steps.
- **Original artwork only.** No JKA logos, club branding or copied images.

## 6. Look and feel

Warm, calm and grown-up, drawn from Japanese ink painting.

| Element | Choice |
| --- | --- |
| Colours | Paper off-white (#f4f0e6), ink black (#1a1a1a), one red accent (#c8102e) |
| Fonts | Yuji Boku for brush lettering (道場), Shippori Mincho for headings, DM Sans for body text. All free Google Fonts |
| Hero | Original brush-style silhouette of a side kick (yoko-geri kekomi) against a red sun |
| Belt progress | Tied-belt icons: solid when achieved, faint and dashed when still to come |

## 7. Syllabus scope

Club syllabus for early gradings: kihon, Heian Shodan through to Heian Sandan (possibly up to Godan), and kihon and gohon kumite.

**Demo scope:** Heian Shodan fully built. Other kata shown as locked or coming soon.

## 8. MVP features (built for the demo)

1. **Home screen.** Brush-style hero, grade picker, tied-belt progress track, practice streak, grading countdown and the kata path (learned, next grading, unlocks later).
2. **Explore the belts.** Tap any belt to preview what it unlocks without changing your real grade, then tap back to your own belt.
3. **Key terms.** Japanese with English meanings, in tabs: punches, blocks, kicks, stances, levels and counting.
4. **Heian Shodan page**
   - Demo video, marked as needing verification, with a YouTube search fallback
   - Follow along through all 21 moves: Japanese count, technique, stance, feet and hips, kiai on moves 9 and 17
   - Steps / opponent toggle, so the headline can be the imagined attacker rather than the technique
   - Floor pattern built into the card: a red dot moves to each move's position, an arrow shows which way you face, and grey dots trail the moves done
   - Practise the whole kata or one of five sections
   - Hands-free mode: calls out the count and the move name in Japanese (e.g. "ichi, gedan-barai"), waits for the voice to finish, then pauses for a slow, steady or brisk gap before the next move. Keeps the screen on
   - Tappable list of all 21 moves that jumps to that move
5. **Test yourself.** Quiz for mental practice: what comes next, and which stance.
6. **Earned practice log.** "I practised today" unlocks only after a full run-through or 5 correct quiz answers, then updates the streak.

## 9. Out of scope for the MVP (roadmap)

- Sensei features: set drills, upload good-practice videos, set focus areas
- Enter a grading result to unlock the next kata (today the student sets their own grade)
- Remaining Heian kata, kihon and kumite content
- Pronunciation audio for key terms, and quizzes on them
- Flexibility exercises and drills
- Light social features, e.g. "5 people in your dojo practised this week"
- Black belt mentoring
- Accounts and syncing between devices

## 10. Technical approach

- Static mobile-first web app (HTML, CSS, JavaScript) hosted on **GitHub Pages**: two pages, index.html and heian-shodan.html, in the Coops1975-sys-hello-hackday repo
- No backend. Grade, grading date, streak and last practice day are saved on the device (localStorage)
- YouTube embeds, with video links held in config so they can be swapped easily
- Placeholder videos: official JKA Heian Shodan (youtube.com/watch?v=O0ndtpxDU8s) and a slow version by Henrik Oesten Sensei (youtube.com/watch?v=Xdx1igUvmlU). Swap in a British JKA video if one is found
- Spoken counts use the phone's built-in Japanese voice (Web Speech API); the screen is kept awake during hands-free mode where the browser allows

## 11. Build status

| Step | Task | Status |
| --- | --- | --- |
| 1 | Brief | Done, this doc |
| 2 | Home screen and belt path | Done, live |
| 3 | Kata page: video, floor pattern, move list | Done, live |
| 4 | Rehearse mode | Done as Test yourself |
| 5 | Countdown, progress and streak | Done; streak now earned |
| 6 | Styling, hands-free, sections, facing arrows | Done |
| 7 | Phone testing and voice check | Before the demo |

## 12. Open questions and research needed

- **Validate the problem:** quick 5-minute chats with 2–3 beginners and the sensei. Is kata sequence really the top pain point?
- **Permissions:** would the sensei and club be comfortable with the app using the syllabus? What are the JKA's expectations about branding and content? Do we have the rights to use the videos?
- **Define "practised":** the demo uses a full run-through or 5 correct quiz answers. Test whether that feels fair to students.
- **Syllabus confirmation:** does the scope for the first three gradings stop at Sandan or go up to Godan?
- **Motivation:** test the streak and progress mechanics with both teenagers and adults.
- **Accuracy:** a sensei should review the move breakdown, opponent lines, floor positions and facing arrows, especially the four diagonal knife-hand moves. The demo video also needs checking.
- **Belt colours:** the grade list is set for this club (white, orange, red, yellow). Confirm with the sensei.
- **Spoken counts:** check the Japanese voice works on the phones students actually use.
