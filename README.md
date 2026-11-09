 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>SNL: The Glucose Economy — Script</title>
<style>
  :root {
    --ink: #202124;
    --muted: #666;
    --paper: #fff;
    --bg: #f2f3f5;
    --accent: #2457c5;
    --highlight: #fff1a8;
    --stage: #eef1f5;
    --border: #d8dce2;
  }
  * { box-sizing: border-box; }
  body {
    margin: 0; background: var(--bg); color: var(--ink);
    font: 16px/1.55 system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  }
  header {
    background: #171923; color: white; padding: 28px 18px 22px;
    text-align: center;
  }
  header h1 { margin: 0 0 5px; font-size: clamp(1.55rem, 4vw, 2.2rem); }
  header p { margin: 0; color: #d4d7e0; }
  .controls {
    position: sticky; top: 0; z-index: 5; background: rgba(255,255,255,.97);
    border-bottom: 1px solid var(--border); padding: 12px 16px;
    display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,.05);
  }
  label { font-weight: 650; }
  select, button {
    font: inherit; border: 1px solid #b9c0cb; border-radius: 9px;
    padding: 9px 12px; background: white; color: var(--ink);
  }
  button { cursor: pointer; }
  button:hover { border-color: var(--accent); }
  main {
    width: min(900px, calc(100% - 28px)); margin: 24px auto 60px;
    background: var(--paper); padding: clamp(18px, 4vw, 42px);
    border-radius: 14px; box-shadow: 0 5px 24px rgba(0,0,0,.07);
  }
  .key { color: var(--muted); font-size: .9rem; margin: 0 0 24px; }
  section { margin: 0 0 34px; }
  h2 { font-size: 1.28rem; margin: 0 0 14px; padding-bottom: 8px; border-bottom: 2px solid var(--border); }
  .line {
    margin: 0 0 11px; padding: 7px 10px; border-radius: 7px;
    transition: background .15s ease, opacity .15s ease;
  }
  .speaker { font-weight: 800; letter-spacing: .02em; }
  .stage {
    color: #505866; background: var(--stage); font-style: italic;
    padding: 8px 12px; margin: 10px 0 14px; border-left: 3px solid #aab3c1;
    border-radius: 0 7px 7px 0;
  }
  .line.dimmed { opacity: .27; }
  .line.selected { background: var(--highlight); outline: 1px solid #e2c95b; }
  .stage.dimmed { opacity: .4; }
  .stage.selected { background: #fff8d7; border-left-color: #d2a900; }
  .all-mode .line, .all-mode .stage { opacity: 1; }
  .footer { color: var(--muted); text-align: center; font-size: .85rem; margin-top: 36px; }
  @media print {
    body { background: white; }
    header { background: white; color: black; padding: 0 0 16px; }
    header p { color: black; }
    .controls { display: none; }
    main { width: 100%; margin: 0; padding: 0; box-shadow: none; }
    .line.dimmed, .stage.dimmed { opacity: 1; }
    .line.selected, .stage.selected { background: transparent; outline: none; }
  }
</style>
</head>
<body>
<header>
  <h1>SNL: The Glucose Economy</h1>
  <p>A five-minute biology skit · No props required</p>
</header>

<div class="controls">
  <label for="partSelect">Highlight part:</label>
  <select id="partSelect" aria-label="Select a character to highlight">
    <option value="all">Full script — everyone</option>
    <option value="NARRATOR">Narrator</option>
    <option value="BLOOD">Blood</option>
    <option value="GLUT">GLUT transporter</option>
    <option value="CELL">Cell</option>
    <option value="LIVER">Liver</option>
    <option value="MUSCLE">Muscle</option>
    <option value="FAT">Fat</option>
    <option value="BANDIT">Muscle Fatigue Bandit</option>
    <option value="DIABETES">Diabetes</option>
    <option value="ALL">All characters (group lines)</option>
  </select>
  <button id="resetBtn" type="button">Show full script</button>
  <button type="button" onclick="window.print()">Print script</button>
</div>

<main id="script" class="all-mode">
  <p class="key">Select a character above to highlight their dialogue. Everyone else's lines will fade, while stage directions remain readable. The script assumes the cast stays in the same room throughout; characters simply turn, react, or change posture rather than entering or exiting.</p>

  <section>
    <h2>Scene 1: The economy is booming (0:00–1:00)</h2>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> Welcome, ladies and gentlemen, to the human body! Today, the glucose economy is BOOMING. Food has just been digested, and glucose is flooding into the bloodstream!</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> (Running in place excitedly) MAKE WAY! COMING THROUGH! Fresh glucose! Fresh glucose! Everybody gets glucose! I've got sugar for everyone!</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> (Excited) OH MY GOD! I've been waiting for this! I'm running low on ATP! GLUT! GLUT! Where are you?!</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> (Casually turns toward Cell) Hey man. What's up? You need some glucose?</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> YES. I'M LITERALLY DYING HERE.</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> Alright, chill. I'm just the transporter. I don't make the rules.</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> Here's your glucose! (Pretends to hand something over)</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> LET'S GOOOO! Time to make ATP!</p>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> And just like that, glucose enters the cell through GLUT transporters, where it can be processed through cellular respiration to produce ATP!</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> WOO MY MITOCHONDRIA. I FEEL THE POOOWWEER</p>
  </section>

  <section>
    <h2>Scene 2: The glucose savings accounts (1:00–2:00)</h2>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> But not all glucose is immediately needed. Some must be stored for later. Enter the liver and muscle!</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> (Slick banker voice; straightens an imaginary tie) Welcome to Liver National Bank. We offer premium glucose savings accounts. Our specialty? Glycogenesis! Turning glucose into glycogen for a rainy day.</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> Hey, you want some glucose?</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> Absolutely. I'll take a deposit. Gotta keep those reserves healthy.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> (Flexing, grunting) BROOOOO! DID SOMEBODY SAY GLUCOSE?!</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> Oh, here we go.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> I'm gonna turn this glucose into GLYCOGEN! Gotta fuel these GAINS! LEG DAY DOESN'T WAIT FOR ANYBODY!</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> Please don't shout in the bank.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> BRO, I AM THE BANK.</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> Actually, you're more like a storage facility.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> THAT'S WHAT A BANK IS, BRO.</p>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> Both the liver and muscle store glucose as glycogen through glycogenesis. The liver helps maintain blood glucose levels between meals, while muscle glycogen is reserved primarily for the muscle's own energy needs.</p>
  </section>

  <section>
    <h2>Scene 3: The precious treasure (2:00–2:40)</h2>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> But there's another player in the glucose economy. Someone who prefers to store energy in a different form...</p>
    <p class="line" data-speaker="FAT"><span class="speaker">FAT:</span> (Crouches, rubbing hands together) MY PRECIOUSSSSS. Give it to me. Give me the glucose.</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> Uh, okay. Here you go?</p>
    <p class="line" data-speaker="FAT"><span class="speaker">FAT:</span> YESSSS. We takes the glucose. We turns it into triglycerides. We stores it FOREVER.</p>
    <p class="stage">[Stage direction: Everyone slowly turns to stare at Fat with a concerned expression.]</p>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> Fat cells can convert excess energy into triglycerides for long-term energy storage.</p>
    <p class="line" data-speaker="FAT"><span class="speaker">FAT:</span> Nobody touches my preciousss.</p>
  </section>

  <section>
    <h2>Scene 4: The grandma scam (2:40–3:40)</h2>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> Unfortunately, not everyone in the glucose economy has good intentions. Introducing... the Muscle Fatigue Bandit.</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> (Turns toward Muscle and sneaks up behind him, speaking in an elderly grandma voice) Hello, sweetheart...</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> (Flexing) BRO?! WHO'S THERE?!</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> It's me... your grandma.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> GRANDMA?! OH MY GOD! WHAT ARE YOU DOING HERE?!</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> I'm in the hospital, sweetheart. The doctors say I don't have much time left...</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> NOOOOO! GRANDMA! PLEASE! TELL ME WHAT I CAN DO!</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> There's only one thing, dear. I need your glycogen.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> MY GLYCOGEN?! BUT THAT'S MY GAINS! THAT'S MY LIFE! I NEED THAT FOR LEG DAY!</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> (Coughs dramatically) Please, sweetheart... I'm dying...</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> NO! NOT GRANDMA! I'LL GIVE YOU EVERYTHING! TAKE IT ALL!</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> Every last bit?</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> EVERY LAST BIT! I LOVE YOU, GRANDMA!</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> (Slowly straightens up, drops grandma voice) Thanks.</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> Wait... Grandma?</p>
    <p class="line" data-speaker="BANDIT"><span class="speaker">BANDIT:</span> (Normal voice) What? You thought I was your grandma?</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> (Realization slowly hits) WAIT... YOU'RE NOT MY GRANDMA?!</p>
    <p class="stage">[Stage direction: The Bandit silently stares at Muscle, then slowly backs away and blends into the group. No one else reacts or speaks to the Bandit.]</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> (Looks down at his imaginary empty glycogen reserves. Voice trembling.) My... my glycogen...</p>
    <p class="stage">(Pause.)</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> MY GAINS...</p>
    <p class="stage">[Stage direction: Muscle slowly drops to his knees, then collapses face-first onto the floor in the most pathetic way possible. He stays there.]</p>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> During exercise, muscle glycogen is broken down through glycogenolysis to fuel muscle activity. As glycogen reserves become depleted, fatigue can occur.</p>
  </section>

  <section>
    <h2>Scene 5: The downfall of the glucose economy (3:40–5:00)</h2>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> But just when things couldn't get worse... a new threat emerges. A politician with a radical new economic plan.</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> (Already in the room, steps forward confidently with presidential campaign energy) HELLO, EVERYBODY! Nobody knows glucose better than me. Nobody. I've got the BEST glucose. Tremendous glucose.</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> Hey, man. Can I help you?</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> First of all, we're putting TARIFFS on all glucose entering cells. Nobody gets free glucose anymore!</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> WHAT?! BUT I'M JUST TRYING TO DELIVER IT!</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> You want to enter the cell? That's gonna cost you. 200% glucose tariff! Maybe 300%! I haven't decided yet!</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> WHAT?! I CAN'T AFFORD THAT! I'M ALREADY STRUGGLING TO MAKE ATP!</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> That's right! We're protecting our domestic glucose! We're bringing all the glucose BACK TO THE BLOODSTREAM! The greatest bloodstream in history!</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> But... that's literally not how this works.</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> (Turns toward GLUT) And YOU. You're the problem. You're letting all this glucose into the cells. You're a terrible transporter. You're fired!</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> Wait, what? I'm literally just doing my job.</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> (Pretends to stab GLUT dramatically) BOOM! TARIFF ENFORCEMENT!</p>
    <p class="stage">[Stage direction: GLUT staggers backward in slow motion, clutching his chest. He looks toward Cell and reaches out a hand.]</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> (Weakly) Cell... I was only trying to get you your glucose...</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> GLUT? No... NO! Don't leave me! I still need you!</p>
    <p class="line" data-speaker="GLUT"><span class="speaker">GLUT:</span> (Fading) Tell... my other transporters... I did my job...</p>
    <p class="stage">[Stage direction: GLUT slowly sinks to the floor, reaching toward Cell until his arm falls limp. Hold a brief, dramatic silence.]</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> (Quietly) ...Goodbye, my friend.</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> WAIT! WHERE'S MY GLUCOSE?! GLUT! GET UP! I NEED ATP!</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> GUYS! WE HAVE A PROBLEM! THERE'S WAY TOO MUCH GLUCOSE IN THE BLOOD!</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> What?! My glucose accounts are overflowing!</p>
    <p class="line" data-speaker="MUSCLE"><span class="speaker">MUSCLE:</span> (Still lying on the floor) BRO... I CAN'T EVEN FEEL MY GAINS...</p>
    <p class="line" data-speaker="FAT"><span class="speaker">FAT:</span> (Excited) MORE GLUCOSE?! MY PRECIOUSSSSS!</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> LOOK AT THIS ECONOMY! THE BEST ECONOMY! BLOOD GLUCOSE THROUGH THE ROOF! RECORD NUMBERS!</p>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> In type 2 diabetes, insulin resistance makes cells less responsive to insulin. This impairs GLUT4-mediated glucose uptake in muscle and fat, contributing to elevated blood glucose levels.</p>
    <p class="line" data-speaker="CELL"><span class="speaker">CELL:</span> I'M STARVING! THERE'S LITERALLY GLUCOSE EVERYWHERE!</p>
    <p class="line" data-speaker="BLOOD"><span class="speaker">BLOOD:</span> I'M CARRYING SO MUCH SUGAR I CAN BARELY MOVE!</p>
    <p class="line" data-speaker="LIVER"><span class="speaker">LIVER:</span> THE MARKET IS CRASHING!</p>
    <p class="line" data-speaker="FAT"><span class="speaker">FAT:</span> (Hugging imaginary glucose) WE'RE RICH! WE'RE RICH!</p>
    <p class="line" data-speaker="DIABETES"><span class="speaker">DIABETES:</span> INSULIN?! NEVER HEARD OF HER!</p>
    <p class="line" data-speaker="NARRATOR"><span class="speaker">NARRATOR:</span> And that, ladies and gentlemen, is how the glucose economy falls apart without proper insulin regulation.</p>
  </section>

  <p class="footer">End of script · Select a role to rehearse your lines, or print the full script.</p>
</main>

<script>
  const select = document.getElementById('partSelect');
  const reset = document.getElementById('resetBtn');
  const script = document.getElementById('script');

  function highlightPart(part) {
    const lines = script.querySelectorAll('[data-speaker]');
    lines.forEach(line => {
      const match = part === 'all' ||
        (part === 'ALL' && line.dataset.speaker === 'ALL') ||
        line.dataset.speaker === part;
      line.classList.toggle('selected', part !== 'all' && match);
      line.classList.toggle('dimmed', part !== 'all' && !match);
    });
    script.querySelectorAll('.stage').forEach(stage => {
      stage.classList.toggle('dimmed', part !== 'all');
      stage.classList.remove('selected');
    });
    script.classList.toggle('all-mode', part === 'all');
  }

  select.addEventListener('change', () => highlightPart(select.value));
  reset.addEventListener('click', () => {
    select.value = 'all';
    highlightPart('all');
  });
  highlightPart('all');
</script>
</body>
</html>
