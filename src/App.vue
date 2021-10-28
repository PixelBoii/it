<template>
    <div>
        <transition
            enter-active-class="transition transform"
            enter-from-class="opacity-0 translate-y-2"
            enter-to-class="opacity-100"
            leave-active-class="transition transform"
            leave-from-class="opacity-100"
            leave-to-class="opacity-0 translate-y-2"
        >
            <div class="bg-white rounded-full h-12 w-12 shadow-md flex items-center justify-center fixed right-6 bottom-6 z-20 cursor-pointer" @click="scrollToTop" v-if="scrollY > 500">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-gray-700" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M14.707 12.707a1 1 0 01-1.414 0L10 9.414l-3.293 3.293a1 1 0 01-1.414-1.414l4-4a1 1 0 011.414 0l4 4a1 1 0 010 1.414z" clip-rule="evenodd" />
                </svg>
            </div>
        </transition>

        <div class="min-h-screen w-full relative bg-[#dde8ea]" :style="{ transform: `translateY(${scrollY / 10}px)` }">
            <div class="absolute top-1/4 inset-x-0 mx-auto">
                <img src="/it-logo.png" alt="It" class="w-32 h-auto mx-auto">

                <div class="flex justify-center items-center space-x-4 mt-8">
                    <a href="#chapter-one">
                        <div class="bg-white px-4 py-2 rounded-md">
                            <p class="text-gray-700 text-2xl font-bold"> Chapter 1 </p>
                        </div>
                    </a>

                    <p class="text-gray-700 text-2xl font-bold"> & </p>

                    <a href="#chapter-two">
                        <div class="bg-gray-800 px-4 py-2 rounded-md">
                            <p class="text-gray-100 text-2xl font-bold"> Chapter 2 </p>
                        </div>
                    </a>
                </div>
            </div>

            <img src="/face-outline.png" class="w-3/4 md:w-1/2 h-auto absolute bottom-0 inset-x-0 mx-auto">
        </div>

        <div class="relative characters" id="chapter-one">
            <div class="absolute top-0 left-0 characters-gradient-down w-full h-72"></div>

            <div class="py-10 px-10 relative">
                <div class="container mx-auto max-w-5xl space-y-6">
                    <div class="bg-white px-6 py-2 rounded-md mx-auto w-max">
                        <p class="text-gray-700 text-2xl font-bold"> Chapter 1 </p>
                    </div>

                    <iframe class="mx-auto h-72 w-2/3 rounded-md" src="https://www.youtube-nocookie.com/embed/xKJmEC5ieOk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </div>

                <div class="py-10">
                    <div class="sticky top-0 bg-gray-100 py-3 w-full">
                        <p class="text-gray-900 text-2xl font-semibold text-center"> Characters </p>
                    </div>

                    <div class="mt-6 space-y-12 container mx-auto max-w-5xl">
                        <div class="flex flex-col items-center space-y-6 md:space-y-0 md:space-x-6 text-center md:text-left" :class="[i % 2 == 1 ? 'md:flex-row-reverse' : 'md:flex-row']" v-for="(character, i) in characters" :key="character.name">
                            <img :src="character.img" alt="" class="w-40 h-40 object-cover rounded-full">

                            <div>
                                <p class="text-gray-900 text-2xl font-semibold"> {{ character.name }} </p>

                                <div class="mt-2">
                                    <span class="text-gray-700 font-semibold"> {{ character.description }} </span>

                                    <a :href="character.source.href">
                                        <span class="text-gray-500 font-semibold italic"> // {{ character.source.name }} </span>
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="py-10">
                    <div class="sticky top-0 bg-gray-100 py-3 w-full">
                        <p class="text-gray-900 text-2xl font-semibold text-center"> Story </p>
                    </div>

                    <div class="mt-6 container mx-auto max-w-5xl">
                        <div>
                            <p class="text-gray-700 font-semibold text-center"> In October 1988, twelve-year-old Bill Denbrough crafts a paper sailboat for Georgie, his six-year-old brother. Georgie sails the boat along the rainy streets of small town Derry, Maine, only to have it fall down a storm drain. As he attempts to retrieve it, Georgie sees a clown in the drain, who introduces himself as "Pennywise the Dancing Clown". Pennywise entices Georgie to come closer, then bites his arm off and drags him into the sewer. </p>
                            <img src="/paper-boat.png" alt="" class="w-32 h-auto mx-auto">
                        </div>

                        <div>
                            <div class="bg-white px-8 rounded-md py-3 w-max mx-auto mt-4">
                                <p class="text-gray-700 font-semibold"> Next Summer </p>
                            </div>

                            <p class="text-gray-700 font-semibold mx-auto w-max leading-none mt-1"> ... </p>
                        </div>

                        <div>
                            <p class="text-gray-700 font-semibold text-center mt-6"> The following summer, Bill and his friends Richie Tozier, Eddie Kaspbrak, and Stan Uris run afoul of older bullies Henry Bowers, Belch Huggins, Patrick Hockstetter, and Victor Criss. Bill, still haunted by Georgie's disappearance, calculates that his brother's body may have washed up in a marshy wasteland called the Barrens. He recruits his friends to investigate, believing Georgie may still be alive. Ben Hanscom, one of Bill's new classmates, learns that unexplained tragedies and child disappearances have plagued the town for centuries. Targeted by Bowers' gang, Ben flees into the Barrens and meets Bill's group. They find the sneaker of a missing girl named Betty Ripsom, while Patrick is killed by Pennywise while searching the sewers for Ben. </p>
                            <img src="/sewers.png" alt="" class="w-2/3 max-h-72 object-cover mx-auto rounded-md mt-6">
                            <p class="text-gray-700 font-semibold text-center mt-6"> Beverly Marsh, a girl bullied over her rumored promiscuity, also joins the group; both Bill and Ben develop feelings for her. Later, the group befriends orphan Mike Hanlon after rescuing him from Bowers. Each member of the group has encountered terrifying manifestations of the same menacing clown who attacked Georgie: a headless undead boy (Ben), a sink that spews blood only children can see (Beverly), a diseased and rotting leper (Eddie), a disturbing painting coming alive (Stan), Mike's parents burning alive (Mike), and a frightening phantom of Georgie (Bill). Now calling themselves "The Losers Club", they realize they are all being stalked by the same entity, which they refer to as "It". They determine that It appears as their individual worst fears, awakening every 27 years to feed on the children of Derry before resuming hibernation, and moves about by using the sewer lines, which all lead to an old stone well hidden under an abandoned house on Neibolt Street. </p>
                            <img src="/team.png" alt="" class="w-2/3 h-auto mx-auto rounded-md mt-6">
                            <p class="text-gray-700 font-semibold text-center mt-6"> After Pennywise attacks them, the group ventures to the house to confront It, only to be separated and terrorized. As Pennywise gloats to Bill about Georgie, the Losers regroup and Beverly impales Pennywise through the head, forcing the clown to retreat. The group flees the house and begins to splinter, with only Bill and Beverly resolute in fighting It. </p>
                        </div>

                        <div class="mt-12">
                            <div class="bg-white px-8 rounded-md py-3 w-max mx-auto mt-6">
                                <p class="text-gray-700 font-semibold"> Weeks Later </p>
                            </div>

                            <p class="text-gray-700 font-semibold mx-auto w-max leading-none mt-1"> ... </p>
                        </div>

                        <div>
                            <p class="text-gray-700 font-semibold mt-6 text-center"> Weeks later, after Beverly confronts and incapacitates her sexually abusive father, Pennywise abducts her. The Losers Club reassembles and returns to the abandoned house to rescue her. Bowers, who has murdered his abusive father after being driven insane by It, attacks the group; Mike fights back and pushes Bowers down the well, apparently killing him. The Losers descend into the sewers and find It's underground lair, which contains a mountain of decayed circus props and children's belongings, around which the bodies of It's child victims float in mid-air. Beverly, now catatonic after being exposed to bright lights inside It's gaping mouth, is restored to consciousness when Ben kisses her. </p>
                            <p class="text-gray-700 font-semibold mt-6 text-center"> Bill encounters Georgie, but recognizes that he is It in disguise. As Pennywise, It takes Bill hostage, offering to spare the others and go into hibernation if they let It feed on Bill. The Losers reject this, battling with It while overcoming their various fears. It is eventually defeated and retreats deeper into the sewers, with Bill declaring that It will starve during its hibernation. After finding the remnants of Georgie's raincoat, Bill finally comes to terms with his brother's death, with his friends comforting him. </p>
                        </div>

                        <div class="mt-12">
                            <div class="bg-white px-8 rounded-md py-3 w-max mx-auto mt-6">
                                <p class="text-gray-700 font-semibold"> End of Summer </p>
                            </div>

                            <p class="text-gray-700 font-semibold mx-auto w-max leading-none mt-1"> ... </p>
                        </div>

                        <div>
                            <p class="text-gray-700 font-semibold mt-6 text-center"> As summer ends, Beverly informs the group of a vision she had while catatonic, where she saw them fighting It again as adults. The Losers swear a blood oath that they will return to Derry as adults if It returns. After the others make their goodbyes and disperse, Beverly and Bill discuss her leaving the next day to live with her aunt in Portland. Before she leaves, Bill reveals his feelings and they kiss. </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="bg-gray-800 py-10" id="chapter-two">
            <div class="bg-gray-700 px-6 py-2 rounded-md mx-auto w-max">
                <p class="text-gray-100 text-2xl font-bold"> Chapter 2 </p>
            </div>

            <div class="py-6 space-y-6 relative">
                <div class="container mx-auto max-w-5xl">
                    <iframe class="mx-auto h-72 w-2/3 rounded-md" src="https://www.youtube-nocookie.com/embed/xhJ5P7Up3jA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

                    <div class="text-center mt-4 px-6">
                        <p class="text-gray-300 text-lg font-medium"> <strong> Twenty-seven </strong> years after their first encounter with the terrifying Pennywise, the Losers Club have grown up and moved away, until a devastating phone call brings them back. </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            scrollY: 0,
            characters: [
                {
                    name: 'Pennywise (It)',
                    img: '/pennywise.png',
                    description: 'It is the title character and the main antagonist in Stephen King\'s 1986 horror novel It. The character is an ancient cosmic evil which preys upon the children of Derry, Maine, roughly every 27 years, using a variety of powers that include the ability to shapeshift, manipulate reality, and go unnoticed by adults. During the course of the story, It primarily appears in the form of Pennywise the Dancing Clown. "The Losers Club" first realizes Pennywise\'s presence because of Bill\'s little brother Georgie. ',
                    source: {
                        name: 'Wikipedia',
                        href: 'https://en.wikipedia.org/wiki/Pennywise_(It)'
                    }
                },
                {
                    name: 'William "Bill" Denbrough',
                    img: '/bill-denbrough.png',
                    description: 'The red-headed leader of the group, and the most self-assured member of the club. He wants to avenge the death of his younger brother, George. He feels partly responsible for his death as it was he who made George the boat and sent him outside to play with it during a rainstorm. In addition, his parents have become cold and withdrawn towards him after the loss of their youngest son, and he secretly hopes the death of the murderer will awaken his parents to his presence again. He has a bad stuttering issue, which his mother attributes to a car accident that occurred when he was three years old, and which earned him the nickname "Stuttering Bill".',
                    source: {
                        name: 'Tvtropes',
                        href: 'https://tvtropes.org/pmwiki/pmwiki.php/Characters/IT'
                    }
                },
                {
                    name: 'Benjamin "Ben" Hanscom',
                    img: '/ben-hanscom.png',
                    description: 'A highly intelligent boy who, before joining the Losers\' Club, often spent his free time reading books at the public library. He is also obese, and due to this has become a favorite victim of Henry Bowers.',
                    source: {
                        name: 'Tvtropes',
                        href: 'https://tvtropes.org/pmwiki/pmwiki.php/Characters/IT'
                    }
                },
                {
                    name: 'Edward "Eddie" Kaspbrak',
                    img: '/edward-kaspbrak.png',
                    description: 'A frail and asthmatic hypochondriac, who carries his inhaler with him everywhere. His father died when he was very young, and his mother is domineering and constantly worries about his health.',
                    source: {
                        name: 'Tvtropes',
                        href: 'https://tvtropes.org/pmwiki/pmwiki.php/Characters/IT'
                    }
                },
                {
                    name: 'Richard "Richie" Tozier',
                    img: '/richie-tozier.png',
                    description: 'Known as "Trashmouth", Richie is the Losers\' most lighthearted member, always cracking jokes and doing impersonations or "Voices", which prove very powerful weapons against It. He is "too intelligent for his own good" and channels his boredom in hyper-active wisecracking, to the point of getting into trouble. His flippant remark to Henry Bowers leads to almost getting beaten up by Henry and his friends. He is the most devoted to keeping the group together as he sees seven as a magical number and believes the group should have no more, no less. In adulthood, he is a successful disc jockey in Los Angeles.',
                    source: {
                        name: 'Tvtropes',
                        href: 'https://tvtropes.org/pmwiki/pmwiki.php/Characters/IT'
                    }
                },
                {
                    name: 'Michael "Mike" Hanlon',
                    img: '/mike-hanlon.png',
                    description: 'The last to join the Losers. He is the only African-American in the group and lives with his parents on a large farm. He goes to a different school from the other kids due to his Baptist faith. Mike is racially persecuted by Henry Bowers, whose father holds a long-standing grudge against Mike\'s father. Mike meets The Losers when they help him fight back against Bowers in a massive rock fight. His father kept an album filled with photos that were important to Derry\'s history, including several of Pennywise the Dancing Clown. He is the only one of the Losers to stay behind in Derry (and thus the only one to retain his memory of the events of 1958) and becomes the town librarian.',
                    source: {
                        name: 'Tvtropes',
                        href: 'https://tvtropes.org/pmwiki/pmwiki.php/Characters/IT'
                    }
                }
            ]
        }
    },
    methods: {
        handleScroll() {
            this.scrollY = window.scrollY;
        },
        scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }
    },
    mounted() {
        this.handleScroll();

        document.addEventListener('scroll', this.handleScroll);
    }
}
</script>

<style>
.characters {
    background-color: #f3f4f5;
}

.characters-gradient-down {
    background-image: linear-gradient(to bottom, #dde8ea, transparent);
}
</style>
