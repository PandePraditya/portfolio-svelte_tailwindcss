<script>
    import { onMount, onDestroy } from 'svelte';

    // --- PROPS ---
    /** An array of words to cycle through */
    export let words = [];
    /** The delay between each character in milliseconds */
    export let speed = 100;
    /** The delay before typing starts in milliseconds */
    export let startDelay = 0;
    /** Whether to loop through the words infinitely */
    export let loop = true;

    // --- STATE ---
    let typedText = '';
    let wordIndex = 0;
    let charIndex = 0;
    let isDeleting = false;
    let timeoutId;

    // --- LOGIC ---
    function tick() {
        const currentWord = words[wordIndex];

        if (isDeleting) {
            // Deleting logic
            typedText = currentWord.substring(0, charIndex - 1);
            charIndex--;
        } else {
            // Typing logic
            typedText = currentWord.substring(0, charIndex + 1);
            charIndex++;
        }

        // Determine the next action
        let typeSpeed = isDeleting ? speed / 2 : speed; // Deleting is usually faster

        if (!isDeleting && typedText === currentWord) {
            // If word is complete, pause before deleting
            typeSpeed = 2000; // Pause at end of word
            isDeleting = true;
        } else if (isDeleting && typedText === '') {
            // If deletion is complete, move to the next word
            isDeleting = false;
            wordIndex++;
            typeSpeed = 500; // Pause before new word

            if (wordIndex >= words.length) {
                if (loop) {
                    wordIndex = 0; // Loop back to the first word
                } else {
                    return; // Stop if not looping
                }
            }
        }

        timeoutId = setTimeout(tick, typeSpeed);
    }

    // --- LIFECYCLE ---
    onMount(() => {
        if (words.length > 0) {
            timeoutId = setTimeout(tick, startDelay);
        }
    });

    onDestroy(() => {
        clearTimeout(timeoutId);
    });
</script>

<span>
    {typedText}
    <span class="cursor">|</span>
</span>

<style>
    .cursor {
        animation: blink 1s infinite;
        color: inherit;
        font-weight: normal;
    }

    @keyframes blink {
        0% { opacity: 1; }
        50% { opacity: 0; }
        100% { opacity: 1; }
    }
</style>