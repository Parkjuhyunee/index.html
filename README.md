<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>주현 & 홍길동 결혼식 청첩장</title>

    <!-- 구글 웹폰트 -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@300;500;700&family=Playfair+Display:wght@500;700&display=swap" rel="stylesheet">

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            min-height: 100vh;
            font-family: "Noto Serif KR", system-ui, -apple-system, BlinkMacSystemFont, "Noto Sans KR", sans-serif;
            background: radial-gradient(circle at top, #f8e7de 0, #f5f0ea 40%, #f0e6dd 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 24px 12px;
            color: #333;
        }

        .card {
            width: 100%;
            max-width: 640px;
            background-color: #ffffff;
            border-radius: 20px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.06);
            overflow: hidden;
        }

        /* 상단 사진/배경 */
        .hero {
            position: relative;
            height: 260px;
            background-size: cover;
            background-position: center;
            background-image: url("https://images.pexels.com/photos/3951622/pexels-photo-3951622.jpeg?auto=compress&cs=tinysrgb&w=800"); 
            /* ↑ 여기를 본인 웨딩사진/배경 링크로 바꾸면 됨 */
        }

        .hero-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to bottom, rgba(0,0,0,0.35), rgba(0,0,0,0.55));
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: #fff;
            padding: 24px;
        }

        .hero-label {
            letter-spacing: 0.35em;
            font-size: 0.75rem;
            text-transform: uppercase;
            margin-bottom: 10px;
        }

        .hero-names {
            font-family: "Playfair Display", serif;
            font-size: 2.1rem;
            letter-spacing: 0.08em;
            margin-bottom: 8px;
        }

        .hero-date {
            font-size: 0.95rem;
            opacity: 0.9;
        }

        .hero-sub {
            font-size: 0.85rem;
            opacity: 0.85;
            margin-top: 4px;
        }

        /* 본문 공통 */
        .content {
            padding: 26px 22px 24px;
        }

        section + section {
            border-top: 1px solid #f3ece4;
            padding-top: 20px;
            margin-top: 14px;
        }

        .section-title {
            font-size: 0.82rem;
            letter-spacing: 0.28em;
            text-transform: uppercase;
            color: #b3887c;
            margin-bottom: 10px;
        }

        .intro-text {
            font-size: 0.95rem;
            line-height: 1.8;
            color: #555;
            white-space: pre-line;
        }

        .names-line {
            margin-top: 16px;
            font-size: 0.95rem;
            text-align: center;
        }

        .names-line span {
            display: inline-block;
            margin: 0 6px;
        }

        /* Details */
        .info-row {
            display: flex;
            font-size: 0.9rem;
            margin-top: 6px;
        }
        .info-label {
            width: 70px;
            color: #999;
        }
        .info-value {
            flex: 1;
        }

        /* 지도/오시는길 */
        .map-box {
            margin-top: 8px;
            padding: 12px;
            background-color: #faf6f1;
            border-radius: 12px;
            font-size: 0.88rem;
        }
        .map-name {
            font-weight: 600;
            margin-bottom: 4px;
        }
        .map-placeholder {
            margin-top: 10px;
            height: 170px;
            border-radius: 10px;
            border: 1px dashed #d2b9a6;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            color: #b9a293;
        }

        /* 갤러리 */
        .gallery-grid {
            margin-top: 10px;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 6px;
        }
        .gallery-grid img {
            width: 100%;
            border-radius: 10px;
            height: 90px;
            object-fit: cover;
        }

        /* 계좌 */
        .account-box {
            margin-top: 10px;
            padding: 12px;
            background-color: #f9f3ee;
            border-radius: 12px;
            font-size: 0.88rem;
        }
        .account-item + .account-item {
            margin-top: 8px;
        }

        /* RSVP 버튼 */
        .rsvp-btn {
            margin-top: 12px;
            display: inline-block;
            padding: 9px 18px;
            border-radius: 999px;
            border: none;
            background: linear-gradient(135deg,#e0a7a5,#d59089);
            color: #fff;
            font-size: 0.9rem;
            letter-spacing: 0.05em;
            text-transform: uppercase;
            cursor: pointer;
        }
        .rsvp-btn:active {
            transform: scale(0.97);
        }

        /* 하단 */
        .footer {
            padding: 14px 22px 22px;
            border-top: 1px solid #f3ece4;
            text-align: center;
            font-size: 0.78rem;
            color: #999;
        }
        .copy-link-btn {
            margin-top: 10px;
            padding: 6px 14px;
            font-size: 0.8rem;
            border-radius: 999px;
            border: 1px solid #d8b1aa;
            background-color: #fff;
            cursor: pointer;
        }
        .copy-link-btn:active {
            transform: scale(0.97);
        }
        #copy-msg {
            margin-top: 6px;
            min-height: 1em;
        }

        @media (max-width: 420px) {
            .hero {
                height: 230px;
            }
            .hero-names {
                font-size: 1.9rem;
            }
            .content {
                padding: 22px 18px 20px;
            }
        }
    </style>
