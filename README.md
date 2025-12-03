# White-devil-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>!!! DOOM INITIATED !!!</title>
    <!-- Load Tailwind CSS for utility classes -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Tone.js for audio drones and jump scares -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.8.49/Tone.js"></script>
    <!-- Load Space Mono font for hacking feel -->
    <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    
    <style>
        /* --- Core Styling --- */
        :root {
            --blood-red: #cc0000;
            --dark-red: #8b0000;
            --text-color: #ff3333; /* Bright, active red for main text */
            --climax-green: #00ff00; /* Neon green for the final message */
        }

        body {
            font-family: 'Space Mono', monospace;
            background-color: #000000; /* Absolute Black */
            color: var(--text-color);
            overflow: hidden; 
            transition: all 0.5s ease-in-out;
            touch-action: manipulation;
        }

        /* --- Terminal Screen Container and Glitch Effect (Red/Black Phase) --- */
        .terminal-screen {
            box-shadow: 0 0 15px var(--text-color), 0 0 30px var(--dark-red) inset;
            border: 4px solid var(--blood-red);
            padding: 2rem;
            min-height: 100vh;
            animation: terror-flicker 0.08s infinite alternate;
            background-color: #000000; 
        }

        @keyframes terror-flicker {
            0% { filter: contrast(110%); opacity: 1; }
            50% { filter: contrast(90%); opacity: 0.95; transform: skewX(0.5deg); }
            100% { filter: contrast(120%); opacity: 1; transform: skewX(-0.5deg); }
        }
        
        /* Ultra-fast glitch for the final 10 seconds */
        .panic-glitch {
            animation: panic-flicker 0.03s infinite alternate !important;
        }
        @keyframes panic-flicker {
            0% { filter: contrast(150%); opacity: 1; transform: translateX(4px) skewY(1deg); }
            50% { filter: contrast(70%); opacity: 0.8; transform: translateX(-4px) skewY(-1deg); }
            100% { filter: contrast(130%); opacity: 1; transform: translateX(0); }
        }


        /* --- Code Rain (Red, Subtler Noise) --- */
        .code-rain {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            opacity: 0.15; 
            background: repeating-linear-gradient(
                to bottom,
                transparent,
                transparent 1px,
                var(--dark-red) 1px,
                var(--dark-red) 2px
            );
            animation: scanline 1.5s linear infinite;
        }

        @keyframes scanline {
            0% { background-position: 0 0; }
            100% { background-position: 0 40px; }
        }

        .main-content {
            position: relative;
            z-index: 10;
        }

        /* --- Intermediate Horror Mode (Red/Black Overload) --- */
        .horror-mode {
            background-color: #400000 !important; /* Extremely Deep Red */
            color: var(--text-color) !important;
        }
        
        .horror-mode .code-rain {
            opacity: 0.8 !important; /* Max Visibility */
            background: repeating-linear-gradient(
                to bottom,
                transparent,
                transparent 1px,
                var(--text-color) 1px,
                var(--text-color) 3px
            ) !important;
        }
        
        /* NEW: White on Black terminal style for the final message window */
        .white-on-black-climax {
            background-color: #000000 !important; /* Pure Black Background */
            color: #ffffff !important; /* Pure White Text */
            border: 4px solid #ffffff !important; /* White border for clean terminal look */
            box-shadow: 0 0 10px #ffffff, 0 0 20px #ffffff inset !important; /* White glow */
            animation: none !important; /* Stop the terror flicker for a clean look */
        }
        
        .final-message-text {
            color: var(--climax-green) !important; /* Neon Green for the final, chilling line */
            text-shadow: 0 0 15px var(--climax-green) !important; 
        }
        
        .climax-button {
            background-color: #000000 !important;
            color: var(--climax-green) !important;
            border: 2px solid var(--climax-green) !important;
            box-shadow: 0 0 10px var(--climax-green) !important;
            transition: all 0.3s ease;
        }
        .climax-button:hover {
            box-shadow: 0 0 20px var(--climax-green) !important;
        }

        /* Other standard styles */
        .blinking-cursor {
            font-weight: bold;
            animation: blink 0.3s infinite;
        }
        .text-stage-title { color: var(--text-color); text-shadow: 0 0 10px var(--text-color); }
        .text-timer { color: var(--blood-red); text-shadow: 0 0 15px var(--blood-red); }
        .initial-warning {
            color: var(--blood-red);
            font-size: 1.5rem;
            text-shadow: 0 0 5px var(--blood-red);
            line-height: 1.5;
        }
        /* Overriding red text for final stage checklist */
        .white-on-black-climax .checkbox-item span,
        .white-on-black-climax .text-stage-title span {
            color: #ffffff !important;
            text-shadow: none !important;
        }
        .checkbox-item input[type="checkbox"]:checked:after {
            content: '!!!'; 
            color: var(--text-color); /* Still uses red for the checkmark for contrast */
        }
    </style>
