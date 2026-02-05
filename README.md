<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>森林小憩 - 老師匿名心情空間</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { background-color: #f3f4ed; color: #444; }
        .forest-bg { background: #718355; }
    </style>
</head>
<body class="min-h-screen">

    <nav class="forest-bg text-white p-4 shadow-md text-center">
        <h1 class="text-xl font-bold">🌲 森林小憩</h1>
        <p class="text-xs opacity-80">給老師的匿名心情樹洞</p>
    </nav>

    <main class="max-w-md mx-auto p-4">
        <div class="bg-white rounded-2xl p-6 shadow-sm mb-6 mt-4 border border-stone-200">
            <h2 class="font-bold mb-3">今天的心情...</h2>
            <textarea id="diaryContent" class="w-full p-3 bg-stone-50 rounded-xl border border-stone-100 outline-none focus:ring-2 focus:ring-green-200" rows="3" placeholder="在這裡寫下你的心情..."></textarea>
            <button onclick="postDiary()" class="w-full mt-4 forest-bg text-white py-2 rounded-full font-bold">發布日記</button>
        </div>

        <div id="diaryWall" class="space-y-4">
            <div class="bg-white p-4 rounded-xl shadow-sm border border-stone-100">
                <p class="text-sm text-stone-600 italic">「歡迎來到這裡，這是一個屬於老師的安全空間。」</p>
            </div>
        </div>
    </main>

    <script>
        function postDiary() {
            const content = document.getElementById('diaryContent').value;
            if (!content) { alert("請輸入內容！"); return; }

            const wall = document.getElementById('diaryWall');
            const div = document.createElement('div');
            div.className = "bg-white p-4 rounded-xl shadow-sm border border-stone-100 animate-pulse";
            div.innerHTML = `<p class="text-stone-700">${content}</p><p class="text-xs text-stone-400 mt-2">剛剛發布的匿名日記</p>`;
            
            wall.prepend(div);
            document.getElementById('diaryContent').value = "";
            setTimeout(() => div.classList.remove('animate-pulse'), 1000);
        }
    </script>
</body>
</html>