</head>
<body>
<div class="card">
    <!-- 상단 히어로 -->
    <header class="hero">
        <div class="hero-overlay">
            <div class="hero-label">WEDDING INVITATION</div>
            <div class="hero-names">주현 & 홍길동</div>
            <div class="hero-date">2025. 10. 18 SAT  2:00 PM</div>
            <div class="hero-sub">서울 ○○웨딩홀 3층 그랜드홀</div>
        </div>
    </header>

    <!-- 본문 내용 -->
    <div class="content">
        <!-- 인사말 -->
        <section>
            <div class="section-title">INVITATION</div>
            <p class="intro-text">
두 사람이 만나
서로의 하루를 나누며
함께 걸어갈 새로운 시작을 맞이하려 합니다.

소중한 분들을 모시고
첫 걸음을 내딛고자 하오니
자리하여 축복해 주신다면
더없이 기쁜 날이 될 것입니다.
            </p>
            <p class="names-line">
                신랑 <span>홍길동</span> · 신부 <span>박주현</span>
            </p>
        </section>

        <!-- 일정/장소 -->
        <section>
            <div class="section-title">DETAILS</div>
            <div class="info-row">
                <div class="info-label">일시</div>
                <div class="info-value">2025년 10월 18일 (토) 오후 2시</div>
            </div>
            <div class="info-row">
                <div class="info-label">장소</div>
                <div class="info-value">서울시 ○○구 ○○로 123, ○○웨딩홀 3층 그랜드홀</div>
            </div>
        </section>

        <!-- 오시는 길 -->
        <section>
            <div class="section-title">LOCATION</div>
            <div class="map-box">
                <div class="map-name">○○웨딩홀 그랜드홀</div>
                <div>서울시 ○○구 ○○로 123</div>
                <div style="margin-top:6px; color:#7f6a5e;">
                    지하철 ○○역 3번 출구 도보 5분<br>
                    주차 2시간 무료 이용 가능합니다.
                </div>
                <div class="map-placeholder">
                    카카오맵/네이버지도 iframe 넣을 자리
                </div>
            </div>
        </section>

        <!-- 사진 갤러리 -->
        <section>
            <div class="section-title">GALLERY</div>
            <div class="gallery-grid">
                <!-- 아래 src 속성을 본인 사진 경로로 바꾸면 됨 -->
                <img src="https://images.pexels.com/photos/302899/pexels-photo-302899.jpeg?auto=compress&cs=tinysrgb&w=400" alt="photo1">
                <img src="https://images.pexels.com/photos/573238/pexels-photo-573238.jpeg?auto=compress&cs=tinysrgb&w=400" alt="photo2">
                <img src="https://images.pexels.com/photos/698899/pexels-photo-698899.jpeg?auto=compress&cs=tinysrgb&w=400" alt="photo3">
            </div>
        </section>

        <!-- 계좌 안내 -->
        <section>
            <div class="section-title">GIFTS</div>
            <p style="font-size:0.88rem; color:#77665c;">
                축하의 마음만으로도 큰 힘이 됩니다.
                조심스러우나 문의가 있으신 분들을 위해 계좌번호를 남깁니다.
            </p>
            <div class="account-box">
                <div class="account-item">
                    <strong>신랑측</strong><br>
                    국민 000000-00-000000 (홍길동)
                </div>
                <div class="account-item">
                    <strong>신부측</strong><br>
                    신한 000-000-000000 (박주현)
                </div>
            </div>
        </section>

        <!-- RSVP -->
        <section>
            <div class="section-title">RSVP</div>
            <p style="font-size:0.88rem; color:#77665c;">
                참석 여부를 미리 알려주시면 식장 안내와 좌석 준비에 큰 도움이 됩니다.
            </p>
            <button class="rsvp-btn" onclick="window.open('https://forms.gle/예시링크', '_blank')">
                참석 여부 전달하기
            </button>
        </section>
    </div>

    <!-- 하단 푸터 -->
    <div class="footer">
        <div>주현 & 홍길동의 결혼식에 함께해 주세요.</div>
        <button class="copy-link-btn" onclick="copyCurrentUrl()">링크 복사하기</button>
        <div id="copy-msg"></div>
    </div>
</div>

<script>
    function copyCurrentUrl() {
        const url = window.location.href;
        if (navigator.clipboard && navigator.clipboard.writeText) {
            navigator.clipboard.writeText(url).then(function () {
                showCopyMessage("링크가 복사되었습니다.");
            }).catch(function () {
                fallbackCopy(url);
            });
        } else {
            fallbackCopy(url);
        }
    }

    function fallbackCopy(text) {
        const temp = document.createElement("textarea");
        temp.value = text;
        document.body.appendChild(temp);
        temp.select();
        try {
            document.execCommand("copy");
            showCopyMessage("링크가 복사되었습니다.");
        } catch (e) {
            showCopyMessage("복사에 실패했습니다. 주소창을 직접 복사해주세요.");
        }
        document.body.removeChild(temp);
    }

    function showCopyMessage(msg) {
        const msgElem = document.getElementById("copy-msg");
        msgElem.textContent = msg;
        setTimeout(() => {
            msgElem.textContent = "";
        }, 2000);
    }
</script>
</body>
</html>
