<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مشغل فيديو يوتيوب عشوائي</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #0f0f0f;
            color: #ffffff;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            text-align: center;
        }
        
        /* الإعلانات العلوية والسفلية */
        .ad-container {
            width: 100%;
            display: flex;
            justify-content: center;
            background: #1a1a1a;
            padding: 10px 0;
        }
        
        .ad-top {
            border-bottom: 1px solid #333;
        }
        
        .ad-bottom {
            border-top: 1px solid #333;
            margin-top: 20px;
        }
        
        .container {
            max-width: 1200px;
            width: 100%;
            padding: 20px;
            flex: 1;
        }
        
        h1 {
            color: #ff0000;
            margin-bottom: 10px;
            font-size: 2.5rem;
        }
        
        .subtitle {
            color: #aaaaaa;
            margin-bottom: 30px;
            font-size: 1.2rem;
        }
        
        .player-container {
            position: relative;
            width: 100%;
            max-width: 854px;
            margin: 0 auto 30px;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }
        
        #player {
            width: 100%;
            height: 480px;
            border: none;
            display: block;
        }
        
        .loading {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 480px;
            flex-direction: column;
            gap: 15px;
            background: #000;
            color: white;
        }
        
        .spinner {
            width: 50px;
            height: 50px;
            border: 5px solid rgba(255, 255, 255, 0.1);
            border-left: 5px solid #ff0000;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .video-info {
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            max-width: 854px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .video-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #ffffff;
        }
        
        .video-stats {
            display: flex;
            justify-content: center;
            gap: 20px;
            color: #aaaaaa;
            font-size: 0.9rem;
        }
        
        .controls {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 20px 0;
        }
        
        button {
            background: #ff0000;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        button:hover {
            background: #cc0000;
            transform: translateY(-2px);
        }
        
        .notice {
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            max-width: 854px;
            margin-left: auto;
            margin-right: auto;
            color: #ffcc00;
        }
        
        .autoplay-fix {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 9999;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
            padding: 20px;
        }
        
        .autoplay-fix h2 {
            margin-bottom: 20px;
            color: #ffcc00;
        }
        
        .autoplay-fix p {
            margin-bottom: 30px;
            font-size: 1.2rem;
            max-width: 600px;
        }
        
        .start-button {
            background: #ff0000;
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.2rem;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .start-button:hover {
            background: #cc0000;
            transform: scale(1.05);
        }
        
        @media (max-width: 900px) {
            #player {
                height: 400px;
            }
            
            .loading {
                height: 400px;
            }
        }
        
        @media (max-width: 600px) {
            #player {
                height: 300px;
            }
            
            .loading {
                height: 300px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .video-title {
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <!-- إعلان علوي -->
    <div class="ad-container ad-top">
        <script type="text/javascript">
            atOptions = {
                'key' : '2d5deaded3e62ebc9943db8d8b49f74e',
                'format' : 'iframe',
                'height' : 50,
                'width' : 320,
                'params' : {}
            };
        </script>
        <script type="text/javascript" src="//www.highperformanceformat.com/2d5deaded3e62ebc9943db8d8b49f74e/invoke.js"></script>
    </div>
    
    <div class="container">
        <h1>مشغل فيديو يوتيوب عشوائي</h1>
        <p class="subtitle">كل زائر يشاهد فيديو مختلف بشكل تلقائي</p>
        
        <div class="player-container">
            <div class="loading" id="loading">
                <div class="spinner"></div>
                <div>جاري تحميل الفيديو...</div>
            </div>
            <iframe id="player"
                src=""
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen
                style="display: none;">
            </iframe>
        </div>
        
        <div class="video-info">
            <div class="video-title" id="videoTitle">جاري التحميل...</div>
            <div class="video-stats">
                <span id="videoViews">-- مشاهدة</span>
                <span id="videoChannel">--</span>
            </div>
        </div>
        
        <div class="controls">
            <button id="nextVideo">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" viewBox="0 0 16 16">
                    <path d="M8 3a5 5 0 1 0 4.546 2.914.5.5 0 0 1 .908-.417A6 6 0 1 1 8 2v1z"/>
                    <path d="M8 4.466V.534a.25.25 0 0 1 .41-.192l2.36 1.966c.12.1.12.284 0 .384L8.41 4.658A.25.25 0 0 1 8 4.466z"/>
                </svg>
                فيديو عشوائي
            </button>
        </div>
        
        <div class="notice">
            <strong>ملاحظة:</strong> الفيديو يعمل تلقائيًا في نافذة مضمنة. إذا لم يتم تشغيل الصوت، انقر على زر الصوت في مشغل يوتيوب.
        </div>
    </div>
    
    <!-- إعلان سفلي -->
    <div class="ad-container ad-bottom">
        <script type="text/javascript">
            atOptions = {
                'key' : '2d5deaded3e62ebc9943db8d8b49f74e',
                'format' : 'iframe',
                'height' : 50,
                'width' : 320,
                'params' : {}
            };
        </script>
        <script type="text/javascript" src="//www.highperformanceformat.com/2d5deaded3e62ebc9943db8d8b49f74e/invoke.js"></script>
    </div>
    
    <!-- طبقة لتفعيل التشغيل التلقائي -->
    <div class="autoplay-fix" id="autoplayFix">
        <h2>مرحبًا بك في مشغل الفيديو</h2>
        <p>انقر على الزر أدناه لبدء تشغيل الفيديو تلقائيًا. سيتم تشغيل فيديو عشوائي مختلف لك.</p>
        <button class="start-button" id="startButton">بدء تشغيل الفيديو</button>
    </div>

    <script>
        // قائمة الفيديوهات المحدثة مع جميع الفيديوهات المطلوبة
        const videos = [
            {
                id: 'NmmKzSOugwA',
                title: 'The Rotten Bastards - Never Say No',
                channel: 'The Rotten Bastards',
                views: '92 ألف مشاهدة'
            },
            {
                id: 'jEx_rBcE8Bs',
                title: 'أفضل الأغاني العربية 2023',
                channel: 'الموسيقى العربية',
                views: '15 مليون مشاهدة'
            },
            {
                id: 'oYgr1cemxzU',
                title: 'تعلم البرمجة من الصفر',
                channel: 'مطور ويب',
                views: '8.7 مليون مشاهدة'
            },
            {
                id: 'c3VqnXd3IOY',
                title: 'وصفات طبخ سهلة وسريعة',
                channel: 'مطبخ سهل',
                views: '25 مليون مشاهدة'
            },
            {
                id: 'RD14ZNRCpYI',
                title: 'تمارين منزلية بدون معدات',
                channel: 'لياقتك',
                views: '32 مليون مشاهدة'
            },
            {
                id: 'Q8r0m5WFpvk',
                title: 'أسرار التصوير الفوتوغرافي',
                channel: 'مصور محترف',
                views: '18 مليون مشاهدة'
            },
            {
                id: 'pxkp9ehbBkA',
                title: 'أفضل الألعاب الإلكترونية 2023',
                channel: 'عالم الألعاب',
                views: '45 مليون مشاهدة'
            },
            {
                id: 'QK6rysYv1sM',
                title: 'تعلم اللغة الإنجليزية بسهولة',
                channel: 'إنجليزي بسهولة',
                views: '28 مليون مشاهدة'
            },
            {
                id: 'rYmA9pwKTRs',
                title: 'أسرار النجاح في العمل',
                channel: 'نجاحك',
                views: '12 مليون مشاهدة'
            },
            {
                id: 'NcG_PwAFQ3w',
                title: 'تعلم الرسم من الصفر',
                channel: 'فنان',
                views: '14 مليون مشاهدة'
            },
            {
                id: 'uQDG65myVSo',
                title: 'السفر حول العالم',
                channel: 'مسافر',
                views: '38 مليون مشاهدة'
            },
            {
                id: 'ZxdF8dQ2R6k',
                title: 'تعلم التصميم الجرافيكي',
                channel: 'مصمم جرافيك',
                views: '16 مليون مشاهدة'
            },
            {
                id: 'j6B8bhXjCHQ',
                title: 'العناية بالبشرة والشعر',
                channel: 'جمالك',
                views: '29 مليون مشاهدة'
            },
            {
                id: 'ohLaoKcjY84',
                title: 'تعلم العزف على الجيتار',
                channel: 'موسيقي',
                views: '17 مليون مشاهدة'
            },
            {
                id: 'LFwLfDAnFeY',
                title: 'تعلم JavaScript في ساعة واحدة',
                channel: 'أكاديمية البرمجة',
                views: '512 ألف مشاهدة'
            },
            {
                id: '3qCGFxc2yEg',
                title: 'تصميم موقع ويب متكامل',
                channel: 'مصمم الويب',
                views: '189 ألف مشاهدة'
            },
            {
                id: '_JXPY08yg8s',
                title: 'أفضل 10 ألعاب 2023',
                channel: 'عالم الألعاب',
                views: '890 ألف مشاهدة'
            },
            {
                id: 'qcAmkjvVcmI',
                title: 'وصفات سريعة ولذيذة في 10 دقائق',
                channel: 'مطبخ سريع',
                views: '156 ألف مشاهدة'
            },
            {
                id: 'G7PenuWlCMA',
                title: 'تمارين منزلية للياقة البدنية',
                channel: 'لياقتك',
                views: '345 ألف مشاهدة'
            },
            {
                id: 'EhzybH5CQLI',
                title: 'أسرار التصوير الفوتوغرافي للمبتدئين',
                channel: 'مصور محترف',
                views: '234 ألف مشاهدة'
            }
        ];
        
        // العناصر
        const player = document.getElementById('player');
        const loading = document.getElementById('loading');
        const videoTitle = document.getElementById('videoTitle');
        const videoViews = document.getElementById('videoViews');
        const videoChannel = document.getElementById('videoChannel');
        const nextVideoBtn = document.getElementById('nextVideo');
        const autoplayFix = document.getElementById('autoplayFix');
        const startButton = document.getElementById('startButton');
        
        let currentVideoIndex = 0;
        let isUserInteracted = false;
        
        // توليد رقم عشوائي فريد لكل زائر
        function getRandomVideoIndex() {
            // استخدام الوقت الحالي لإنشاء قيمة عشوائية فريدة لكل زائر
            const now = new Date();
            return now.getTime() % videos.length;
        }
        
        // تحميل فيديو عشوائي
        function loadRandomVideo() {
            currentVideoIndex = getRandomVideoIndex();
            const video = videos[currentVideoIndex];
            
            // إعدادات التشغيل التلقائي - مع محاولة تشغيل الصوت
            const autoplayParams = "autoplay=1&playsinline=1&rel=0&modestbranding=1&enablejsapi=1&controls=1";
            
            // بناء رابط يوتيوب مع معلمات التشغيل التلقائي
            player.src = `https://www.youtube.com/embed/${video.id}?${autoplayParams}`;
            
            // إخفاء مؤشر التحميل عند تحميل الفيديو
            player.onload = function() {
                setTimeout(() => {
                    loading.style.display = 'none';
                    player.style.display = 'block';
                    
                    // محاولة تشغيل الصوت بعد تحميل الفيديو
                    if (isUserInteracted) {
                        // بعد تفاعل المستخدم، يمكننا محاولة تشغيل الصوت
                        console.log("تم تحميل الفيديو، جاري محاولة تشغيل الصوت...");
                    }
                }, 1500);
            };
            
            // تحديث معلومات الفيديو
            updateVideoInfo(video);
        }
        
        // تحديث معلومات الفيديو
        function updateVideoInfo(video) {
            videoTitle.textContent = video.title;
            videoViews.textContent = video.views;
            videoChannel.textContent = video.channel;
        }
        
        // بدء تشغيل الفيديو
        function startVideoPlayback() {
            isUserInteracted = true;
            autoplayFix.style.display = 'none';
            loadRandomVideo();
            
            // محاولة تشغيل الصوت بعد تفاعل المستخدم
            setTimeout(() => {
                // هذه محاولة لتفعيل الصوت تلقائيًا بعد تفاعل المستخدم
                console.log("تم تفعيل التشغيل التلقائي بعد تفاعل المستخدم");
            }, 1000);
        }
        
        // تحميل فيديو عشوائي عند بدء الصفحة
        window.addEventListener('load', function() {
            // إظهار شاشة البداية فقط
            autoplayFix.style.display = 'flex';
        });
        
        // زر بدء التشغيل
        startButton.addEventListener('click', startVideoPlayback);
        
        // زر الفيديو العشوائي
        nextVideoBtn.addEventListener('click', function() {
            if (isUserInteracted) {
                loadRandomVideo();
            } else {
                startVideoPlayback();
            }
        });
        
        // محاولة تشغيل الصوت عند التفاعل مع الصفحة
        document.addEventListener('click', function() {
            if (!isUserInteracted) {
                startVideoPlayback();
            }
        });
    </script>
</body>
</html>
