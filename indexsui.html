<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NovaTech Kaydedici - Minimalist Arayüz</title>
    <!--
        NOT: PHP sunucu taraflı çalıştığı için, ses kaydı ve IndexedDB
        işlemleri tarayıcıda (client-side) JavaScript ile yapılmak zorundadır.
        Bu dosya PHP uzantısıyla sunulmuştur.
    -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
    <link href="https://fonts.googleapis.com/icon?family=Material+Symbols_Rounded" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f1f5f9; }
        .material-symbols-rounded {
          font-variation-settings: 'FILL' 1, 'wght' 400, 'GRAD' 0, 'opsz' 24;
          font-size: 32px;
        }
        .app-card { transform: translateY(20px); opacity: 0; }
        .record-item { cursor: pointer; transition: all 0.15s ease-in-out; }
        .record-item:hover {
            background-color: #e2e8f0; 
            transform: translateY(-1px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.06);
        }
        .btn-record {
            background-color: #ef4444; 
            transition: all 0.3s;
        }
        .btn-record:hover { background-color: #dc2626; }
        .icon-btn-size {
            width: 64px; 
            height: 64px;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body class="min-h-screen p-4 sm:p-8 flex items-start sm:items-center justify-center">

    <div id="app" class="app-card w-full max-w-lg bg-white shadow-2xl rounded-xl p-6 sm:p-8">
        
        <!-- Başlık Bölümü -->
        <h1 class="text-3xl font-extrabold text-gray-900 mb-2 flex items-center">
            <span class="material-symbols-rounded text-red-500 mr-2">mic</span>
            NovaTech Kaydedici
        </h1>
        <p class="text-sm text-gray-500 mb-6">Basit ve hızlı ses kaydı. (Kısayol: Space)</p>

        <!-- Durum ve Kontrol Bölümü -->
        <div class="space-y-4">
            <div id="status-display" class="p-3 text-center rounded-lg font-medium bg-indigo-100 text-indigo-800">
                Mikrofon bağlantısı bekleniyor...
            </div>

            <div class="flex justify-center items-center gap-6">
                <!-- Kaydı Başlat butonu (Sadece İkon) -->
                <button id="record-button" 
                        class="icon-btn-size rounded-full text-white font-semibold btn-record shadow-lg shadow-red-300 transition duration-150 ease-in-out disabled:opacity-50" 
                        title="Kaydı Başlat (Space)" 
                        disabled>
                    <span class="material-symbols-rounded">fiber_manual_record</span>
                </button>
                
                <!-- Kaydı Durdur butonu (Sadece İkon) -->
                <button id="stop-button" 
                        class="icon-btn-size rounded-full text-white font-semibold bg-gray-500 shadow-lg shadow-gray-300 transition duration-150 ease-in-out disabled:opacity-50" 
                        title="Kaydı Durdur & Kaydet (Space)" 
                        disabled>
                    <span class="material-symbols-rounded">stop</span>
                </button>
            </div>
            
            <div id="timer" class="text-center text-3xl font-mono text-gray-800 pt-2">00:00</div>
        </div>

        <!-- Kayıt Listesi Bölümü -->
        <div class="mt-8 pt-4 border-t border-gray-200">
            <h2 class="text-xl font-bold text-gray-800 mb-3">Kayıtlarım <span class="text-sm font-normal text-indigo-500">(Kırpmak için tıklayın)</span></h2>
            <div id="recordings-list" class="bg-white border border-gray-200 rounded-lg max-h-60 overflow-y-auto">
                <p id="empty-message" class="p-4 text-center text-gray-500">Henüz bir kayıt yok.</p>
            </div>
        </div>

        <!-- Uyarı Modalı -->
        <div id="custom-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden items-center justify-center p-4 z-50">
            <div class="bg-white rounded-lg shadow-xl p-6 max-w-sm w-full">
                <h3 id="modal-title" class="text-lg font-bold text-red-600 mb-3">Hata</h3>
                <p id="modal-message" class="text-gray-700 mb-4"></p>
                <div id="modal-actions" class="flex justify-end space-x-2">
                    <button id="modal-cancel-btn" class="py-2 px-4 bg-gray-300 text-gray-800 rounded-lg font-semibold hover:bg-gray-400 hidden">İptal</button>
                    <button id="modal-confirm-btn" class="py-2 px-4 bg-red-500 text-white rounded-lg font-semibold hover:bg-red-600">Tamam</button>
                </div>
            </div>
        </div>

         <!-- Kırpma Modalı -->
        <div id="trim-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden items-center justify-center p-4 z-50">
            <div class="bg-white rounded-xl shadow-2xl p-6 max-w-md w-full">
                <h3 class="text-2xl font-bold text-gray-800 mb-4">Kaydı Kırp</h3>
                
                <p id="trim-duration-info" class="text-sm text-gray-600 mb-4">Toplam Süre: 00:00</p>
                
                <div class="space-y-4">
                    <!-- Başlangıç Saati -->
                    <div>
                        <label for="trim-start" class="block text-sm font-medium text-gray-700">Başlangıç Zamanı (saniye)</label>
                        <input type="number" id="trim-start" min="0" value="0" step="0.1" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 p-2 border">
                    </div>
                    <!-- Bitiş Saati -->
                    <div>
                        <label for="trim-end" class="block text-sm font-medium text-gray-700">Bitiş Zamanı (saniye)</label>
                        <input type="number" id="trim-end" min="0.1" step="0.1" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 p-2 border">
                    </div>
                    
                    <button id="trim-save-button" class="w-full py-3 bg-indigo-500 text-white rounded-lg font-semibold hover:bg-indigo-600 transition duration-150 ease-in-out">
                        Kaydı Kırp ve Yeni Kayıt Olarak Kaydet
                    </button>
                    <button onclick="document.getElementById('trim-modal').classList.add('hidden');" class="w-full py-2 text-gray-600 rounded-lg font-semibold hover:text-gray-800">
                        İptal
                    </button>
                </div>
            </div>
        </div>

    </div>

    <script>
        // --- PHP Desteği Olmayan İşlemler İçin JavaScript (IndexedDB) ---
        
        // Sabitler
        const DB_NAME = 'NovaTechDB';
        const STORE_NAME = 'Recordings';
        const DB_VERSION = 1;
        
        // DOM Elementleri
        const statusDisplay = document.getElementById('status-display');
        const recordButton = document.getElementById('record-button');
        const stopButton = document.getElementById('stop-button');
        const recordingsList = document.getElementById('recordings-list');
        const emptyMessage = document.getElementById('empty-message');
        const timerElement = document.getElementById('timer');
        
        // Modal Elementleri
        const customModal = document.getElementById('custom-modal');
        const modalTitle = document.getElementById('modal-title');
        const modalMessage = document.getElementById('modal-message');
        const modalConfirmBtn = document.getElementById('modal-confirm-btn');
        const modalCancelBtn = document.getElementById('modal-cancel-btn');

        // Trim Modal Elementleri
        const trimModal = document.getElementById('trim-modal');
        const trimDurationInfo = document.getElementById('trim-duration-info');
        const trimStartInput = document.getElementById('trim-start');
        const trimEndInput = document.getElementById('trim-end');
        const trimSaveButton = document.getElementById('trim-save-button');

        // Kayıt Değişkenleri
        let mediaRecorder;
        let audioChunks = [];
        let stream;
        let timerInterval;
        let startTime;
        let recordingAnime;
        let activeTrimRecord = null; 
        let audioContext; // Web Audio API Context


        // --- Yardımcı Fonksiyonlar ---

        function showCustomModal(title, message, isConfirmation = false, onConfirm = () => {}, onCancel = () => {}) {
            modalTitle.textContent = title;
            modalMessage.textContent = message;
            
            if (isConfirmation) {
                modalTitle.classList.replace('text-red-600', 'text-indigo-600');
                modalConfirmBtn.textContent = 'Evet, Sil';
                modalConfirmBtn.classList.replace('bg-red-500', 'bg-indigo-500');
                modalCancelBtn.classList.remove('hidden');
                
                modalConfirmBtn.onclick = () => { customModal.classList.add('hidden'); onConfirm(); };
                modalCancelBtn.onclick = () => { customModal.classList.add('hidden'); onCancel(); };
            } else {
                modalTitle.classList.replace('text-indigo-600', 'text-red-600');
                modalConfirmBtn.textContent = 'Tamam';
                modalConfirmBtn.classList.replace('bg-indigo-500', 'bg-red-500');
                modalCancelBtn.classList.add('hidden');
                modalConfirmBtn.onclick = () => { customModal.classList.add('hidden'); };
            }

            customModal.classList.remove('hidden');
            customModal.classList.add('flex');
        }

        function startTimer() {
            startTime = Date.now();
            timerElement.textContent = '00:00';
            timerInterval = setInterval(() => {
                const elapsed = Date.now() - startTime;
                const totalSeconds = Math.floor(elapsed / 1000);
                const minutes = String(Math.floor(totalSeconds / 60)).padStart(2, '0');
                const seconds = String(totalSeconds % 60).padStart(2, '0');
                timerElement.textContent = `${minutes}:${seconds}`;
            }, 1000);
        }

        function stopTimer() {
            clearInterval(timerInterval);
            timerElement.textContent = '00:00';
        }

        function formatDuration(seconds) {
            const date = new Date(null);
            date.setSeconds(seconds);
            return date.toISOString().substr(11, 8);
        }

        function formatTimestamp(timestamp) {
            const date = new Date(timestamp);
            return date.toLocaleDateString('tr-TR', {
                year: 'numeric', month: 'short', day: 'numeric',
                hour: '2-digit', minute: '2-digit'
            });
        }

        // --- IndexedDB İşlemleri (PHP yerine tarayıcı veritabanı) ---

        function openDatabase() {
            return new Promise((resolve, reject) => {
                const request = indexedDB.open(DB_NAME, DB_VERSION);

                request.onupgradeneeded = (event) => {
                    const db = event.target.result;
                    if (!db.objectStoreNames.contains(STORE_NAME)) {
                        db.createObjectStore(STORE_NAME, { keyPath: 'id' }); 
                    }
                };

                request.onsuccess = (event) => { resolve(event.target.result); };
                request.onerror = (event) => { reject(`IndexedDB hatası: ${event.target.error}`); };
            });
        }

        /** IndexedDB'ye kaydeder (Önceki hatayı düzelten, asenkron süre hesaplamalı versiyon) */
        async function saveRecording(blob, nameSuffix = '') {
            try {
                // 1. Asenkron: Süreyi hesapla (Transaction dışında tutulur)
                const finalDuration = await new Promise(resolve => {
                    const tempAudio = new Audio(URL.createObjectURL(blob));
                    tempAudio.onloadedmetadata = () => {
                        resolve(formatDuration(Math.round(tempAudio.duration)));
                        URL.revokeObjectURL(tempAudio.src);
                    };
                    tempAudio.onerror = () => {
                        resolve('Bilinmeyen'); 
                        URL.revokeObjectURL(tempAudio.src);
                    };
                });
                
                /* Eğer PHP kullanılsaydı, bu noktada Blob'u 
                    FormData'ya koyup PHP sunucusuna POST edilirdi.
                */

                // 2. Senkron: Transaction ve ekleme işlemleri başlar
                const db = await openDatabase();
                const tx = db.transaction(STORE_NAME, 'readwrite');
                const store = tx.objectStore(STORE_NAME);
                
                const recordingData = {
                    id: Date.now(),
                    name: `NovaTech Kaydı ${nameSuffix} (${formatTimestamp(Date.now())})`,
                    blob: blob, 
                    mimeType: blob.type,
                    duration: finalDuration
                };

                const request = store.add(recordingData);

                // Transaction'ın tamamlanmasını bekle
                await new Promise((resolve, reject) => {
                    request.onsuccess = () => resolve(recordingData);
                    request.onerror = (e) => reject(new Error(e.target.error));
                    tx.oncomplete = () => resolve(recordingData); 
                    tx.onerror = (e) => reject(new Error(e.target.error));
                });
                
                return recordingData;

            } catch (error) {
                console.error("Kayıt veritabanına kaydedilemedi:", error);
                showCustomModal('Hata', `Kayıt veritabanına kaydedilemedi: ${error.message || 'Bilinmeyen Hata'}`, false);
            }
        }

        async function loadRecordings() {
            try {
                /*
                    Eğer PHP kullanılsaydı, bu noktada PHP'den 
                    JSON formatında kayıt listesi GET edilirdi.
                */
                const db = await openDatabase();
                const tx = db.transaction(STORE_NAME, 'readonly');
                const store = tx.objectStore(STORE_NAME);
                const request = store.getAll();

                return new Promise((resolve, reject) => {
                    request.onsuccess = (event) => {
                        resolve(event.target.result.sort((a, b) => b.id - a.id));
                    };
                    request.onerror = (e) => reject(`Kayıtlar yüklenirken hata oluştu: ${e.target.error}`);
                });
            } catch (error) {
                console.error("Veritabanı yüklenemedi:", error);
                return [];
            }
        }
        
        async function deleteRecording(id) {
            try {
                const db = await openDatabase();
                const tx = db.transaction(STORE_NAME, 'readwrite');
                const store = tx.objectStore(STORE_NAME);
                store.delete(id);
                await new Promise((resolve, reject) => {
                    tx.oncomplete = resolve;
                    tx.onerror = reject;
                });
                displayRecordings();
            } catch (error) {
                showCustomModal('Hata', `Kayıt silinirken hata oluştu: ${error}`, false);
            }
        }


        // --- UI Güncelleme ve Oynatma ---

        async function displayRecordings() {
            const recordings = await loadRecordings();
            recordingsList.innerHTML = ''; 

            if (recordings.length === 0) {
                emptyMessage.classList.remove('hidden');
                recordingsList.appendChild(emptyMessage);
                return;
            }
            emptyMessage.classList.add('hidden');

            recordings.forEach(record => {
                const itemDiv = document.createElement('div');
                itemDiv.className = 'record-item flex items-center justify-between p-4 border-b last:border-b-0 shadow-sm';
                itemDiv.dataset.id = record.id;
                
                itemDiv.onclick = () => openTrimModal(record);

                const infoDiv = document.createElement('div');
                infoDiv.className = 'flex-1 pr-4 min-w-0';
                infoDiv.innerHTML = `
                    <p class="font-semibold text-gray-800 truncate">${record.name}</p>
                    <p class="text-xs text-gray-500">Süre: ${record.duration} | Tarih: ${formatTimestamp(record.id)}</p>
                `;
                
                const actionsDiv = document.createElement('div');
                actionsDiv.className = 'flex items-center space-x-3';

                // Oynatma Butonu
                const playBtn = document.createElement('button');
                playBtn.className = 'text-indigo-500 hover:text-indigo-700 p-1 rounded-full hover:bg-indigo-100 transition';
                playBtn.innerHTML = '<span class="material-symbols-rounded">play_circle</span>';
                playBtn.title = 'Oynat';
                playBtn.onclick = (e) => {
                    e.stopPropagation(); 
                    playRecording(record.blob);
                };

                // Silme Butonu
                const deleteBtn = document.createElement('button');
                deleteBtn.className = 'text-red-500 hover:text-red-700 p-1 rounded-full hover:bg-red-100 transition';
                deleteBtn.innerHTML = '<span class="material-symbols-rounded">delete</span>';
                deleteBtn.title = 'Sil';
                deleteBtn.onclick = (e) => {
                    e.stopPropagation();
                    showCustomModal(
                        'Silme Onayı',
                        `"${record.name}" kaydını silmek istediğinizden emin misiniz? Bu işlem geri alınamaz.`,
                        true,
                        () => deleteRecording(record.id)
                    );
                };

                actionsDiv.appendChild(playBtn);
                actionsDiv.appendChild(deleteBtn);

                itemDiv.appendChild(infoDiv);
                itemDiv.appendChild(actionsDiv);
                recordingsList.appendChild(itemDiv);
            });
        }

        function playRecording(blob) {
            const audioUrl = URL.createObjectURL(blob);
            const audio = new Audio(audioUrl);
            audio.play();

            statusDisplay.textContent = 'Kayıt Oynatılıyor...';
            audio.onended = () => {
                statusDisplay.textContent = 'Oynatma Tamamlandı.';
                setTimeout(() => {
                    checkMicrophoneStatus(true); 
                }, 1000);
            };
            audio.onerror = () => {
                showCustomModal('Oynatma Hatası', 'Ses dosyası oynatılamadı veya bozuk.', false);
                checkMicrophoneStatus(true);
            }
        }


        // --- Ana Kayıt İşlevleri ---

        function startRecording() {
            if (!stream) {
                showCustomModal('Hata', "Mikrofon başlatılamadı. Lütfen izinleri kontrol edin.", false);
                return;
            }
            
            if (mediaRecorder && mediaRecorder.state === 'recording') {
                 stopRecording();
                 return;
            }

            audioChunks = [];
            const mimeType = MediaRecorder.isTypeSupported('audio/mp4') ? 'audio/mp4' : 'audio/webm';
            mediaRecorder = new MediaRecorder(stream, { mimeType: mimeType });
            
            mediaRecorder.ondataavailable = (event) => {
                audioChunks.push(event.data);
            };

            mediaRecorder.onstop = async () => {
                stopTimer();
                if (recordingAnime) recordingAnime.pause();
                recordButton.style.transform = 'scale(1)';
                recordButton.style.boxShadow = '0 10px 15px -3px rgba(239, 68, 68, 0.1), 0 4px 6px -4px rgba(239, 68, 68, 0.1)';


                const audioBlob = new Blob(audioChunks, { type: mimeType }); 
                
                await saveRecording(audioBlob, 'Yeni');
                displayRecordings(); 

                statusDisplay.textContent = 'Kayıt başarıyla tamamlandı ve kaydedildi.';
                recordButton.innerHTML = '<span class="material-symbols-rounded">fiber_manual_record</span>'; // Sadece ikon
                recordButton.title = 'Kaydı Başlat (Space)';
                recordButton.disabled = false;
                stopButton.disabled = true;
            };

            // Kaydı başlat
            mediaRecorder.start();
            startTimer();

            statusDisplay.textContent = 'KAYIT DEVAM EDİYOR...';
            recordButton.innerHTML = '<span class="material-symbols-rounded">mic</span>'; // Sadece ikon
            recordButton.title = 'KAYITTA (Space)';
            recordButton.disabled = true;
            stopButton.disabled = false;
            
            // Anime.js kayıt animasyonu
            recordingAnime = anime({
                targets: recordButton,
                scale: [1, 1.1],
                boxShadow: ['0 10px 15px -3px rgba(239, 68, 68, 0.5)', '0 0 0 0 rgba(239, 68, 68, 0.0)'],
                duration: 1500,
                easing: 'easeInOutQuad',
                direction: 'alternate',
                loop: true
            });
        }

        function stopRecording() {
            if (mediaRecorder && mediaRecorder.state !== 'inactive') {
                mediaRecorder.stop();
            }
        }

        function checkMicrophoneStatus(isRestore = false) {
            if (isRestore) {
                statusDisplay.textContent = 'Hazır. Kaydı başlatabilirsiniz.';
                statusDisplay.classList.replace('bg-red-100', 'bg-green-100');
                statusDisplay.classList.replace('text-red-800', 'text-green-800');
                recordButton.disabled = false;
                return;
            }

            if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
                navigator.mediaDevices.getUserMedia({ audio: true })
                    .then(s => {
                        stream = s;
                        checkMicrophoneStatus(true); 
                    })
                    .catch(err => {
                        console.error('Mikrofon erişimi reddedildi:', err);
                        statusDisplay.textContent = 'HATA: Mikrofon erişimine izin verilmedi.';
                        statusDisplay.classList.replace('bg-indigo-100', 'bg-red-100');
                        statusDisplay.classList.replace('text-indigo-800', 'text-red-800');
                        recordButton.disabled = true;
                        showCustomModal('Mikrofon Gerekli', 'Mikrofona erişim izni gereklidir. Lütfen tarayıcı ayarlarınızı kontrol edin.', false);
                    });
            } else {
                statusDisplay.textContent = 'HATA: Tarayıcınız ses kaydını desteklemiyor.';
                recordButton.disabled = true;
                showCustomModal('Tarayıcı Hatası', 'Tarayıcınız MediaDevices API\'sini (ses kaydını) desteklemiyor.', false);
            }
        }
        
        // --- Ses Kırpma İşlemleri (Web Audio API) ---

        async function openTrimModal(record) {
            activeTrimRecord = record;
            
            const parts = record.duration.split(':');
            let totalSeconds = 0;
            if (parts.length === 3) {
                totalSeconds = parseInt(parts[0]) * 3600 + parseInt(parts[1]) * 60 + parseInt(parts[2]);
            } else if (parts.length === 2) {
                totalSeconds = parseInt(parts[0]) * 60 + parseInt(parts[1]);
            }
            
            if (totalSeconds === 0) {
                 showCustomModal('Hata', 'Kayıt süresi hesaplanamadığı için kırpma yapılamıyor.', false);
                 return;
            }

            trimDurationInfo.textContent = `Toplam Süre: ${formatDuration(totalSeconds)} (${totalSeconds.toFixed(1)} sn)`;
            trimStartInput.value = 0;
            trimEndInput.value = totalSeconds.toFixed(1);
            trimEndInput.max = totalSeconds.toFixed(1);
            trimStartInput.max = totalSeconds.toFixed(1);

            trimSaveButton.onclick = () => processTrim(record, totalSeconds);

            trimModal.classList.remove('hidden');
            trimModal.classList.add('flex');
        }
        
        async function processTrim(record, fullDuration) {
            const startSec = parseFloat(trimStartInput.value);
            const endSec = parseFloat(trimEndInput.value);
            
            if (startSec >= endSec || startSec < 0 || endSec > fullDuration) {
                showCustomModal('Hata', 'Geçersiz zaman aralığı. Başlangıç bitişten önce olmalı ve süre içinde kalmalıdır.', false);
                return;
            }

            trimModal.classList.add('hidden');
            showCustomModal('İşleniyor', 'Ses kırpılıyor, lütfen bekleyin...', false);

            try {
                if (!audioContext) {
                    audioContext = new (window.AudioContext || window.webkitAudioContext)();
                }

                const arrayBuffer = await record.blob.arrayBuffer();
                const audioBuffer = await audioContext.decodeAudioData(arrayBuffer);
                const sampleRate = audioBuffer.sampleRate;
                
                const startSample = Math.floor(startSec * sampleRate);
                const endSample = Math.floor(endSec * sampleRate);
                const durationSample = endSample - startSample;
                
                const newBuffer = audioContext.createBuffer(
                    audioBuffer.numberOfChannels,
                    durationSample,
                    sampleRate
                );
                
                for (let i = 0; i < audioBuffer.numberOfChannels; i++) {
                    const originalChannel = audioBuffer.getChannelData(i);
                    const newChannel = newBuffer.getChannelData(i);
                    newChannel.set(originalChannel.subarray(startSample, endSample));
                }

                const trimmedBlob = audioBufferToWavBlob(newBuffer);

                await saveRecording(trimmedBlob, `Kırpıldı (${startSec.toFixed(1)}-${endSec.toFixed(1)}sn)`);
                
                showCustomModal('Başarılı', 'Kayıt başarıyla kırpıldı ve yeni bir kayıt olarak eklendi.', false);
                displayRecordings();

            } catch (error) {
                console.error("Kırpma Hatası:", error);
                showCustomModal('Kırpma Hatası', `Ses dosyası işlenirken bir hata oluştu: ${error.message}.`, false);
            }
        }
        
        function audioBufferToWavBlob(buffer) {
            const numOfChan = buffer.numberOfChannels;
            const length = buffer.length * numOfChan * 2 + 44; 
            const array = new Uint8Array(length);
            const view = new DataView(array.buffer);
            const channelData = [];
            let offset = 0;
            let i = 0;
            let j = 0;
            
            function writeString(view, offset, string) {
                for (let i = 0; i < string.length; i++) {
                    view.setUint8(offset + i, string.charCodeAt(i));
                }
            }

            writeString(view, offset, 'RIFF'); offset += 4;
            view.setUint32(offset, length - 8, true); offset += 4;
            writeString(view, offset, 'WAVE'); offset += 4;
            writeString(view, offset, 'fmt '); offset += 4;
            view.setUint32(offset, 16, true); offset += 4; 
            view.setUint16(offset, 1, true); offset += 2; 
            view.setUint16(offset, numOfChan, true); offset += 2; 
            view.setUint32(offset, buffer.sampleRate, true); offset += 4; 
            view.setUint32(offset, buffer.sampleRate * 2 * numOfChan, true); offset += 4; 
            view.setUint16(offset, numOfChan * 2, true); offset += 2; 
            view.setUint16(offset, 16, true); offset += 2; 
            writeString(view, offset, 'data'); offset += 4;
            view.setUint32(offset, length - offset, true); offset += 4;

            for (i = 0; i < buffer.numberOfChannels; i++)
                channelData.push(buffer.getChannelData(i));

            while (offset < length) {
                for (i = 0; i < numOfChan; i++) {
                    let sample = Math.max(-1, Math.min(1, channelData[i][j]));
                    sample = (sample < 0 ? sample * 0x8000 : sample * 0x7FFF); 
                    view.setInt16(offset, sample, true); offset += 2;
                }
                j++;
            }

            return new Blob([view], { type: 'audio/wav' });
        }
        
        // --- Klavye Kısayolları ---
        document.addEventListener('keydown', (e) => {
            if (e.code === 'Space' && !customModal.classList.contains('flex') && !trimModal.classList.contains('flex')) {
                if (e.target.tagName !== 'INPUT' && e.target.tagName !== 'TEXTAREA') {
                    e.preventDefault(); 
                    
                    if (recordButton.disabled && stopButton.disabled) {
                        return; 
                    }
                    
                    if (mediaRecorder && mediaRecorder.state === 'recording') {
                        stopRecording();
                    } else if (!recordButton.disabled) {
                        startRecording();
                    }
                }
            }
        });


        // --- Uygulama Başlangıcı ---

        window.onload = () => {
            recordButton.addEventListener('click', startRecording);
            stopButton.addEventListener('click', stopRecording);
            
            checkMicrophoneStatus();
            displayRecordings();
            
            // Giriş Animasyonu
            anime({
                targets: '#app',
                translateY: [20, 0],
                opacity: [0, 1],
                duration: 800,
                easing: 'easeOutQuart',
                delay: 200
            });
        };

    </script>
</body>
</html>
