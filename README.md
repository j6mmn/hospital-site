<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مستشفى روح الحياة الطبي</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', Tahoma, Arial, sans-serif; line-height: 1.6; color: #333; background: #f8f9fa; }
        .top-bar { background: #0d47a1; color: white; padding: 8px 0; text-align: center; font-size: 14px; }
        .top-bar i { margin-left: 5px; }
        header { background: white; box-shadow: 0 2px 10px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000; }
        nav { max-width: 1200px; margin: 0 auto; padding: 15px 20px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; }
        .logo { display: flex; align-items: center; gap: 15px; }
        .logo img { height: 50px; width: 50px; object-fit: contain; border-radius: 8px; }
        .logo h1 { font-size: 20px; color: #0d47a1; }
        .nav-links { display: flex; gap: 20px; list-style: none; flex-wrap: wrap; }
        .nav-links a { color: #333; text-decoration: none; font-weight: 500; transition: color 0.3s; font-size: 15px; }
        .nav-links a:hover { color: #1976d2; }
        .hero { position: relative; height: 550px; background: url('IMG_٢٠٩٢٢_٢٠٢٦٠٦٢٤_805.png') center/cover no-repeat; display: flex; align-items: center; justify-content: center; text-align: center; color: white; }
        .hero::before { content: ''; position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: rgba(13, 71, 161, 0.65); }
        .hero-content { position: relative; z-index: 2; max-width: 800px; padding: 20px; }
        .hero-content img { width: 110px; height: 110px; object-fit: cover; margin-bottom: 20px; background: white; border-radius: 50%; padding: 8px; }
        .hero-content h2 { font-size: 42px; margin-bottom: 15px; }
        .hero-content p { font-size: 20px; margin-bottom: 30px; }
        .btn { display: inline-block; padding: 14px 35px; background: #1976d2; color: white; text-decoration: none; border-radius: 50px; font-weight: bold; transition: all 0.3s; border: none; cursor: pointer; font-size: 16px; }
        .btn:hover { background: #0d47a1; transform: translateY(-2px); box-shadow: 0 5px 15px rgba(25, 118, 210, 0.4); }
        .offers-bar { background: linear-gradient(90deg, #1976d2, #0d47a1); color: white; padding: 12px 0; overflow: hidden; white-space: nowrap; }
        .offers-bar-content { display: inline-block; animation: scroll 25s linear infinite; padding-right: 100%; }
        @keyframes scroll { 0% { transform: translateX(0); } 100% { transform: translateX(100%); } }
        .offers-bar span { margin: 0 40px; font-weight: 500; }
        .container { max-width: 1200px; margin: 0 auto; padding: 60px 20px; }
        .section-title { text-align: center; font-size: 36px; color: #0d47a1; margin-bottom: 15px; }
        .section-subtitle { text-align: center; color: #666; margin-bottom: 50px; font-size: 18px; }
        .about { background: white; border-radius: 15px; padding: 50px; box-shadow: 0 5px 20px rgba(0,0,0,0.08); margin-bottom: 60px; }
        .about-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; margin-top: 40px; }
        .about-card { text-align: center; padding: 30px; background: #f8f9fa; border-radius: 10px; }
        .about-card i { font-size: 48px; color: #1976d2; margin-bottom: 15px; }
        .departments { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 30px; }
        .dept-card { background: white; border-radius: 15px; overflow: hidden; box-shadow: 0 5px 20px rgba(0,0,0,0.08); transition: transform 0.3s; }
        .dept-card:hover { transform: translateY(-10px); }
        .dept-header { background: linear-gradient(135deg, #1976d2, #0d47a1); color: white; padding: 25px; text-align: center; }
        .dept-header i { font-size: 48px; margin-bottom: 10px; }
        .dept-header h3 { font-size: 24px; }
        .dept-body { padding: 25px; }
        .service-list { list-style: none; margin-bottom: 20px; }
        .service-list li { padding: 12px 0; border-bottom: 1px solid #eee; display: flex; justify-content: space-between; align-items: center; }
        .service-list li:last-child { border-bottom: none; }
        .service-list li i { color: #1976d2; margin-left: 10px; }
        .badge { background: #e3f2fd; color: #0d47a1; padding: 4px 12px; border-radius: 20px; font-size: 12px; font-weight: bold; }
        .contact { background: white; border-radius: 15px; padding: 50px; box-shadow: 0 5px 20px rgba(0,0,0,0.08); }
        .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; margin-top: 30px; }
        .contact-item { text-align: center; padding: 20px; }
        .contact-item i { font-size: 40px; color: #1976d2; margin-bottom: 15px; }
        footer { background: #0d47a1; color: white; text-align: center; padding: 30px 20px; margin-top: 60px; }
        .modal { display: none; position: fixed; z-index: 2000; left: 0; top: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.7); }
        .modal-content { background: white; margin: 5% auto; padding: 40px; border-radius: 15px; max-width: 600px; position: relative; }
        .close { position: absolute; left: 20px; top: 15px; font-size: 32px; cursor: pointer; color: #999; }
        .close:hover { color: #333; }
        @media (max-width: 768px) { .hero-content h2 { font-size: 32px; } .hero-content p { font-size: 18px; } .nav-links { gap: 15px; font-size: 14px; } .section-title { font-size: 28px; } .logo h1 { font-size: 18px; } }
    </style>
</head>
<body>
    <div class="top-bar"><i class="fas fa-map-marker-alt"></i> شارع الخليج مجاور البوابة العزيزية</div>
    <header><nav><div class="logo"><img src="FB_IMG_1782320199923.jpg" alt="شعار مستشفى روح الحياة الطبي"><h1>مستشفى روح الحياة الطبي</h1></div><ul class="nav-links"><li><a href="#home">الرئيسية</a></li><li><a href="#about">من نحن</a></li><li><a href="#departments">الأقسام الطبية</a></li><li><a href="#offers">العروض</a></li><li><a href="#contact">تواصل معنا</a></li></ul></nav></header>
    <section class="hero" id="home"><div class="hero-content"><img src="FB_IMG_1782320199923.jpg" alt="شعار"><h2>مستشفى روح الحياة الطبي</h2><p>رعايتكم هي رسالتنا</p><a href="#contact" class="btn">احجز موعدك الآن</a></div></section>
    <div class="offers-bar" id="offers"><div class="offers-bar-content"><span><i class="fas fa-tag"></i> خصم 30% على تنظيف الأسنان</span><span><i class="fas fa-star"></i> عروض البوتوكس والفلر تبدأ من 500,000 د.ع</span><span><i class="fas fa-eye"></i> فحص العيون مجاني كل خميس</span><span><i class="fas fa-heartbeat"></i> باقة فحص شامل للجسم بخصم 25%</span><span><i class="fas fa-bolt"></i> جلسات الليزر الكامل بأسعار مميزة</span></div></div>
    <div class="container">
        <section id="about" class="about"><h2 class="section-title">من نحن</h2><p class="section-subtitle">نقدم أفضل الخدمات الطبية بأحدث التقنيات وأمهر الكوادر</p><p style="text-align: center; font-size: 18px; line-height: 2; color: #555;">تأسس <strong>مستشفى روح الحياة الطبي</strong> ليكون صرحًا طبيًا متكاملاً يخدم أهالي العزيزية وواسط. رؤيتنا أن نكون الخيار الأول للرعاية الصحية المتميزة، ورسالتنا تقديم خدمات طبية آمنة وعالية الجودة باستخدام أحدث الأجهزة وبأيدي نخبة من الأطباء الاستشاريين.</p><div class="about-grid"><div class="about-card"><i class="fas fa-bullseye"></i><h3>رؤيتنا</h3><p>الريادة في الرعاية الصحية المتكاملة</p></div><div class="about-card"><i class="fas fa-hand-holding-heart"></i><h3>رسالتنا</h3><p>صحة المريض أولويتنا القصوى</p></div><div class="about-card"><i class="fas fa-award"></i><h3>قيمنا</h3><p>الجودة، الثقة، الرحمة، الابتكار</p></div></div></section>
        <section id="departments"><h2 class="section-title">الأقسام الطبية</h2><p class="section-subtitle">نخبة من التخصصات الطبية تحت سقف واحد</p><div class="departments">
            <div class="dept-card"><div class="dept-header"><i class="fas fa-tooth"></i><h3>قسم الأسنان</h3></div><div class="dept-body"><ul class="service-list"><li><span><i class="fas fa-check"></i> تقويم الأسنان</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('تقويم الأسنان')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> حشوات تجميلية</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('الحشوات التجميلية')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> تصميم الابتسامة</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('تصميم الابتسامة')">نتائج العلاج</button></li></ul></div></div>
            <div class="dept-card"><div class="dept-header"><i class="fas fa-spa"></i><h3>قسم التجميل</h3></div><div class="dept-body"><ul class="service-list"><li><span><i class="fas fa-check"></i> تنظيف البشرة</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('تنظيف البشرة')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> تجميل الأنف</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('تجميل الأنف')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> الفلر</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('الفلر')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> البوتوكس</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('البوتوكس')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> قص الأجفان</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('قص الأجفان')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> شفط الدهون</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('شفط الدهون')">نتائج العلاج</button></li></ul></div></div>
            <div class="dept-card"><div class="dept-header"><i class="fas fa-bolt"></i><h3>قسم الليزر</h3><span class="badge" style="background: white; color: #0d47a1; margin-top: 8px; display: inline-block;">كادر رجالي ونسائي</span></div><div class="dept-body"><ul class="service-list"><li><span><i class="fas fa-check"></i> ليزر الرقبة</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('ليزر الرقبة')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> ليزر كامل للجسم</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('ليزر كامل')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> ليزر الوجه</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('ليزر الوجه')">نتائج العلاج</button></li></ul></div></div>
            <div class="dept-card"><div class="dept-header"><i class="fas fa-eye"></i><h3>قسم العيون</h3></div><div class="dept-body"><ul class="service-list"><li><span><i class="fas fa-check"></i> فحص النظر</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('فحص النظر')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> عمليات الليزك</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('الليزك')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> علاج الماء الأبيض</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('الماء الأبيض')">نتائج العلاج</button></li></ul></div></div>
            <div class="dept-card"><div class="dept-header"><i class="fas fa-heartbeat"></i><h3>قسم الباطنية</h3></div><div class="dept-body"><ul class="service-list"><li><span><i class="fas fa-check"></i> أمراض القلب</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('أمراض القلب')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> السكري والغدد</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('السكري')">نتائج العلاج</button></li><li><span><i class="fas fa-check"></i> الجهاز الهضمي</span> <button class="btn" style="padding: 6px 15px; font-size: 13px;" onclick="openModal('الجهاز الهضمي')">نتائج العلاج</button></li></ul></div></div>
        </div></section>
        <section id="contact" class="contact"><h2 class="section-title">تواصل معنا</h2><p class="section-subtitle">نحن هنا لخدمتكم على مدار الساعة</p><div class="contact-grid"><div class="contact-item"><i class="fas fa-phone"></i><h3>اتصل بنا</h3><p>07XX XXX XXXX</p><p>طوارئ: 07XX XXX XXXX</p></div><div class="contact-item"><i class="fas fa-map-marker-alt"></i><h3>العنوان</h3><p>شارع الخليج</p><p>مجاور البوابة العزيزية - واسط</p></div><div class="contact-item"><i class="fas fa-clock"></i><h3>أوقات العمل</h3><p>العيادات: 8 صباحًا - 10 مساءً</p><p>الطوارئ: 24 ساعة</p></div></div></section>
    </div>
    <footer><p>&copy; 2026 مستشفى روح الحياة الطبي. جميع الحقوق محفوظة.</p><p style="margin-top: 10px; font-size: 14px;">شارع الخليج مجاور البوابة العزيزية - العزيزية، واسط</p></footer>
    <div id="resultModal" class="modal"><div class="modal-content"><span class="close" onclick="closeModal()">&times;</span><h2 id="modalTitle" style="color: #0d47a1; margin-bottom: 20px;"></h2><p style="color: #666; margin-bottom: 20px;">صور قبل وبعد العلاج - نتائج حقيقية من مرضانا</p><div style="background: #f0f0f0; padding: 60px; text-align: center; border-radius: 10px;"><i class="fas fa-image" style="font-size: 64px; color: #ccc;"></i><p style="margin-top: 15px; color: #999;">يتم إضافة صور النتائج هنا</p></div><button class="btn" style="margin-top: 20px; width: 100%;" onclick="closeModal()">إغلاق</button></div></div>
    <script>
        function openModal(serviceName) { document.getElementById('resultModal').style.display = 'block'; document.getElementById('modalTitle').textContent = 'نتائج علاج: ' + serviceName; }
        function closeModal() { document.getElementById('resultModal').style.display = 'none'; }
        window.onclick = function(event) { if (event.target == document.getElementById('resultModal')) { closeModal(); } }
    </script>
</body>
</html>
