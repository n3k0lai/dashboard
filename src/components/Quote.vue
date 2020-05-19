<template>
  <div class="block quote">
    <div class="block-cont">
      <div class="quote-cont">
        <div v-for="(q, idx) in quote" :key="idx">{{ q }}</div>
      </div>
    </div>
  </div>
</template>
<script>
const xxx = [

  // SAD!
  ["I love when you're aroung", "but I fuckin' hate when you leave"],
  ["I gave her everything", "She took my heart", "and left me lonely", "I won't fix", "I'd rather weep."],
  ["I'm lost then I'm found", "but it's torture bein in love"],
  ["Who am I?", "Someone that's afraid to let go"],

  // Jocelyn Flores
  ["All wanna see me", "with no pot to piss in", "but niggas been excited", "'bout the grave I'm diggin"],

  // Depression & Obsession
  ["I'm poisoned and my body doesn't feel well", "I ate her, inside and out", "I feel my stomach turnin'"],
  ["Make out hill", "where we met", "We let our lips do all the talkin", "and now I'm hooked and depression", "and obsession don't mix well"],
  ["Hollywood motels", "Hell, I think I'm just obsessed with you"],

  // Moonlight
  ["Fuck a Scantron", "here's your lesson"],
  ["Feel like I'm damaged", "girl I know you fucking planned this"],

  // Everybody Dies in their Nightmares
  ["Tired of feelin' like I'm trapped in my damn mind"],
  ["Only time I feel pain", "when I'm feelin' love", "That's why it's tatted on my face", "that I'm damn numb"],
  ["Only time I'm in my mind", "when I'm all alone", "That's why I'm never really alone", "in the night time"],

  // Carry on
  ["I fuckin' hate that I love you still"],

  // Save me
  ["Hello, from the dark side in", "Does anybody here wanna be my friend?"],

  // Infinity (888)
  ["I'm the realest since Kennedy"],

  // $$$
  ["Spin on my dick like a Beyblade"],

  // Alone, Part 3
  ["Gave my love a piece of me", "She put my heart beneath her feet", "She turned and left a question", "\"What's my worth?\""],

  // Angel
  ["Father forgive me", "for you know that I'm sinning"],

  // NUMB
  ["And every single year", "I'm drowning in my tears", "I'm drowning in my tears again"],

  // Floor 555
  ["If you shoot that shit at me, nigga", "I best die 'cause I'm a muh'fuckin' narcissist"],
  ["Fuckboy", "don't test me"],
  ["don’t be gawkin'", "I ain’t doin' no barkin'"]
];
  
export default {
  name: 'quote',
  data() {
    return {
      quote: xxx[Math.floor(Math.random() * xxx.length)] 
    }
  } 
}
</script>
<style lang="scss" scoped>
.quote {
  width: 50%;
  height: 200px;
  .block-cont {
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
.quote-cont {
  font-size: 12px;
  text-align: center;
}
</style>