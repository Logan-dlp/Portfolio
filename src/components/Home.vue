<script>
    import '../assets/Home.css'

    export default {
    name: "ProgressiveText",
    data() {
        return {
            fullText: `Hi, i'm Logan !<br>Tools & Gameplay Programmer.`,
            displayedText: "",
            index: 0,
            isTag: false,
            isTyping: true,
        };
    },
  methods: {
        typeText() {
            if (this.index < this.fullText.length) {
                const char = this.fullText[this.index];
                this.displayedText += char;
                this.index++;

            // Gestion des balises HTML
                if (char === "<") this.isTag = true;
                if (char === ">") this.isTag = false;

                setTimeout(this.typeText, this.isTag ? 0 : 100); // Pas de délai pour les balises
            } else {
                this.isTyping = false;
            }
        },
    },
    mounted() {
        this.typeText();
    },
};
</script>

<template>
    <div>
        <div class="text-container">
            <span v-html="displayedText"></span><span :class="['cursor', { 'blinking': !isTyping }]"></span>
        </div>
    
        <div class="logo-container">
            <div>
                <img src="../../public/U_Cube_1C_Black.png" alt="" class="logo_code">
                <img src="../../public/UE-Icon-2023-Black.png" alt="" class="logo_code">
            </div>

            <div>
                <img src="../../public/Logo_C_sharp.png" alt="" class="logo_code">
                <img src="../../public/cpp_logo.png" alt="" class="logo_code">
            </div>
        </div>
    </div>
</template>