</head>
<body class="bg-[#000000] text-prank-red flex items-center justify-center">

    <div id="app" class="terminal-screen w-full max-w-4xl mx-auto rounded-lg shadow-2xl p-4 sm:p-8">
        <!-- The Hacking Background Effect (Code Rain) -->
        <div id="code-rain" class="code-rain"></div>

        <div class="main-content space-y-8">
            
            <!-- Stage 0: Welcome Screen (Red/Black/Flicker) -->
            <div id="stage-0" class="text-center transition-opacity duration-1000">
                <h1 class="text-4xl sm:text-6xl font-bold text-stage-title mb-6 animate-pulse">
                    [[ CORE SYSTEM EXPOSED ]]
                </h1>
                <p class="text-2xl sm:text-3xl text-prank-red mb-10">
                    <span class="text-prank-red font-extrabold">WHITE DEVIL</span> is now monitoring your life<span class="blinking-cursor">_</span>
                </p>
                
                <p class="initial-warning font-bold mt-12 mb-10">
                    !!! WARNING: YOUR PRIVACY IS DEAD.<br>
                    CLICK ANYWHERE TO CONFIRM YOUR DOOM & BEGIN THE HARVEST. !!!
                </p>

                <p id="audio-status" class="mt-8 text-sm text-yellow-500">
                    (ACTION WILL ACTIVATE YOUR FRONT CAMERA & MICROPHONE - FOREVER)
                </p>
            </div>

            <!-- Stage 1, 2, 3: Simulation Active (Intense Red/Black Flicker) -->
            <div id="stage-active" class="hidden space-y-6">
                
                <!-- Target Identification Block -->
                <div class="text-sm text-gray-400 border-b border-blood-red pb-2 mb-4">
                    <p class="font-bold text-blood-red">HOST SCAN: CRITICAL BREACH - TARGET CONFIRMED</p>
                    <p>IP: <span id="spoofed-ip">10.0.1.666</span> (PRIVATE / SECURED)</p>
                    <p>DEVICE ID: <span id="spoofed-device-id">1A3C-D9E4-F6B2-01A0</span> | OS: <span id="spoofed-os">iOS_ROOTED</span></p>
                    <p>OWNER HASH: <span id="spoofed-owner" class="text-text-color font-bold">USER_ID_DEATH_HEX_17D</span></p>
                </div>
                
                <!-- Timer -->
                <div class="text-center border-b border-blood-red pb-4">
                    <p class="text-xl sm:text-2xl font-bold text-stage-title mb-2">
                        TIME REMAINING UNTIL COMPLETE INVASION
                    </p>
                    <div class="text-6xl sm:text-8xl font-extrabold text-timer">
                        <span id="countdown-timer">00:45</span>
                    </div>
                </div>

                <!-- Live Status and Progress Bar -->
                <div>
                    <p id="status-message" class="stage-message text-xl sm:text-3xl font-bold text-blood-red mb-2">
                        // PHASE 1: TARGETING YOUR FRONT-FACING CAMERA & MIC. INITIALIZING SPY MODE...
                    </p>
                    <div class="w-full bg-gray-900 border border-dark-red rounded-full h-4 sm:h-6">
                        <div id="progress-bar" class="bg-text-color h-full rounded-full transition-none" style="width: 0%"></div>
                    </div>
                    <div class="flex justify-between text-sm mt-1">
                        <span class="text-blood-red">SYSTEM INFILTRATION PROGRESS</span>
                        <span id="progress-percentage" class="text-text-color font-bold">0%</span>
                    </div>
                </div>

                <!-- Data Transfer Visualization -->
                <div class="flex flex-col sm:flex-row items-center justify-around text-center mt-6">
                    <!-- User Phone -->
                    <div class="w-full sm:w-1/3 p-2 border border-text-color rounded-xl shadow-lg shadow-text-color/50">
                        <p class="text-sm text-blood-red">TARGET DEVICE (CAPTURED)</p>
                        <p class="text-lg font-bold">WEAPONIZED: ACTIVE</p>
                        <svg class="w-8 h-8 mx-auto mt-2 text-text-color" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" />
                        </svg>
                    </div>

                    <!-- Transfer Arrow -->
                    <div class="my-4 sm:my-0 sm:w-1/6 flex justify-center items-center">
                        <span class="text-blood-red text-4xl transfer-arrow">&rArr;</span>
                    </div>
                    
                    <!-- Dark Web Hub -->
                    <div class="w-full sm:w-1/3 p-2 border border-blood-red rounded-xl shadow-lg shadow-blood-red/70">
                        <p class="text-sm text-text-color">WHITE DEVIL DATA STREAM</p>
                        <p class="text-lg font-bold">HARVEST NODE: RECEIVING</p>
                        <svg class="w-8 h-8 mx-auto mt-2 text-blood-red" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9h-3M12 21a9 9 0 01-9-9m9 9v-3M3 12h3M12 3v3m0 0V3m0 3a9 9 0 00-9 9m3 3h3m0 0v-3m-3 3h-3" />
                        </svg>
                    </div>
                </div>

                <!-- Log Console (Taller for more visual data) -->
                <div class="h-48 bg-black p-2 overflow-y-scroll text-sm border border-dark-red/50">
                    <pre id="log-console" class="text-text-color"></pre>
                </div>

            </div>

            <!-- Stage 4: Completion Screen (White-on-Black Climax) -->
            <div id="stage-final" class="hidden text-center transition-opacity duration-1000 p-8">
                <h1 class="text-6xl sm:text-7xl font-extrabold mb-4 text-stage-title animate-pulse">
                    <span>!!! HARVEST COMPLETE !!!</span>
                </h1>
                
                <p class="text-3xl sm:text-4xl font-bold mb-6">
                    [ WHITE DEVIL ] OWNERSHIP TRANSFER LOCKED.
                </p>

                <!-- Checklist of Stolen Data (White Text) -->
                <div class="text-left max-w-md mx-auto my-8">
                    <div class="checkbox-item">
                        <input type="checkbox" checked disabled>
                        <span>CONTACTS, PASSWORDS, AND GPS DATA RETAINED</span>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" checked disabled>
                        <span>PERMANENT CAMERA/MIC BACKDOOR ACTIVE</span>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" checked disabled>
                        <span>ALL EMAILS & PRIVATE CHATS DECRYPTED</span>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" checked disabled>
                        <span>SENSITIVE PHOTOS & VIDEO ARCHIVES UPLOADED</span>
                    </div>
                </div>

                <!-- Final Message (Neon Green) -->
                <div class="mt-12 text-5xl sm:text-6xl font-extrabold animate-bounce final-message-text">
                    <p>I &nbsp; S E E &nbsp; Y O U &nbsp; N O W</p>
                </div>
                <!-- Prank reset button (Black/Green Hacker Style) -->
                <button onclick="resetAndRestart();" class="mt-12 px-8 py-4 font-bold rounded-md transition duration-300 climax-button">
                    SYSTEM LOCKDOWN: ATTEMPT ABORT (ACCESS DENIED)
                </button>
            </div>

        </div>
    </div>

    <script>
        // --- Configuration ---
        const DURATION = 45; 
        const PROGRESS_RATE = 20; 
        const LOG_MESSAGE_INTERVAL = 800; 
        const BLOOD_RED = '#cc0000'; 

        // --- State Variables ---
        let timerInterval = null;
        let progressInterval = null;
        let logInterval = null;
        let seconds = DURATION;
        let progress = 0;
        let statusIndex = 0;
        let isSimulationRunning = false;
        let isAudioSetup = false;
        let isAudioLoading = false;
        
        // --- API & Audio Setup ---
        const apiKey = "";
        const ttsApiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-tts:generateContent?key=${apiKey}`;
        const ttsPrompt = "Your private files are mine. Your location is exposed. I know who you truly are. Look at your screen. It was never a prank. It's too late to run.";
        let audioUrl = null;
        let audioStatusElement = document.getElementById('audio-status');
        let droneSynth = null;
        let terminalScreen = document.getElementById('app');

        // --- DOM Elements ---
        const body = document.body;
        const stage0 = document.getElementById('stage-0');
        const stageActive = document.getElementById('stage-active');
        const stageFinal = document.getElementById('stage-final');
        const timerDisplay = document.getElementById('countdown-timer');
        const progressBar = document.getElementById('progress-bar');
        const progressPercentage = document.getElementById('progress-percentage');
        const statusMessage = document.getElementById('status-message');
        const logConsole = document.getElementById('log-console');
        
        // --- Utility Functions for Audio Conversion (Required for TTS) ---
        
        function base64ToArrayBuffer(base64) {
            const binaryString = atob(base64);
            const len = binaryString.length;
            const bytes = new Uint8Array(len);
            for (let i = 0; i < len; i++) {
                bytes[i] = binaryString.charCodeAt(i);
            }
            return bytes.buffer;
        }

        function writeString(view, offset, string) {
            for (let i = 0; i < string.length; i++) {
                view.setUint8(offset + i, string.charCodeAt(i));
            }
        }

        function pcmToWav(pcm16, sampleRate = 24000) {
            const numChannels = 1;
            const bitsPerSample = 16;
            const byteRate = (sampleRate * numChannels * bitsPerSample) / 8;
            const blockAlign = (numChannels * bitsPerSample) / 8;
            
            const buffer = new ArrayBuffer(44 + pcm16.length * 2);
            const view = new DataView(buffer);

            // RIFF header
            writeString(view, 0, 'RIFF');
            view.setUint32(4, 36 + pcm16.length * 2, true);
            writeString(view, 8, 'WAVE');

            // fmt sub-chunk
            writeString(view, 12, 'fmt ');
            view.setUint32(16, 16, true);
            view.setUint16(20, 1, true);
            view.setUint16(22, numChannels, true);
            view.setUint32(24, sampleRate, true);
            view.setUint32(28, byteRate, true);
            view.setUint16(32, blockAlign, true);
            view.setUint16(34, bitsPerSample, true);

            // data sub-chunk
            writeString(view, 36, 'data');
            view.setUint32(40, pcm16.length * 2, true);

            // Write PCM data
            for (let i = 0; i < pcm16.length; i++) {
                view.setInt16(44 + i * 2, pcm16[i], true);
            }

            return new Blob([view], { type: 'audio/wav' });
        }
        
        // --- History Manipulation Logic (Blocks Back Button) ---

        // The handler function that traps the user when they hit the back button
        function handleBackNavigation() {
            // Push a new state immediately to cancel the navigation, trapping the user on the page.
            history.pushState(null, '', location.href); 
            console.log("Back button hit. Trapped in history stack.");
            // Note: We rely solely on history.pushState and do not use event.preventDefault() 
            // as the latter can sometimes be ignored or cause undesirable side effects.
        }

        function startHistoryBlocker() {
            // Add two states to the history so the user has to press back twice
            // before hitting the page they came from (and triggering the trap twice).
            history.pushState(null, '', location.href);
            history.pushState(null, '', location.href);

            // Add the listener for when the user attempts to go back
            window.addEventListener('popstate', handleBackNavigation);
        }

        function stopHistoryBlocker() {
            // Remove the listener to allow normal back navigation
            window.removeEventListener('popstate', handleBackNavigation);
            console.log("History trap released.");
        }

        // --- Audio Logic ---
        function setupAudioDrone() {
            if (isAudioSetup) return;
            Tone.context.lookAhead = 0.0; 
            
            droneSynth = new Tone.NoiseSynth({
                noise: { type: "pink" },
                envelope: { attack: 0.005, decay: 0.1, sustain: 0.8, release: 0.5 }
            }).toDestination();
            
            isAudioSetup = true;
        }

        function startDrone() {
            if (!isAudioSetup) setupAudioDrone();
            droneSynth.volume.value = -25;
            droneSynth.triggerAttackRelease(DURATION + "s");
        }

        function stopDrone() {
            if (droneSynth) {
                droneSynth.triggerRelease();
            }
        }

        async function fetchAndPrepareAudio() {
            if (isAudioLoading || audioUrl !== null) return;
            isAudioLoading = true;
            
            if (!isSimulationRunning) {
                 audioStatusElement.textContent = "ATTENTION: PRE-CACHING HOSTILE VOICE MODULE (DO NOT WAIT)...";
            }
           
            const payload = {
                contents: [{ parts: [{ text: `Say in a deep, menacing voice, with chilling intensity and a slight, cold whisper: ${ttsPrompt}` }] }],
                generationConfig: {
                    responseModalities: ["AUDIO"],
                    speechConfig: {
                        voiceConfig: { prebuiltVoiceConfig: { voiceName: "Kore" } } 
                    }
                },
                model: "gemini-2.5-flash-preview-tts"
            };

            const maxRetries = 3;
            for (let i = 0; i < maxRetries; i++) {
                try {
                    const response = await fetch(ttsApiUrl, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(payload) });
                    if (!response.ok) throw new Error(`HTTP error! status: ${response.status}`);
                    const result = await response.json();
                    const part = result?.candidates?.[0]?.content?.parts?.[0];
                    const audioData = part?.inlineData?.data;
                    const mimeType = part?.inlineData?.mimeType;

                    if (audioData && mimeType && mimeType.startsWith("audio/L16")) {
                        const sampleRate = 24000;
                        const pcmData = base64ToArrayBuffer(audioData);
                        const pcm16 = new Int16Array(pcmData);
                        const wavBlob = pcmToWav(pcm16, sampleRate);
                        audioUrl = URL.createObjectURL(wavBlob);
                        
                         if (!isSimulationRunning) {
                            audioStatusElement.textContent = "(AUDIO MODULE READY - BEGIN THE HARVEST)";
                        }
                        isAudioLoading = false;
                        return;
                    } else {
                        throw new Error("Invalid audio data received from API.");
                    }
                } catch (error) {
                    console.error(`Attempt ${i + 1} failed: `, error);
                    if (i < maxRetries - 1) {
                        await new Promise(resolve => setTimeout(resolve, Math.pow(2, i) * 1000));
                    } else {
                        audioStatusElement.textContent = "(FATAL: AUDIO MODULE OFFLINE. PRANK WILL BE SILENT)";
                        audioUrl = null; 
                        isAudioLoading = false;
                    }
                }
            }
        }
        
        // --- Log Messages (Extreme Threatening) ---
        const logMessages = [
            'INITIATING MULTI-NATIONAL NODE ROUTING: via [UAE, RU, DE, HU, CH]. **TRACE INVISIBLE**',
            'CONNECTION ESTABLISHED. DEVICE FINGERPRINTED (MAC:00-A0-C9-14-C8-29) - **IDENTITY EXPOSED**',
            'VULNERABILITY EXPLOIT SUCCESSFUL. SYSTEM SHELL ACCESS GRANTED. **YOU ARE UNPROTECTED**',
            'HOOK INITIATED: ACTIVATING FRONT-FACING CAMERA. LIVE FEED STARTED. **SMILE**',
            'ALERT: /data/app/com.bank.mobile/credentials.db - **DECRYPTING ALL FINANCIALS**',
            'DATA DUMP: /storage/emulated/0/WhatsApp/Media - Initiating high-speed **PERSONAL HARVEST**.',
            'SYSTEM TRACE OVERRIDDEN. ALL SECURITY PROTOCOLS BYPASSED. **ABANDON HOPE**',
            'EXTRACTING: All stored browser passwords and 2FA secrets. **YOUR SECRETS ARE MINE**',
            'GEOLOCATION SERVICES LOCKED. YOUR CURRENT COORDINATES ARE KNOWN. **I KNOW WHERE YOU SLEEP**',
            'SCANNING: Microphone buffer for ambient noise and voice patterns. **I AM LISTENING**',
            'MIRRORING: CONTACT LIST, CALL HISTORY, AND DELETED MESSAGES. **YOUR FRIENDS ARE NEXT**',
            'DATA EXFILTRATION: 99.9% COMPLETE. TARGET ACHIEVED. **THE HARVEST IS OVER**',
            'FINALIZING: SELF-DESTRUCT SEQUENCE (LOGS) INITIATED. **NO TRACE. NO WITNESSES.**',
        ];

        const statusUpdates = [
            'PHASE 1: TARGETING YOUR FRONT-FACING CAMERA & MIC. INITIALIZING SPY MODE...',
            'PHASE 2: BREACHING CORE OS KERNEL. ADMIN ACCESS IS NOW WHITE DEVIL\'S...',
            'PHASE 3: REMOTE ROOT SHELL ESTABLISHED. WE HAVE FULL HARDWARE CONTROL.',
            'PHASE 4: EXTRACTING FINANCIAL AND DEEPLY PERSONAL FILES (IRREVERSIBLE)...',
            'PHASE 5: UPLOADING ALL SENSITIVE DATA TO DARK WEB NODE (PERMANENT COPY)...',
            'PHASE 6: DELETING ALL LOCAL EVIDENCE. YOUR DATA IS NO LONGER YOURS.',
            'SYSTEM LOCKDOWN IMMINENT: WHITE DEVIL IS TAKING CHARGE OF YOUR LIFE...'
        ];
        
        // --- Full-Screen Logic ---
        function requestFullScreen() {
            const element = document.documentElement;
            if (element.requestFullscreen) {
                element.requestFullscreen().catch(err => console.log("Fullscreen failed (normal for some browsers).", err));
            } else if (element.webkitRequestFullscreen) { 
                element.webkitRequestFullscreen().catch(err => console.log("Fullscreen failed (normal for some browsers).", err));
            } else if (element.msRequestFullscreen) { 
                element.msRequestFullscreen().catch(err => console.log("Fullscreen failed (normal for some browsers).", err));
            }
        }

        // --- Simulation Logic ---

        function formatTime(sec) {
            const minutes = Math.floor(sec / 60);
            const remainingSeconds = sec % 60;
            return `${String(minutes).padStart(2, '0')}:${String(remainingSeconds).padStart(2, '0')}`;
        }

        function startTimer() {
            timerInterval = setInterval(() => {
                seconds--;
                timerDisplay.textContent = formatTime(seconds);

                if (seconds === 10) {
                    terminalScreen.classList.add('panic-glitch');
                }

                if (seconds % 6 === 0 && seconds > 0 && statusIndex < statusUpdates.length) {
                    statusMessage.textContent = `// ${statusUpdates[statusIndex]}`;
                    statusIndex++;
                }

                if (seconds <= 0) {
                    clearInterval(timerInterval);
                    clearInterval(logInterval);
                    clearInterval(progressInterval);
                    showFinalStage();
                }
            }, 1000);
        }

        function startProgressBar() {
            const targetCompletionSeconds = 25;
            const totalUpdates = (targetCompletionSeconds * 1000) / PROGRESS_RATE;
            const progressPerUpdate = 100 / totalUpdates;

            progressInterval = setInterval(() => {
                if (progress < 100) {
                    progress += progressPerUpdate; 
                    if (progress > 100) progress = 100;
                    
                    const p = Math.floor(progress);
                    progressBar.style.width = `${p}%`;
                    progressPercentage.textContent = `${p}%`;
                }
            }, PROGRESS_RATE);
        }

        function startLogging() {
            let logIndex = 0;
            logConsole.innerHTML = ''; 
            logInterval = setInterval(() => {
                if (logIndex < logMessages.length) {
                    const timestamp = new Date().toLocaleTimeString('en-US', { hour12: false });
                    let message = logMessages[logIndex].replace(/\*\*(.*?)\*\*/g, '<span class="font-bold text-lg text-[#ff0000]">$1</span>');
                    logConsole.innerHTML += `<span style="color:${BLOOD_RED}">[${timestamp}]</span> ${message}<br>`;
                    logConsole.scrollTop = logConsole.scrollHeight;
                    logIndex++;
                }
            }, LOG_MESSAGE_INTERVAL);
        }

        function startSimulation() {
            if (isSimulationRunning) return;

            seconds = DURATION;
            progress = 0;
            statusIndex = 0;
            isSimulationRunning = true;
            
            // NEW: Trap the user in the history stack
            startHistoryBlocker();

            body.classList.remove('horror-mode');
            terminalScreen.classList.remove('panic-glitch');
            timerDisplay.textContent = formatTime(DURATION);
            progressBar.style.width = '0%';
            progressPercentage.textContent = '0%';
            statusMessage.textContent = `// ${statusUpdates[0]}`;
            audioStatusElement.classList.add('hidden');

            // Quick fade out of start screen
            setTimeout(() => {
                stage0.classList.add('opacity-0');
            }, 100);
            
            // Switch screen and start timers
            setTimeout(() => {
                stage0.classList.add('hidden');
                stageActive.classList.remove('hidden');

                startTimer();
                startProgressBar();
                startLogging();
            }, 600);
        }

        function showFinalStage() {
            stopDrone();
            clearInterval(progressInterval);
            clearInterval(timerInterval);
            clearInterval(logInterval);
            isSimulationRunning = false;
            
            // NEW: Release the history trap (allow back button to work)
            stopHistoryBlocker();

            // 1. Play the terrifying TTS jump scare
            if (audioUrl) {
                const audio = new Audio(audioUrl);
                audio.volume = 0.9;
                audio.play().catch(e => console.error("Audio playback failed:", e));
            }
            
            // 2. Activate Horror Visuals for the background
            body.classList.add('horror-mode');
            terminalScreen.classList.remove('panic-glitch'); 

            // 3. Hide active stage
            stageActive.classList.add('hidden');

            // 4. APPLY WHITE-ON-BLACK CLIMAX STYLE TO THE FINAL STAGE CONTAINER
            terminalScreen.classList.add('white-on-black-climax');

            // 5. Show final, terrifying stage
            stageFinal.classList.remove('hidden');
            stageFinal.classList.add('opacity-100');

            // 6. Ensure progress bar shows 100%
            progressBar.style.width = '100%';
            progressPercentage.textContent = '100% (OWNERSHIP TRANSFER COMPLETE)';
        }
        
        function resetAndRestart() {
            // Ensure blocker is stopped on manual reset
            stopHistoryBlocker();

            if (document.exitFullscreen) {
                document.exitFullscreen();
            } else if (document.webkitExitFullscreen) { 
                document.webkitExitFullscreen();
            } else if (document.msExitFullscreen) { 
                document.msExitFullscreen();
            }

            // Remove all custom climax and horror styles
            terminalScreen.classList.remove('white-on-black-climax');
            body.classList.remove('horror-mode');

            // Reset UI visibility
            stageFinal.classList.add('hidden');
            stageActive.classList.add('hidden');
            stage0.classList.remove('hidden', 'opacity-0');
            audioStatusElement.classList.remove('hidden');

            // Clear any lingering intervals
            clearInterval(timerInterval);
            clearInterval(progressInterval);
            clearInterval(logInterval);
            
            // Reset status text
            seconds = DURATION;
            timerDisplay.textContent = formatTime(DURATION);
        }
        
        // --- Target Information Generator (Fake Data) ---
        function generateTargetInfo() {
            document.getElementById('spoofed-ip').textContent = `10.0.${Math.floor(Math.random() * 255)}.${Math.floor(Math.random() * 255)}`;
            const deviceId = Math.random().toString(16).slice(2, 6).toUpperCase() + '-' + Math.random().toString(16).slice(2, 6).toUpperCase();
            document.getElementById('spoofed-device-id').textContent = deviceId;
            const osTypes = ["iOS_ROOTED", "ANDROID_EXPOSED", "WINDOWS_INSECURE"];
            document.getElementById('spoofed-os').textContent = osTypes[Math.floor(Math.random() * osTypes.length)];
        }


        // --- Primary Event Listener: Guarantees Start on Click/Touch ---
        document.addEventListener('click', function handler(e) {
            // Prevent accidental clicks restarting if already running or clicking the button
            if (isSimulationRunning || e.target.closest('button')) {
                return;
            }

            // Start full screen and audio context
            requestFullScreen();

            if (isAudioSetup && Tone.context.state !== 'running') {
                Tone.start();
            }

            startDrone();
            startSimulation();
            
            // Remove the initial handler so subsequent clicks don't interfere
            document.removeEventListener('click', handler);

        }, { once: true });
        
        // --- Initialization ---
        document.addEventListener('DOMContentLoaded', () => {
            generateTargetInfo();
            setupAudioDrone();
            // Start loading the TTS audio in the background
            fetchAndPrepareAudio(); 
        });
    </script>
</body>
</html>

