<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>رحلة المبتكر الصغير - التصاميم العلمية التقنية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Cairo', sans-serif; background-color: #f0fdf4; }
        .hero-pattern { background-image: radial-gradient(#10b981 1.5px, transparent 1.5px); background-size: 28px 28px; }
    </style>
</head>
<body class="min-h-screen flex flex-col hero-pattern text-slate-800">

    <!-- شريط العلوى -->
    <header class="bg-emerald-700 text-white shadow-lg sticky top-0 z-50">
        <div class="container mx-auto px-4 py-3 flex flex-wrap justify-between items-center">
            <div class="flex items-center space-x-3 space-x-reverse">
                <span class="bg-white text-emerald-700 font-black text-xl px-3.5 py-1.5 rounded-2xl shadow">٢م (ج)</span>
                <div>
                    <h1 class="font-black text-lg md:text-xl">رحلة المبتكر الصغير 🚀</h1>
                    <p class="text-xs text-emerald-200">المعلمة: أمل عبدالله الشهري | برنامج النشاط الطلابي (العلوم والتقنية)</p>
                </div>
            </div>
            <div class="mt-2 md:mt-0 flex items-center gap-2">
                <span class="bg-emerald-800 px-3 py-1 rounded-full text-xs font-bold border border-emerald-600">تنفيذ حضوري (7 حصص / 315 دقيقة)[span_1](start_span)[span_1](end_span)</span>
            </div>
        </div>
    </header>

    <!-- شريط التنقل بين الحصص (فهرس الرحلة) -->
    <nav class="bg-white shadow-md py-3 px-4 overflow-x-auto border-b border-emerald-100">
        <div class="container mx-auto flex gap-2 min-w-max justify-center" id="lessonTabs">
            <!-- أزرار الحصص -->
        </div>
    </nav>

    <!-- محتوى الحصة الرئيسي -->
    <main class="container mx-auto px-4 py-8 flex-grow max-w-5xl">
        <div id="lessonContent" class="bg-white rounded-3xl shadow-xl p-6 md:p-10 border border-emerald-100 relative overflow-hidden">
            <!-- المحتوى -->
        </div>
    </main>

    <!-- الشخصية الكرتونية المرافقة (رائد) -->
    <div id="characterGuide" class="fixed bottom-4 left-4 z-40 bg-white border-2 border-emerald-500 rounded-3xl shadow-2xl p-4 max-w-xs flex items-start gap-3 transition-all duration-300">
        <div class="bg-emerald-100 text-emerald-700 rounded-2xl w-12 h-12 flex items-center justify-center font-black text-2xl shrink-0 shadow-inner">🤖</div>
        <div>
            <h4 class="font-bold text-sm text-emerald-800">رائد (مرافق الرحلة)</h4>
            <p id="characterSpeech" class="text-xs text-slate-600 mt-1 leading-relaxed">أهلاً بكِ أستاذتي أمل وطالبات الصف الثاني متوسط (ج)! أنا هنا لنخوض معاً أمتع رحلة ابتكار تقني!</p>
        </div>
        <button onclick="toggleCharacter()" class="text-slate-400 hover:text-red-500 text-xs font-bold p-1">✕</button>
    </div>

    <!-- التذييل -->
    <footer class="bg-slate-900 text-slate-400 py-4 text-center text-xs border-t border-slate-800">
        <p>جميع الحقوق محفوظة © 2026 | برنامج التصاميم العلمية التقنية - المملكة العربية السعودية[span_2](start_span)[span_2](end_span)</p>
    </footer>

    <script>
        const lessonsData = [
            {
                id: 1,
                title: "الحصة الأولى: تقديم المفاهيم الأساسية ومهارات STEM",
                duration: "45 دقيقة[span_3](start_span)[span_3](end_span)",
                objective: "أن تتعرف الطالبة على مفهوم التصميم العلمي التقني، وتربط بين العلوم والتقنية والهندسة والرياضيات في حل مشكلة واقعية[span_4](start_span)[span_4](end_span).",
                teacherRole: "عرض فيديوهات تعليمية (أسلوب العلم، إسهامات المسلمين في الوضوء، أشكال الطاقة)، وطرح سؤال التهيئة عن 'هدر المياه[span_5](start_span)'[span_5](end_span).",
                studentRole: "المشاركة في العصف الذهني الحضوري، وتدوين المفاهيم الأساسية (البرمجة الشرطية، الطاقة، الهندسة، التقنية)[span_6](start_span)[span_6](end_span).",
                activity: "نشاط جماعي سريع: مناقشة أسباب الهدر المائي في المدرسة واقتراح حلول أولية بصنبور ذكي يعمل بالحساسات[span_7](start_span)[span_7](end_span).",
                speech: "في المحطة الأولى يا مبدعات، سنكتشف كيف تخدم العلوم والتقنية مجتمعنا بحلول ذكية!"
            },
            {
                id: 2,
                title: "الحصة الثانية: المهمة الأولى «نتعرف إلى المشكلة»",
                duration: "45 دقيقة[span_8](start_span)[span_8](end_span)",
                objective: "أن تحلل كل مجموعة مشكلة بيئية أو اجتماعية واقعية في مجتمعها وتحدد تأثيرها بوضوح تام[span_9](start_span)[span_9](end_span).",
                teacherRole: "تقسيم الطالبات إلى مجموعات عمل حضورية، وتوجيههن لاختيار مشكلة (الهدر المائي، النفايات، الازدحام المروري، ذوي الإعاقة)[span_10](start_span)[span_10](end_span).",
                studentRole: "التفكير الجماعي، اختيار المشكلة الميدانية، وتعبئة وصف بسيط يوضح كيف تؤثر هذه المشكلة على الناس[span_11](start_span)[span_11](end_span).",
                activity: "تعبئة «بطاقة اكتشاف المشكلة» وتحديد التأثير والمجتمع المستهدف بدقة[span_12](start_span)[span_12](end_span).",
                speech: "اخترن المشكلة بعناية في مجموعاتكن، فكل ابتكار عظيم خلفه مشكلة حقيقية حليناها!"
            },
            {
                id: 3,
                title: "الحصة الثالثة: المهمة الثانية «نبحث وندعم فكرتنا بحل تقني»",
                duration: "45 دقيقة[span_13](start_span)[span_13](end_span)",
                objective: "توظيف مصدرين علميين موثوقين على الأقل لجمع معلومات تدعم فكرة المشروع وعرضها في ملخص[span_14](start_span)[span_14](end_span).",
                teacherRole: "توجيه الطالبات للبحث عن أفكار داعمة ومشاريع عالمية مشابهة، وإدارة عصف ذهني تقني[span_15](start_span)[span_15](end_span).",
                studentRole: "البحث عن حلول تقنية ومقارنتها بالتجارب العالمية، وتحديد المبدأ العلمي والكهربائي للفكرة[span_16](start_span)[span_16](end_span).",
                activity: "صياغة فقرة فنية توضح الحل التقني المقترح (مثل حساسات تقطع الماء أو تطبيقات تنظيم المواقف)[span_17](start_span)[span_17](end_span).",
                speech: "البحث العلمي يمنحنا قوة المعرفة! ابحثن عن تجارب الدول الأخرى لتطوير أفكاركن."
            },
            {
                id: 4,
                title: "الحصة الرابعة: المهمة الثالثة «نصمم نموذجًا عمليًا»",
                duration: "45 دقيقة[span_18](start_span)[span_18](end_span)",
                objective: "دمج مفاهيم من البرمجة والعلوم والهندسة في تصميم نموذج عملي تطبيقي (يدوي أو رقمي)[span_19](start_span)[span_19](end_span).",
                teacherRole: "الاستعانة بقناة البرمجة على قناة عين الإثرائية لشرح الأوردوينو، والإشراف على بناء النماذج الهندسية[span_20](start_span)[span_20](end_span).",
                studentRole: "تطبيق الأوامر البرمجية الشرطية (If/Else)، وبناء المجسم الهندسي للنموذج المبدئي[span_21](start_span)[span_21](end_span).",
                activity: "بناء المجسم اليدوي أو الرقمي لنظام الحل التقني (جهاز ري ذكي أو صنبور تلقائي)[span_22](start_span)[span_22](end_span).",
                speech: "حان وقت التطبيق الهندسي والبرمجي الممتع! اربطن بين الأوامر البرمجية والنموذج بمهارة."
            },
            {
                id: 5,
                title: "الحصة الخامسة: المهمة الرابعة «نحسن تصميمنا»",
                duration: "45 دقيقة[span_23](start_span)[span_23](end_span)",
                objective: "اقتراح تحسين واحد على الأقل لتطوير المشروع بناءً على الملاحظة أو التغذية الراجعة (النقد البناء)[span_24](start_span)[span_24](end_span).",
                teacherRole: "تنظيم جلسة مراجعة مبيّنة وتبادل النماذج بين المجموعات لإبداء الملاحظات والتفكير النقدي[span_25](start_span)[span_25](end_span).",
                studentRole: "تقييم نماذج الزميلات، تقديم تغذية راجعة إيجابية، وإجراء تعديلات تحسينية للأمان والمرونة[span_26](start_span)[span_26](end_span).",
                activity: "إضافة تعديلات هندسية مثل زر إيقاف يدوي احتياطي أو تحسين استجابة الحساس[span_27](start_span)[span_27](end_span).",
                speech: "النقد البناء والمراجعة هما سر تميز وتطور المشاريع العظيمة!"
            },
            {
                id: 6,
                title: "الحصة السادسة: المهمة الخامسة والتجربة الداعمة",
                duration: "45 دقيقة[span_28](start_span)[span_28](end_span)",
                objective: "توضيح إسهام المشروع في خدمة المجتمع، وتنفيذ التجربة الداعمة لاختبار مسافة استجابة الحساسات[span_29](start_span)[span_29](end_span).",
                teacherRole: "متابعة كتابة التقرير المجتمعي النهائي، والإشراف على التجربة العملية لاختبار الحساسات[span_30](start_span)[span_30](end_span).",
                studentRole: "كتابة فقرة تأثير المشروع على خدمة البيئة والمجتمع، وتنفيذ تجربة مسافات الحساس وتسجيل النتائج[span_31](start_span)[span_31](end_span).",
                activity: "تجربة داعمة: اختبار مسافة الحساس (5 سم تشغيل / 20 سم لا يعمل) وتسجيل الاستنتاج العلمي[span_32](start_span)[span_32](end_span).",
                speech: "مشاريعكن اليوم ستخدم مجتمعنا الحبيب وتحافظ على مواردنا بكل كفاءة واقتدار!"
            },
            {
                id: 7,
                title: "الحصة السابعة: الختام «معرض الابتكار التقني»",
                duration: "45 دقيقة[span_33](start_span)[span_33](end_span)",
                objective: "عرض نتائج التجربة أو المشروع في شكل منظم باستخدام الجداول والرسوم التوضيحية في معرض صفي[span_34](start_span)[span_34](end_span).",
                teacherRole: "تنظيم وإقامة المعرض الصفي الحضوري «ابتكري يخدم مجتمعي»، وتطبيق أدوات التقويم التكويني[span_35](start_span)[span_35](end_span).",
                studentRole: "عرض الابتكارات، شرح الفكرة بثقة تامة أمام الحاضرين واللجنة، والإجابة عن الأسئلة[span_36](start_span)[span_36](end_span).",
                activity: "إقامة معرض الابتكار التقني الصفي واستكمال بطاقات تقويم المشاريع والملاحظة[span_37](start_span)[span_37](end_span).",
                speech: "وصلنا محطة الختام بكل فخر وسعادة! أنتن اليوم مهندسات ومبتكرات المستقبل الرائعات!"
            }
        ];

        let currentLessonId = 1;

        function renderTabs() {
            const tabsContainer = document.getElementById('lessonTabs');
            tabsContainer.innerHTML = '';
            lessonsData.forEach(lesson => {
                const btn = document.createElement('button');
                btn.className = `px-4 py-2.5 rounded-2xl font-bold text-sm transition-all shadow-sm ${currentLessonId === lesson.id ? 'bg-emerald-600 text-white shadow-md scale-105' : 'bg-slate-100 text-slate-600 hover:bg-emerald-50'}`;
                btn.innerText = `حصة ${lesson.id}`;
                btn.onclick = () => switchLesson(lesson.id);
                tabsContainer.appendChild(btn);
            });
        }

        function switchLesson(id) {
            currentLessonId = id;
            renderTabs();
            renderContent();
        }

        function renderContent() {
            const lesson = lessonsData.find(l => l.id === currentLessonId);
            const contentDiv = document.getElementById('lessonContent');
            
            contentDiv.innerHTML = `
                <div class="flex flex-wrap justify-between items-center mb-6 border-b pb-4">
                    <div>
                        <span class="bg-emerald-100 text-emerald-800 text-xs font-bold px-3.5 py-1.5 rounded-full">المدة: ${lesson.duration}</span>
                        <h2 class="text-2xl font-black text-emerald-900 mt-2">${lesson.title}</h2>
                    </div>
                    <div class="text-xs text-slate-500 font-bold bg-slate-50 px-3.5 py-2 rounded-2xl border">
                        الصف: الثاني متوسط (ج) 🏫
                    </div>
                </div>

                <div class="space-y-6">
                    <div class="bg-emerald-50/70 border-r-4 border-emerald-600 p-4 rounded-2xl">
                        <h3 class="font-bold text-emerald-900 text-sm mb-1">🎯 الهدف الرئيسي للحصة:</h3>
                        <p class="text-slate-700 text-sm leading-relaxed">${lesson.objective}</p>
                    </div>

                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="bg-blue-50/50 border border-blue-100 p-4 rounded-2xl">
                            <h4 class="font-bold text-blue-900 text-sm mb-2 flex items-center gap-2">👩‍🏫 دور المعلمة (أمل الشهري):</h4>
                            <p class="text-slate-700 text-xs leading-relaxed">${lesson.teacherRole}</p>
                        </div>
                        <div class="bg-amber-50/50 border border-amber-100 p-4 rounded-2xl">
                            <h4 class="font-bold text-amber-900 text-sm mb-2 flex items-center gap-2">👩‍‍🎓 مطلوب من الطالبات:</h4>
                            <p class="text-slate-700 text-xs leading-relaxed">${lesson.studentRole}</p>
                        </div>
                    </div>

                    <div class="bg-slate-50 border border-slate-200 p-4 rounded-2xl">
                        <h4 class="font-bold text-slate-900 text-sm mb-2">⭐ النشاط العملي والتطبيقي الحضوري:</h4>
                        <p class="text-slate-700 text-sm font-semibold">${lesson.activity}</p>
                    </div>

                    <div class="flex justify-between items-center pt-6 border-t">
                        <button onclick="changeLesson(-1)" ${currentLessonId === 1 ? 'disabled class="opacity-40 cursor-not-allowed bg-slate-200 text-slate-500 px-4 py-2 rounded-xl text-xs font-bold"' : 'class="bg-slate-200 hover:bg-slate-300 text-slate-700 px-4 py-2 rounded-xl text-xs font-bold transition"'}>
                            ← الحصة السابقة
                        </button>
                        <span class="text-xs font-bold text-emerald-700">حصة ${currentLessonId} من 7</span>
                        <button onclick="changeLesson(1)" ${currentLessonId === 7 ? 'disabled class="opacity-40 cursor-not-allowed bg-emerald-200 text-emerald-500 px-4 py-2 rounded-xl text-xs font-bold"' : 'class="bg-emerald-600 hover:bg-emerald-700 text-white px-4 py-2 rounded-xl text-xs font-bold transition shadow"'}>
                            الحصة التالية →
                        </button>
                    </div>
                </div>
            `;

            document.getElementById('characterSpeech').innerText = lesson.speech;
        }

        function changeLesson(direction) {
            const newId = currentLessonId + direction;
            if (newId >= 1 && newId <= 7) {
                switchLesson(newId);
            }
        }

        function toggleCharacter() {
            const guide = document.getElementById('characterGuide');
            guide.classList.toggle('hidden');
        }

        // تشغيل العرض أول مرة
        renderTabs();
        renderContent();
    </script>
</body>
</html>
