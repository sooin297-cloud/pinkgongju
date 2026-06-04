# pinkgongju
기타공주
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎀 Pink Princess Guitar Chords & Atelier 🎀</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for Cute Aesthetic -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Gaegu:wght@400;700&family=Gowun+Dodum&family=Cherry+Bomb+One&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Gowun Dodum', sans-serif;
            background: linear-gradient(135deg, #ffeef8 0%, #ffd3eb 50%, #fbc2eb 100%);
        }
        .cute-font {
            font-family: 'Gaegu', cursive;
        }
        .princess-title {
            font-family: 'Cherry Bomb One', cursive;
            color: #ff6ebb;
            text-shadow: 3px 3px 0px #fff, -1px -1px 0px #fff, 1px -1px 0px #fff, -1px 1px 0px #fff, 3px 3px 10px rgba(255, 105, 180, 0.4);
        }
        /* Heart Sparkle Animation */
        @keyframes sparkle {
            0%, 100% { transform: scale(1) rotate(0deg); opacity: 0.8; }
            50% { transform: scale(1.2) rotate(15deg); opacity: 1; filter: drop-shadow(0 0 8px rgba(255,105,180,0.8)); }
        }
        .sparkle-icon {
            animation: sparkle 2s infinite ease-in-out;
        }
        /* Pulse scale */
        @keyframes custom-pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.08); }
        }
        .pulse-card {
            animation: custom-pulse 3s infinite ease-in-out;
        }
        /* Customized Scrollbar for princess */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #ffeef8;
        }
        ::-webkit-scrollbar-thumb {
            background: #ffb7dd;
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #ff8ebb;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between items-center p-3 md:p-6 overflow-x-hidden">

    <!-- Deco Sparkles -->
    <div class="absolute top-6 left-6 text-pink-400 opacity-60 text-3xl sparkle-icon hidden md:block">✨</div>
    <div class="absolute top-20 right-12 text-pink-400 opacity-60 text-4xl sparkle-icon hidden md:block" style="animation-delay: 0.5s;">🎀</div>
    <div class="absolute bottom-20 left-12 text-pink-400 opacity-60 text-4xl sparkle-icon hidden md:block" style="animation-delay: 1s;">💖</div>
    <div class="absolute bottom-6 right-8 text-pink-400 opacity-60 text-3xl sparkle-icon hidden md:block" style="animation-delay: 1.5s;">✨</div>

    <!-- Main Container -->
    <div class="w-full max-w-5xl bg-white/75 backdrop-blur-md rounded-[32px] border-4 border-pink-200 p-4 md:p-8 shadow-[0_20px_50px_rgba(255,182,193,0.4)] flex flex-col items-center relative z-10 my-auto">
        
        <!-- Top Ribbon Header -->
        <div class="flex flex-col items-center text-center mb-4">
            <span class="text-pink-500 text-5xl mb-1">🎀</span>
            <h1 class="princess-title text-4xl md:text-5xl tracking-wider">Princess Guitar Studio</h1>
            <p class="text-rose-500 font-bold cute-font text-lg md:text-2xl mt-1">리본과 보석으로 나만의 마법 음악을 연주해요! 💖</p>
        </div>

        <!-- Mode Select Tabs -->
        <div class="flex bg-pink-100/60 p-1.5 rounded-2xl mb-4 gap-2 border border-pink-200/50 w-full max-w-md shadow-inner">
            <button id="tab-library" onclick="switchMode('library')" class="flex-1 py-2 text-sm font-extrabold rounded-xl transition-all duration-300 bg-white text-pink-600 shadow-sm">
                📚 핑크 코드 마법책
            </button>
            <button id="tab-creator" onclick="switchMode('creator')" class="flex-1 py-2 text-sm font-extrabold rounded-xl transition-all duration-300 text-pink-500 hover:text-pink-600">
                🪄 나만의 코드 메이커
            </button>
        </div>

        <!-- Layout Wrapper -->
        <div class="w-full grid grid-cols-1 md:grid-cols-12 gap-5 items-stretch">
            
            <!-- Left Side: Chord Category & List OR Custom Maker Panel (7 cols) -->
            <div class="md:col-span-7 flex flex-col bg-pink-50/60 rounded-3xl p-4 md:p-5 border-2 border-pink-100">
                
                <!-- View 1: Chord Library Mode -->
                <div id="panel-library" class="flex flex-col h-full">
                    <div class="flex items-center justify-between mb-3 pb-2 border-b-2 border-pink-200">
                        <span class="text-rose-600 font-extrabold text-lg flex items-center gap-2">
                            <i class="fa-solid fa-heart text-pink-500"></i> 코드 마법 보석상자
                        </span>
                        <span class="text-pink-400 text-xs cute-font font-bold">코드를 터치하면 신비로운 소리가 나요!</span>
                    </div>
                    
                    <!-- Category Buttons -->
                    <div class="flex gap-2 mb-3 justify-center">
                        <button onclick="filterCategory('all')" id="btn-all" class="category-btn px-3 py-1.5 bg-pink-400 text-white rounded-full text-xs font-bold shadow-sm hover:bg-pink-500 transition-all scale-105">전체보기 ✨</button>
                        <button onclick="filterCategory('major')" id="btn-major" class="category-btn px-3 py-1.5 bg-white text-pink-500 border border-pink-200 rounded-full text-xs font-bold shadow-sm hover:bg-pink-100 transition-all">메이저 🎀</button>
                        <button onclick="filterCategory('minor')" id="btn-minor" class="category-btn px-3 py-1.5 bg-white text-pink-500 border border-pink-200 rounded-full text-xs font-bold shadow-sm hover:bg-pink-100 transition-all">마이너 🧸</button>
                    </div>

                    <!-- Chord Grid -->
                    <div id="chord-grid" class="grid grid-cols-3 sm:grid-cols-4 gap-2 max-h-[280px] overflow-y-auto pr-1">
                        <!-- Cards dynamically injected -->
                    </div>
                </div>

                <!-- View 2: Creator Panel Mode -->
                <div id="panel-creator" class="hidden flex flex-col h-full">
                    <div class="flex items-center justify-between mb-3 pb-2 border-b-2 border-pink-200">
                        <span class="text-rose-600 font-extrabold text-lg flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic-sparkles text-pink-500"></i> 나만의 코드 연구실
                        </span>
                        <span class="text-pink-400 text-xs cute-font font-bold">오른쪽 지판을 탭해 보석을 얹어보세요!</span>
                    </div>

                    <p class="text-xs text-pink-500/90 leading-relaxed mb-4 bg-white/60 p-3 rounded-2xl border border-pink-100">
                        💡 <b>사용법:</b> 오른쪽 지판의 가로줄(프렛)과 세로줄(기타현)이 만나는 곳을 직접 클릭해보세요. 
                        마법 보석이 박히면서 손가락 번호가 부여되고 즉각 음색을 확인할 수 있습니다. 맨 위의 <b class="text-rose-500">O/X</b> 영역을 누르면 소리가 나지 않는 뮤트 설정도 가능합니다!
                    </p>

                    <!-- Save Form -->
                    <div class="bg-white/80 p-4 rounded-2xl border border-pink-200 shadow-sm mt-auto space-y-3">
                        <h4 class="font-bold text-pink-600 text-sm flex items-center gap-1.5">
                            <i class="fa-solid fa-cloud-arrow-down text-pink-400"></i> 이 코드를 마법책에 저장하기
                        </h4>
                        <div class="flex flex-col sm:flex-row gap-2">
                            <input type="text" id="custom-chord-name" maxlength="6" placeholder="예: MyC7, 핑키" class="flex-1 px-3 py-2 border-2 border-pink-200 rounded-xl text-sm focus:outline-none focus:border-pink-400 font-extrabold text-pink-700 placeholder-pink-300">
                            <button onclick="saveCustomChord()" class="px-5 py-2 bg-gradient-to-r from-pink-400 to-rose-400 hover:from-pink-500 hover:to-rose-500 text-white text-sm font-extrabold rounded-xl shadow-sm transition-all active:scale-95">
                                💖 저장하기
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Sound Preset & Rhythm Engine Box (Always Visible Below List) -->
                <div class="mt-4 bg-white/70 rounded-2xl p-4 border border-pink-100 space-y-3">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                        <!-- Sound preset selector -->
                        <div>
                            <label class="block text-xs font-bold text-pink-600 mb-1 flex items-center gap-1">
                                🎵 소리 요정 프리셋 선택
                            </label>
                            <select id="select-synth" onchange="changeSynthType()" class="w-full text-xs font-bold bg-pink-50 text-pink-600 border border-pink-200 px-3 py-2 rounded-xl focus:outline-none">
                                <option value="guitar">🎸 요정의 기타 (Classic Guitar)</option>
                                <option value="musicbox">✨ 핑크 오르골 (Music Box)</option>
                                <option value="harp">🌌 은하수 하프 (Cosmic Harp)</option>
                            </select>
                        </div>

                        <!-- Strum Rhythm selector -->
                        <div>
                            <label class="block text-xs font-bold text-pink-600 mb-1 flex items-center gap-1">
                                🥁 마법 스트럼 리듬 패턴
                            </label>
                            <div class="flex gap-1">
                                <select id="select-rhythm" onchange="stopAutoRhythm()" class="flex-1 text-xs font-bold bg-pink-50 text-pink-600 border border-pink-200 px-3 py-2 rounded-xl focus:outline-none">
                                    <option value="single">🎀 싱글 스트럼 (기본)</option>
                                    <option value="waltz">🎈 Lovely 왈츠 (3/4 박자)</option>
                                    <option value="shuffle">🍭 Shiny 셔플 (4/4 박자)</option>
                                </select>
                                <button id="btn-rhythm-play" onclick="toggleAutoRhythm()" class="px-3 bg-pink-400 hover:bg-pink-500 text-white rounded-xl text-xs font-bold shadow-sm transition-all">
                                    <i id="rhythm-play-icon" class="fa-solid fa-play"></i>
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- BPM controls -->
                    <div id="bpm-container" class="hidden flex items-center gap-3 bg-pink-100/40 p-2 rounded-xl border border-pink-100/50">
                        <span class="text-xs font-bold text-pink-500 shrink-0">마법 속도 (BPM): <span id="bpm-val" class="text-pink-600 font-extrabold">110</span></span>
                        <input type="range" id="input-bpm" min="60" max="180" value="110" oninput="changeBpm(this.value)" class="w-full accent-pink-400 h-1.5 bg-pink-200 rounded-lg appearance-none cursor-pointer">
                    </div>
                </div>

            </div>

            <!-- Right Side: Interactive Display (5 cols) -->
            <div class="md:col-span-5 flex flex-col items-center justify-between bg-white/90 rounded-3xl p-5 border-4 border-dashed border-pink-200 shadow-inner relative overflow-hidden">
                <!-- Sparkle background overlay -->
                <div class="absolute inset-0 bg-[radial-gradient(#ffd5ec_1px,transparent_1px)] [background-size:16px_16px] opacity-40 pointer-events-none"></div>

                <!-- Active Chord Title -->
                <div class="text-center relative z-10 w-full">
                    <div class="flex justify-center items-center gap-1 text-pink-400 mb-0.5">
                        <i class="fa-solid fa-star text-[10px]"></i>
                        <i class="fa-solid fa-star text-xs"></i>
                        <i class="fa-solid fa-star text-[10px]"></i>
                    </div>
                    <div id="active-chord-name" class="text-5xl font-extrabold text-pink-600 tracking-wide cute-font">C</div>
                    <div id="active-chord-type" class="text-xs font-bold text-rose-400 mt-0.5 bg-pink-100/70 px-3 py-0.5 rounded-full inline-block">C Major Triad</div>
                </div>

                <!-- SVG Chord Diagram (The Fretboard) -->
                <div class="my-3 relative z-10 flex items-center justify-center w-full" style="height: 220px;">
                    <svg id="fretboard" viewBox="0 0 160 200" class="w-full h-full max-w-[170px] drop-shadow-md cursor-pointer">
                        <!-- Left border / Nut -->
                        <line x1="20" y1="30" x2="140" y2="30" stroke="#f472b6" stroke-width="6" stroke-linecap="round"/>
                        
                        <!-- Frets (5 frets shown) -->
                        <line x1="20" y1="64" x2="140" y2="64" stroke="#fbcfe8" stroke-width="2"/>
                        <line x1="20" y1="98" x2="140" y2="98" stroke="#fbcfe8" stroke-width="2"/>
                        <line x1="20" y1="132" x2="140" y2="132" stroke="#fbcfe8" stroke-width="2"/>
                        <line x1="20" y1="166" x2="140" y2="166" stroke="#fbcfe8" stroke-width="2"/>
                        <line x1="20" y1="200" x2="140" y2="200" stroke="#fbcfe8" stroke-width="2"/>

                        <!-- Strings (6 strings) -->
                        <line x1="20" y1="30" x2="20" y2="200" stroke="#f472b6" stroke-width="1.5"/>
                        <line x1="44" y1="30" x2="44" y2="200" stroke="#f472b6" stroke-width="1.5"/>
                        <line x1="68" y1="30" x2="68" y2="200" stroke="#f472b6" stroke-width="1.5"/>
                        <line x1="92" y1="30" x2="92" y2="200" stroke="#f472b6" stroke-width="1.5"/>
                        <line x1="116" y1="30" x2="116" y2="200" stroke="#f472b6" stroke-width="1.5"/>
                        <line x1="140" y1="30" x2="140" y2="200" stroke="#f472b6" stroke-width="1.5"/>

                        <!-- Placeholders for chord markings (JS) -->
                        <g id="chord-markers"></g>
                        <g id="open-mute-markers"></g>
                    </svg>
                </div>

                <!-- Princess Finger Map (Visual Finger Guide) -->
                <div class="w-full grid grid-cols-4 gap-1 bg-pink-50/60 p-2 rounded-2xl border border-pink-100/80 mb-3 relative z-10">
                    <!-- Finger 1 (Index) -->
                    <div id="finger-1" class="flex flex-col items-center transition-all duration-300">
                        <span class="text-lg">☝️</span>
                        <span class="text-[9px] font-bold text-pink-600 mt-0.5">1 검지</span>
                        <span id="finger-1-detail" class="text-[8px] text-pink-300 font-bold bg-white px-1.5 py-0.5 rounded-full border border-pink-100 mt-1 transition-all">💤</span>
                    </div>
                    <!-- Finger 2 (Middle) -->
                    <div id="finger-2" class="flex flex-col items-center transition-all duration-300">
                        <span class="text-lg">👆</span>
                        <span class="text-[9px] font-bold text-pink-600 mt-0.5">2 중지</span>
                        <span id="finger-2-detail" class="text-[8px] text-pink-300 font-bold bg-white px-1.5 py-0.5 rounded-full border border-pink-100 mt-1 transition-all">💤</span>
                    </div>
                    <!-- Finger 3 (Ring) -->
                    <div id="finger-3" class="flex flex-col items-center transition-all duration-300">
                        <span class="text-lg">💍</span>
                        <span class="text-[9px] font-bold text-pink-600 mt-0.5">3 약지</span>
                        <span id="finger-3-detail" class="text-[8px] text-pink-300 font-bold bg-white px-1.5 py-0.5 rounded-full border border-pink-100 mt-1 transition-all">💤</span>
                    </div>
                    <!-- Finger 4 (Little) -->
                    <div id="finger-4" class="flex flex-col items-center transition-all duration-300">
                        <span class="text-lg">🤙</span>
                        <span class="text-[9px] font-bold text-pink-600 mt-0.5">4 새끼</span>
                        <span id="finger-4-detail" class="text-[8px] text-pink-300 font-bold bg-white px-1.5 py-0.5 rounded-full border border-pink-100 mt-1 transition-all">💤</span>
                    </div>
                </div>

                <!-- Interactive Play Button -->
                <div class="w-full flex flex-col items-center gap-1.5 relative z-10">
                    <button id="btn-main-strum" onclick="playActiveChord()" class="w-full py-2.5 bg-gradient-to-r from-pink-400 to-rose-400 text-white font-extrabold rounded-full shadow-[0_4px_12px_rgba(244,114,182,0.3)] hover:shadow-[0_6px_18px_rgba(244,114,182,0.5)] hover:from-pink-500 hover:to-rose-500 active:scale-95 transition-all flex items-center justify-center gap-1.5 text-base">
                        <span class="animate-bounce">🪄</span> 요정의 핑크 스트럼 연주하기
                    </button>
                    <p id="fingering-text" class="text-[11px] font-bold text-pink-500 mt-0.5 text-center bg-pink-50 px-2.5 py-1 rounded-lg border border-pink-100 w-full min-h-[32px] flex items-center justify-center">
                        로딩 중...
                    </p>
                </div>

            </div>
        </div>

        <!-- Easy Guide / Tips for Princesses -->
        <div class="w-full mt-4 bg-rose-50/50 rounded-2xl p-4 border border-pink-100 flex items-start gap-3">
            <span class="text-2xl text-rose-400">👑</span>
            <div class="text-left">
                <h4 class="font-bold text-rose-600 text-sm mb-1">마법 아틀리에 이용 팁</h4>
                <ul class="text-xs text-rose-500/90 list-disc list-inside space-y-1">
                    <li><b>나만의 코드 메이커</b> 모드에서 마법 지판을 터치해 예쁜 보석을 올려 새로운 코드를 합성할 수 있어요.</li>
                    <li>지판 가장 위쪽 여백을 탭하면 줄 개방 상태를 순서대로 변경할 수 있습니다 (소리남 <span class="text-rose-600 font-bold">O</span> &rarr; 소리안남 <span class="text-rose-600 font-bold">X</span> &rarr; 비어있음).</li>
                    <li><b>소리 요정 선택</b>과 <b>리듬 자동 재생(Play 버튼)</b>을 켜서 흥겨운 공주님의 밴드 세션을 꾸려보세요!</li>
                </ul>
            </div>
        </div>

    </div>

    <!-- Footer -->
    <div class="mt-4 text-center text-rose-400/80 text-xs font-bold z-10">
        <p>🎀 Designed with Pure Pink Magic & Sparkles 🎀</p>
        <p class="mt-0.5">&copy; Princess Chord World Corp.</p>
    </div>

    <!-- Script for Chord Magic -->
    <script>
        // Core Chord Database (Beginners + Extendable)
        const DEFAULT_CHORDS = [
            { id: "C", name: "C", fullName: "C Major", category: "major", markers: [ { s: 5, f: 3, num: 3 }, { s: 4, f: 2, num: 2 }, { s: 2, f: 1, num: 1 } ], openMute: ['x', 'o', '', '', '', 'o'], text: "3번 손가락으로 5번줄, 2번으로 4번줄, 1번으로 2번줄을 짚으세요!" },
            { id: "A", name: "A", fullName: "A Major", category: "major", markers: [ { s: 4, f: 2, num: 1 }, { s: 3, f: 2, num: 2 }, { s: 2, f: 2, num: 3 } ], openMute: ['x', 'o', '', '', '', 'o'], text: "2번 프렛의 4번, 3번, 2번줄을 조르르 예쁘게 짚어주세요." },
            { id: "G", name: "G", fullName: "G Major", category: "major", markers: [ { s: 6, f: 3, num: 3 }, { s: 5, f: 2, num: 2 }, { s: 1, f: 3, num: 4 } ], openMute: ['', '', 'o', 'o', 'o', ''], text: "손을 활짝 펴서 6번줄 3번, 5번줄 2번, 1번줄 3번을 짚어요!" },
            { id: "E", name: "E", fullName: "E Major", category: "major", markers: [ { s: 5, f: 2, num: 2 }, { s: 4, f: 2, num: 3 }, { s: 3, f: 1, num: 1 } ], openMute: ['o', '', '', '', 'o', 'o'], text: "중지/약지로 5, 4번줄 2프렛을, 검지로 3번줄 1프렛을 꼭!" },
            { id: "D", name: "D", fullName: "D Major", category: "major", markers: [ { s: 3, f: 2, num: 1 }, { s: 2, f: 3, num: 3 }, { s: 1, f: 2, num: 2 } ], openMute: ['x', 'x', 'o', '', '', ''], text: "예쁜 세모 모양으로 3번줄 2, 2번줄 3, 1번줄 2프렛을 짚어요." },
            { id: "Am", name: "Am", fullName: "A Minor", category: "minor", markers: [ { s: 4, f: 2, num: 2 }, { s: 3, f: 2, num: 3 }, { s: 2, f: 1, num: 1 } ], openMute: ['x', 'o', '', '', '', 'o'], text: "살짝 아련한 마이너 소리! 4번줄 2, 3번줄 2, 2번줄 1프렛이에요." },
            { id: "Em", name: "Em", fullName: "E Minor", category: "minor", markers: [ { s: 5, f: 2, num: 2 }, { s: 4, f: 2, num: 3 } ], openMute: ['o', '', '', 'o', 'o', 'o'], text: "두 손가락만 있으면 끝! 5번줄과 4번줄의 2프렛만 짚어보세요." },
            { id: "Dm", name: "Dm", fullName: "D Minor", category: "minor", markers: [ { s: 3, f: 2, num: 2 }, { s: 2, f: 3, num: 3 }, { s: 1, f: 1, num: 1 } ], openMute: ['x', 'x', 'o', '', '', ''], text: "비 내리는 오후처럼 촉촉한 소리. 3번줄 2, 2번줄 3, 1번줄 1프렛!" },
            { id: "F", name: "F", fullName: "F Major (Easy)", category: "major", markers: [ { s: 4, f: 3, num: 3 }, { s: 3, f: 2, num: 2 }, { s: 2, f: 1, num: 1 }, { s: 1, f: 1, num: 1 } ], openMute: ['x', 'x', '', '', '', ''], text: "쉬운 미니 F코드! 4번줄 3, 3번줄 2, 그리고 검지로 1, 2번줄을 동시에!" },
            { id: "Bm", name: "Bm", fullName: "B Minor (Easy)", category: "minor", markers: [ { s: 4, f: 4, num: 3 }, { s: 3, f: 4, num: 4 }, { s: 2, f: 3, num: 2 }, { s: 1, f: 2, num: 1 } ], openMute: ['x', 'x', '', '', '', ''], text: "하이코드가 버겁다면 미니 Bm으로! 4번 프렛부터 계단식으로 예쁘게." },
            { id: "C7", name: "C7", fullName: "C Dominant 7th", category: "major", markers: [ { s: 5, f: 3, num: 3 }, { s: 4, f: 2, num: 2 }, { s: 3, f: 3, num: 4 }, { s: 2, f: 1, num: 1 } ], openMute: ['x', '', '', '', '', 'o'], text: "C코드에 새끼손가락(3번줄 3프렛)만 보태면 한층 신비스러운 7화음 완성!" },
            { id: "A7", name: "A7", fullName: "A Dominant 7th", category: "major", markers: [ { s: 4, f: 2, num: 2 }, { s: 2, f: 2, num: 3 } ], openMute: ['x', 'o', '', 'o', '', 'o'], text: "가운데 손가락 두 개만 벌려 짚으면 되는 기분 좋은 징검다리 코드!" }
        ];

        let CHORDS = [...DEFAULT_CHORDS];

        const FINGER_EMOJIS = {
            1: "☝️",
            2: "👆",
            3: "💍",
            4: "🤙"
        };

        // App State
        let currentMode = 'library'; // 'library' | 'creator'
        let currentActiveChordId = 'C';
        let synthType = 'guitar'; // 'guitar' | 'musicbox' | 'harp'
        let currentBpm = 110;
        let isRhythmPlaying = false;
        let rhythmTimer = null;
        let audioCtx = null;

        // Custom Chord Temporary Creation State
        let customMarkers = [];
        let customOpenMute = ['', '', '', '', '', ''];

        // Standard Guitar String Base Frequencies
        const STRING_FREQS = [82.41, 110.00, 146.83, 196.00, 246.94, 329.63]; 

        window.addEventListener('DOMContentLoaded', () => {
            renderChords(CHORDS);
            selectChord('C');
            setupFretboardInteractions();
        });

        // Mode Switch Panel Toggle
        function switchMode(mode) {
            currentMode = mode;
            const tabLib = document.getElementById('tab-library');
            const tabCreate = document.getElementById('tab-creator');
            const pnlLib = document.getElementById('panel-library');
            const pnlCreate = document.getElementById('panel-creator');

            if (mode === 'library') {
                tabLib.className = "flex-1 py-2 text-sm font-extrabold rounded-xl transition-all duration-300 bg-white text-pink-600 shadow-sm";
                tabCreate.className = "flex-1 py-2 text-sm font-extrabold rounded-xl transition-all duration-300 text-pink-500 hover:text-pink-600";
                pnlLib.classList.remove('hidden');
                pnlCreate.classList.add('hidden');
                selectChord('C');
            } else {
                tabCreate.className = "flex-1 py-2 text-sm font-extrabold rounded-xl transition-all duration-300 bg-white text-pink-600 shadow-sm";
                tabLib.className = "flex-1 py-2 text-sm font-extrabold rounded-xl transition-all duration-300 text-pink-500 hover:text-pink-600";
                pnlCreate.classList.remove('hidden');
                pnlLib.classList.add('hidden');
                
                // Set Up Default Blank Custom Canvas
                customMarkers = [];
                customOpenMute = ['o', 'o', 'o', 'o', 'o', 'o'];
                document.getElementById('active-chord-name').innerText = "DIY";
                document.getElementById('active-chord-type').innerText = "나만의 신비로운 코드";
                document.getElementById('fingering-text').innerHTML = "✨ 지판을 눌러 보석을 직접 짚고 설계해보세요!";
                drawCustomDiagram();
            }
        }

        // Change synthesizer engine
        function changeSynthType() {
            synthType = document.getElementById('select-synth').value;
            playActiveChord();
        }

        // Filter chords by category
        function filterCategory(cat) {
            document.querySelectorAll('.category-btn').forEach(btn => {
                btn.className = "category-btn px-3 py-1.5 bg-white text-pink-500 border border-pink-200 rounded-full text-xs font-bold shadow-sm hover:bg-pink-100 transition-all";
            });

            const activeBtn = document.getElementById(`btn-${cat}`);
            if (activeBtn) {
                activeBtn.className = "category-btn px-3 py-1.5 bg-pink-400 text-white rounded-full text-xs font-bold shadow-md hover:bg-pink-500 transition-all scale-105";
            }

            if (cat === 'all') {
                renderChords(CHORDS);
            } else {
                const filtered = CHORDS.filter(chord => chord.category === cat);
                renderChords(filtered);
            }
        }

        // Render Chords List
        function renderChords(list) {
            const grid = document.getElementById('chord-grid');
            grid.innerHTML = '';

            list.forEach(chord => {
                const btn = document.createElement('button');
                const isActive = chord.id === currentActiveChordId;
                btn.className = `p-2 rounded-2xl border-2 font-black text-lg transition-all duration-200 transform hover:scale-105 shadow-sm flex flex-col items-center justify-center gap-0.5 ${
                    isActive 
                    ? 'bg-gradient-to-b from-pink-300 to-pink-400 text-white border-pink-400 shadow-[0_4px_10px_rgba(244,114,182,0.4)]' 
                    : 'bg-white text-pink-600 border-pink-100 hover:border-pink-300 hover:bg-pink-50/50'
                }`;
                btn.onclick = () => selectChord(chord.id);
                
                btn.innerHTML = `
                    <span class="cute-font text-xl">${chord.name}</span>
                    <span class="text-[8px] font-bold tracking-tight text-pink-400/90 bg-pink-50 px-1.5 py-0.5 rounded-full ${isActive ? 'text-pink-600 bg-white' : ''}">
                        ${chord.category === 'major' ? '💖 Major' : chord.category === 'custom' ? '🪄 DIY' : '🧸 Minor'}
                    </span>
                `;
                grid.appendChild(btn);
            });
        }

        // Select specific chord
        function selectChord(id) {
            if (currentMode === 'creator') return;

            currentActiveChordId = id;
            const chord = CHORDS.find(c => c.id === id);
            if (!chord) return;
            
            // Re-render
            const activeBtn = document.querySelector('.category-btn.bg-pink-400');
            const currentCat = activeBtn ? activeBtn.id.replace('btn-', '') : 'all';
            if (currentCat === 'all') {
                renderChords(CHORDS);
            } else {
                renderChords(CHORDS.filter(c => c.category === currentCat));
            }

            document.getElementById('active-chord-name').innerText = chord.name;
            document.getElementById('active-chord-type').innerText = chord.fullName;
            document.getElementById('fingering-text').innerHTML = `🌸 <b>연주 팁:</b> ${chord.text}`;

            updateFingerMap(chord.markers);
            drawChordDiagram(chord);
            playActiveChord(true); // Quiet initialization
        }

        // Helper to update bottom finger visualizers
        function updateFingerMap(markers) {
            for (let i = 1; i <= 4; i++) {
                const fingerEl = document.getElementById(`finger-${i}`);
                const detailEl = document.getElementById(`finger-${i}-detail`);
                if (fingerEl && detailEl) {
                    fingerEl.style.opacity = '0.35';
                    fingerEl.style.transform = 'scale(0.9)';
                    detailEl.innerText = '💤';
                    detailEl.className = "text-[8px] text-pink-300 font-bold bg-white px-1.5 py-0.5 rounded-full border border-pink-100 mt-1 transition-all";
                }
            }

            markers.forEach(marker => {
                const fingerEl = document.getElementById(`finger-${marker.num}`);
                const detailEl = document.getElementById(`finger-${marker.num}-detail`);
                if (fingerEl && detailEl) {
                    fingerEl.style.opacity = '1';
                    fingerEl.style.transform = 'scale(1.05)';
                    detailEl.innerText = `${marker.s}줄 ${marker.f}프`;
                    detailEl.className = "text-[8px] text-white font-black bg-gradient-to-r from-pink-400 to-rose-400 px-1.5 py-0.5 rounded-full border border-pink-200 mt-1 transition-all shadow-sm animate-pulse";
                }
            });
        }

        // Standard Diagram Drawing
        function drawChordDiagram(chord) {
            const markerGroup = document.getElementById('chord-markers');
            const openMuteGroup = document.getElementById('open-mute-markers');
            markerGroup.innerHTML = '';
            openMuteGroup.innerHTML = '';

            const stringX = [20, 44, 68, 92, 116, 140];
            const fretY = [30, 64, 98, 132, 166, 200];

            // 1. Draw top Open/Mute
            chord.openMute.forEach((mark, index) => {
                if (mark === 'x' || mark === 'o') {
                    const xPos = stringX[index];
                    const yPos = 18;
                    const text = document.createElementNS("http://www.w3.org/2000/svg", "text");
                    text.setAttribute("x", xPos);
                    text.setAttribute("y", yPos);
                    text.setAttribute("text-anchor", "middle");
                    text.setAttribute("fill", mark === 'x' ? '#f43f5e' : '#ec4899');
                    text.setAttribute("font-size", "14px");
                    text.setAttribute("font-weight", "black");
                    text.setAttribute("font-family", "Gowun Dodum");
                    text.textContent = mark.toUpperCase();
                    openMuteGroup.appendChild(text);
                }
            });

            // 2. Draw Fingered dots
            chord.markers.forEach(marker => {
                const stringIndex = 6 - marker.s;
                const xPos = stringX[stringIndex];
                const fretIndex = marker.f;
                const yPos = fretY[fretIndex - 1] + (fretY[fretIndex] - fretY[fretIndex - 1]) / 2;

                const g = document.createElementNS("http://www.w3.org/2000/svg", "g");

                // Jewel Circle
                const bgCircle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
                bgCircle.setAttribute("cx", xPos);
                bgCircle.setAttribute("cy", yPos);
                bgCircle.setAttribute("r", "12");
                bgCircle.setAttribute("fill", "#ff8ebb");
                bgCircle.setAttribute("stroke", "#fff");
                bgCircle.setAttribute("stroke-width", "2");

                // Emoji
                const emojiText = document.createElementNS("http://www.w3.org/2000/svg", "text");
                emojiText.setAttribute("x", xPos);
                emojiText.setAttribute("y", yPos + 4);
                emojiText.setAttribute("text-anchor", "middle");
                emojiText.setAttribute("font-size", "12px");
                emojiText.textContent = FINGER_EMOJIS[marker.num] || "";

                // Badge circle
                const badgeCircle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
                badgeCircle.setAttribute("cx", xPos + 9);
                badgeCircle.setAttribute("cy", yPos - 9);
                badgeCircle.setAttribute("r", "7");
                badgeCircle.setAttribute("fill", "#f43f5e");
                badgeCircle.setAttribute("stroke", "#fff");
                badgeCircle.setAttribute("stroke-width", "1.5");

                // Badge number
                const badgeText = document.createElementNS("http://www.w3.org/2000/svg", "text");
                badgeText.setAttribute("x", xPos + 9);
                badgeText.setAttribute("y", yPos - 6.5);
                badgeText.setAttribute("text-anchor", "middle");
                badgeText.setAttribute("fill", "#ffffff");
                badgeText.setAttribute("font-size", "8px");
                badgeText.setAttribute("font-weight", "black");
                badgeText.textContent = marker.num;

                g.appendChild(bgCircle);
                g.appendChild(emojiText);
                g.appendChild(badgeCircle);
                g.appendChild(badgeText);
                markerGroup.appendChild(g);
            });
        }

        // Custom Mode Live Sketch Canvas Redraw
        function drawCustomDiagram() {
            const tempChord = {
                markers: customMarkers,
                openMute: customOpenMute
            };
            drawChordDiagram(tempChord);
            updateFingerMap(customMarkers);
        }

        // Click / Touch interaction parsing on Fretboard (Supports DIY Custom design)
        function setupFretboardInteractions() {
            const svg = document.getElementById('fretboard');
            svg.addEventListener('click', (e) => {
                if (currentMode !== 'creator') {
                    playActiveChord(); // Simply play chord on library mode click
                    return;
                }

                // Parse click coordinates relative to SVG
                const rect = svg.getBoundingClientRect();
                const clickX = ((e.clientX - rect.left) / rect.width) * 160;
                const clickY = ((e.clientY - rect.top) / rect.height) * 200;

                const stringX = [20, 44, 68, 92, 116, 140];
                const fretY = [30, 64, 98, 132, 166, 200];

                // Check if clicking the top Open/Mute bar (Y < 28)
                if (clickY < 28) {
                    // Find closest string
                    let closestStringIdx = 0;
                    let minDiff = 999;
                    stringX.forEach((sx, idx) => {
                        const diff = Math.abs(clickX - sx);
                        if (diff < minDiff) {
                            minDiff = diff;
                            closestStringIdx = idx;
                        }
                    });

                    // Cycle value: 'o' -> 'x' -> ''
                    const currentVal = customOpenMute[closestStringIdx];
                    if (currentVal === 'o') customOpenMute[closestStringIdx] = 'x';
                    else if (currentVal === 'x') customOpenMute[closestStringIdx] = '';
                    else customOpenMute[closestStringIdx] = 'o';

                    drawCustomDiagram();
                    triggerInteractiveSound(closestStringIdx, customOpenMute[closestStringIdx] === 'o' ? 0 : 'x');
                    return;
                }

                // Otherwise, clicking on frets
                // 1. Find string
                let closestStringIdx = 0; // 0 = 6th string, 5 = 1st string
                let minXDiff = 999;
                stringX.forEach((sx, idx) => {
                    const diff = Math.abs(clickX - sx);
                    if (diff < minXDiff) {
                        minXDiff = diff;
                        closestStringIdx = idx;
                    }
                });

                // 2. Find fret
                let closestFretIdx = 0; // 1 to 5
                let minYDiff = 999;
                for (let f = 1; f <= 5; f++) {
                    const midY = fretY[f - 1] + (fretY[f] - fretY[f - 1]) / 2;
                    const diff = Math.abs(clickY - midY);
                    if (diff < minYDiff) {
                        minYDiff = diff;
                        closestFretIdx = f;
                    }
                }

                // Toggle string placement
                const stringNum = 6 - closestStringIdx; // Map index to guitar string number (6 to 1)
                const existingIdx = customMarkers.findIndex(m => m.s === stringNum);

                if (existingIdx !== -1) {
                    // If tap on the exact same fret, remove it
                    if (customMarkers[existingIdx].f === closestFretIdx) {
                        customMarkers.splice(existingIdx, 1);
                    } else {
                        // Change fret position
                        customMarkers[existingIdx].f = closestFretIdx;
                    }
                } else {
                    // Add new marker. Dynamically assign finger numbers 1 to 4 depending on availability
                    const usedFingers = customMarkers.map(m => m.num);
                    let availableFinger = 1;
                    for (let fNum = 1; fNum <= 4; fNum++) {
                        if (!usedFingers.includes(fNum)) {
                            availableFinger = fNum;
                            break;
                        }
                    }
                    customMarkers.push({
                        s: stringNum,
                        f: closestFretIdx,
                        num: availableFinger
                    });
                }

                // If a string is fretted, mute status becomes blank
                if (customMarkers.some(m => m.s === stringNum)) {
                    customOpenMute[closestStringIdx] = '';
                }

                drawCustomDiagram();
                
                // Play individual note immediately for cool feedback!
                const activeFret = customMarkers.find(m => m.s === stringNum)?.f || 0;
                triggerInteractiveSound(closestStringIdx, activeFret);
            });
        }

        // Instant note trigger when building custom chords
        function triggerInteractiveSound(stringIdx, fret) {
            initAudio();
            if (audioCtx.state === 'suspended') audioCtx.resume();
            if (fret === 'x') return;

            const baseFreq = STRING_FREQS[stringIdx];
            const freq = baseFreq * Math.pow(2, fret / 12);
            triggerPluck(freq, audioCtx.currentTime);
        }

        // Save customized chord from creator panel
        function saveCustomChord() {
            const nameInput = document.getElementById('custom-chord-name');
            let name = nameInput.value.trim();
            if (!name) {
                alert("코드를 대표하는 귀여운 이름을 지어주세요! 🎀");
                return;
            }

            // Create saved object
            const newId = "custom-" + Date.now();
            const newChord = {
                id: newId,
                name: name,
                fullName: "Princess Special (" + name + ")",
                category: "custom",
                markers: [...customMarkers],
                openMute: [...customOpenMute],
                text: "공주님이 직접 발명한 환상적인 소리의 커스텀 코드예요!"
            };

            // Add to DB
            CHORDS.push(newChord);
            renderChords(CHORDS);
            
            // Switch to library view to show saved card
            switchMode('library');
            selectChord(newId);

            // Clean inputs
            nameInput.value = '';
            customMarkers = [];
        }

        // Web Audio Initializer
        function initAudio() {
            if (!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            }
        }

        // Main Core Strum play
        function playActiveChord(isSilentInit = false) {
            initAudio();
            if (isSilentInit && audioCtx.state === 'suspended') return;
            if (audioCtx.state === 'suspended') audioCtx.resume();

            let chord;
            if (currentMode === 'creator') {
                chord = {
                    markers: customMarkers,
                    openMute: customOpenMute
                };
            } else {
                chord = CHORDS.find(c => c.id === currentActiveChordId);
            }

            if (!chord) return;
            const now = audioCtx.currentTime;

            // Fret values calculation
            const frets = [null, null, null, null, null, null];
            chord.openMute.forEach((mark, index) => {
                if (mark === 'o') frets[index] = 0;
                else if (mark === 'x') frets[index] = 'x';
            });
            chord.markers.forEach(marker => {
                const stringIdx = 6 - marker.s;
                frets[stringIdx] = marker.f;
            });

            // Normal Strum spacing
            const strumSpeed = 0.05;
            frets.forEach((fret, stringIdx) => {
                if (fret === 'x' || fret === null) return;
                const baseFreq = STRING_FREQS[stringIdx];
                const freq = baseFreq * Math.pow(2, fret / 12);
                triggerPluck(freq, now + (stringIdx * strumSpeed));
            });
        }

        // Customizable Synthesizers Pluck Engine
        function triggerPluck(frequency, startTime) {
            if (!audioCtx) return;

            if (synthType === 'musicbox') {
                // Preset 2: Sparkle Music Box
                const osc = audioCtx.createOscillator();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(frequency * 2, startTime); // Higher pitch for music box

                // Ring Modulator high chime harmonic
                const metalOsc = audioCtx.createOscillator();
                metalOsc.type = 'triangle';
                metalOsc.frequency.setValueAtTime(frequency * 5, startTime);

                const gainNode = audioCtx.createGain();
                const metalGain = audioCtx.createGain();

                gainNode.gain.setValueAtTime(0, startTime);
                gainNode.gain.linearRampToValueAtTime(0.15, startTime + 0.002);
                gainNode.gain.exponentialRampToValueAtTime(0.001, startTime + 1.8); // Long bell ring

                metalGain.gain.setValueAtTime(0, startTime);
                metalGain.gain.linearRampToValueAtTime(0.04, startTime + 0.001);
                metalGain.gain.exponentialRampToValueAtTime(0.0001, startTime + 0.15);

                osc.connect(gainNode);
                metalOsc.connect(metalGain);

                gainNode.connect(audioCtx.destination);
                metalGain.connect(audioCtx.destination);

                osc.start(startTime);
                metalOsc.start(startTime);
                osc.stop(startTime + 1.9);
                metalOsc.stop(startTime + 0.2);

            } else if (synthType === 'harp') {
                // Preset 3: Cosmic Shimmer Harp
                const osc = audioCtx.createOscillator();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(frequency, startTime);
                
                // Add a cute quick sweep slide for classic glissando harp texture
                osc.frequency.exponentialRampToValueAtTime(frequency * 1.02, startTime + 0.05);

                const subOsc = audioCtx.createOscillator();
                subOsc.type = 'triangle';
                subOsc.frequency.setValueAtTime(frequency * 1.5, startTime);

                const gainNode = audioCtx.createGain();
                gainNode.gain.setValueAtTime(0, startTime);
                gainNode.gain.linearRampToValueAtTime(0.12, startTime + 0.015);
                gainNode.gain.exponentialRampToValueAtTime(0.001, startTime + 2.5);

                // Add deep chorus panning effect visually simulated via detune
                osc.detune.setValueAtTime(-8, startTime);
                subOsc.detune.setValueAtTime(8, startTime);

                osc.connect(gainNode);
                subOsc.connect(gainNode);
                gainNode.connect(audioCtx.destination);

                osc.start(startTime);
                subOsc.start(startTime);
                osc.stop(startTime + 2.6);
                subOsc.stop(startTime + 2.6);

            } else {
                // Preset 1: Wooden Acoustic Guitar (Default Triangle synth)
                const osc = audioCtx.createOscillator();
                osc.type = 'triangle';
                osc.frequency.setValueAtTime(frequency, startTime);

                const subOsc = audioCtx.createOscillator();
                subOsc.type = 'sine';
                subOsc.frequency.setValueAtTime(frequency * 0.5, startTime);

                const sparkleOsc = audioCtx.createOscillator();
                sparkleOsc.type = 'sine';
                sparkleOsc.frequency.setValueAtTime(frequency * 3, startTime);

                const mainGain = audioCtx.createGain();
                const sparkleGain = audioCtx.createGain();

                mainGain.gain.setValueAtTime(0, startTime);
                mainGain.gain.linearRampToValueAtTime(0.2, startTime + 0.01);
                mainGain.gain.exponentialRampToValueAtTime(0.001, startTime + 1.2);

                sparkleGain.gain.setValueAtTime(0, startTime);
                sparkleGain.gain.linearRampToValueAtTime(0.05, startTime + 0.005);
                sparkleGain.gain.exponentialRampToValueAtTime(0.0001, startTime + 0.3);

                osc.connect(mainGain);
                subOsc.connect(mainGain);
                sparkleOsc.connect(sparkleGain);

                mainGain.connect(audioCtx.destination);
                sparkleGain.connect(audioCtx.destination);

                osc.start(startTime);
                subOsc.start(startTime);
                sparkleOsc.start(startTime);

                osc.stop(startTime + 1.3);
                subOsc.stop(startTime + 1.3);
                sparkleOsc.stop(startTime + 0.4);
            }
        }

        // Toggle automatic drum pattern player
        function toggleAutoRhythm() {
            const pattern = document.getElementById('select-rhythm').value;
            if (pattern === 'single') {
                playActiveChord();
                return;
            }

            if (isRhythmPlaying) {
                stopAutoRhythm();
            } else {
                startAutoRhythm(pattern);
            }
        }

        function startAutoRhythm(pattern) {
            initAudio();
            if (audioCtx.state === 'suspended') audioCtx.resume();
            
            isRhythmPlaying = true;
            document.getElementById('rhythm-play-icon').className = "fa-solid fa-pause";
            document.getElementById('bpm-container').classList.remove('hidden');

            let beatIndex = 0;
            const intervalMs = (60 / currentBpm) * 1000; // Time per beat

            function tick() {
                if (!isRhythmPlaying) return;

                if (pattern === 'waltz') {
                    // 3/4 Waltz Beat (1: Strum, 2: Tap chord, 3: Tap chord)
                    if (beatIndex % 3 === 0) {
                        playActiveChord(); // Strong heavy down-strum
                    } else {
                        // Light cute tap sound representation using high chord registers
                        triggerWaltzAccent();
                    }
                    beatIndex++;
                } else if (pattern === 'shuffle') {
                    // 4/4 Shuffle bouncy groove (D-DU-D-DU)
                    if (beatIndex % 4 === 0 || beatIndex % 4 === 2) {
                        playActiveChord(); // Main Down beats
                    } else if (beatIndex % 4 === 1 || beatIndex % 4 === 3) {
                        // Swing delay bounce
                        setTimeout(() => {
                            if (isRhythmPlaying) playActiveChord();
                        }, intervalMs * 0.3);
                    }
                    beatIndex++;
                }

                // Loop with dynamic BPM check
                const currentInterval = (60 / currentBpm) * 1000;
                rhythmTimer = setTimeout(tick, currentInterval);
            }

            tick();
        }

        function stopAutoRhythm() {
            isRhythmPlaying = false;
            if (rhythmTimer) clearTimeout(rhythmTimer);
            document.getElementById('rhythm-play-icon').className = "fa-solid fa-play";
            document.getElementById('bpm-container').classList.add('hidden');
        }

        function changeBpm(val) {
            currentBpm = val;
            document.getElementById('bpm-val').innerText = val;
        }

        // Decorative rhythmic accent sounds for empty beats
        function triggerWaltzAccent() {
            const now = audioCtx.currentTime;
            // Play only high sweet strings (1st, 2nd, 3rd)
            const activeChord = CHORDS.find(c => c.id === currentActiveChordId) || { markers: [], openMute: [] };
            const frets = [null, null, null, null, null, null];
            
            activeChord.openMute.forEach((mark, i) => { if (mark === 'o') frets[i] = 0; });
            activeChord.markers.forEach(m => { frets[6 - m.s] = m.f; });

            // Just strum string indices 3, 4, 5 (High G, B, E)
            let noteDelay = 0;
            [3, 4, 5].forEach(strIdx => {
                const fret = frets[strIdx];
                if (fret === 'x' || fret === null) return;
                const baseFreq = STRING_FREQS[strIdx];
                const freq = baseFreq * Math.pow(2, fret / 12);
                triggerPluck(freq * 1.1, now + noteDelay); // slightly brighter pitch
                noteDelay += 0.02;
            });
        }
    </script>
</body>
</html>
