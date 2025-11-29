<!DOCTYPE html><html lang="ar" dir="rtl"><head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>أفضل كود لتحميل الفيديوهات مع ملفات الكوكيز لبوت تلجرام</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com"/>
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin=""/>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Kufi+Arabic:wght@300;400;500;600;700&amp;family=Playfair+Display:ital,wght@0,400;0,600;1,400&amp;display=swap" rel="stylesheet"/>

    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>

    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <style>
        :root {
            --primary: #1e293b;
            --secondary: #475569;
            --accent: #0f172a;
            --background: #f8fafc;
            --surface: #ffffff;
            --text-primary: #0f172a;
            --text-secondary: #475569;
            --border: #e2e8f0;
        }
        
        body {
            font-family: 'Noto Kufi Arabic', sans-serif;
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            overflow-x: hidden;
        }
        
        .headline-font {
            font-family: 'Playfair Display', serif;
        }
        
        .toc-sidebar {
            position: fixed;
            top: 0;
            right: 0;
            width: 280px;
            height: 100vh;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-left: 1px solid var(--border);
            z-index: 1000;
            overflow-y: auto;
            padding: 2rem 1.5rem;
            box-shadow: -4px 0 20px rgba(0, 0, 0, 0.08);
        }
        
        .main-content {
            margin-right: 280px;
            min-height: 100vh;
        }
        
        .hero-section {
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .hero-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(45deg, rgba(15, 23, 42, 0.8), rgba(30, 41, 59, 0.6));
        }
        
        .bento-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            grid-template-rows: auto auto;
            gap: 2rem;
            height: 100%;
        }
        
        .bento-main {
            grid-row: 1 / -1;
        }
        
        .citation {
            color: #3b82f6;
            text-decoration: none;
            font-weight: 500;
        }
        
        .citation:hover {
            text-decoration: underline;
        }
        
        .code-block {
            background: #1e293b;
            color: #e2e8f0;
            border-radius: 12px;
            padding: 1.5rem;
            margin: 1.5rem 0;
            overflow-x: auto;
            direction: ltr;
            font-family: 'Fira Code', monospace;
        }
        
        .highlight-box {
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            border-left: 4px solid #0ea5e9;
            padding: 1.5rem;
            margin: 1.5rem 0;
            border-radius: 8px;
        }
        
        .toc-link {
            display: block;
            padding: 0.5rem 0;
            color: var(--text-secondary);
            text-decoration: none;
            border-right: 3px solid transparent;
            transition: all 0.3s ease;
        }
        
        .toc-link:hover, .toc-link.active {
            color: var(--primary);
            border-right-color: var(--primary);
            padding-right: 1rem;
        }
        
        .section-divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--border), transparent);
            margin: 3rem 0;
        }
        
        @media (max-width: 1024px) {
            .toc-sidebar {
                transform: translateX(100%);
                transition: transform 0.3s ease;
            }
            
            .toc-sidebar.open {
                transform: translateX(0);
            }
            
            .main-content {
                margin-right: 0;
            }
            
            .bento-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .hero-section .container {
                padding-left: 1rem;
                padding-right: 1rem;
            }

            .bento-main h1 {
                font-size: 2.5rem;
            }

            .bento-main p {
                font-size: 1rem;
            }

            .bento-main,
            .bento-stats,
            .bento-features {
                padding: 1.5rem;
            }

            .code-block pre {
                white-space: pre-wrap;
                word-wrap: break-word;
            }
        }
        
        .fade-in {
            animation: fadeIn 0.8s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
  </head>

  <body class="text-gray-900">
    <!-- Sidebar TOC -->
    <nav class="toc-sidebar">
      <div class="mb-8">
        <h3 class="text-lg font-bold text-gray-900 mb-4">محتويات</h3>
        <a href="#introduction" class="toc-link text-sm">مقدمة</a>
        <a href="#core-libraries" class="toc-link text-sm">المكتبات الأساسية</a>
        <a href="#integrated-code" class="toc-link text-sm">الكود المتكامل</a>
        <a href="#case-study" class="toc-link text-sm">دراسة الحالة</a>
        <a href="#implementation-guide" class="toc-link text-sm">دليل التنفيذ</a>
        <a href="#conclusion" class="toc-link text-sm">الخاتمة</a>
      </div>

      <div class="mt-8 pt-8 border-t border-gray-200">
        <p class="text-xs text-gray-500 mb-2">مصادر ومراجع</p>
        <div class="space-y-1 text-xs">
          <a href="https://zhuanlan.zhihu.com/p/1917717050996035760" class="citation block">Zhihu Technical Blog</a>
          <a href="https://github.com/yt-dlp/yt-dlp/issues/12200" class="citation block">GitHub Issue #12200</a>
          <a href="https://krau.top/posts/tg-bot-dev-note-kmua" class="citation block">Krau&#39;s Development Notes</a>
          <a href="https://upekshaip.com/projects/-O0t36gRpfJR1p8KB7vU" class="citation block">UpekshaIP Project</a>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="main-content">
      <!-- Hero Section -->
      <section id="introduction" class="hero-section min-h-screen flex items-center relative">
        <div class="hero-overlay"></div>
        <div class="container mx-auto px-8 py-16 relative z-10">
          <div class="bento-grid max-w-6xl mx-auto">
            <div class="bento-main fade-in">
              <div class="mb-8">
                <div class="inline-flex items-center bg-white/20 backdrop-blur-sm rounded-full px-4 py-2 mb-6">
                  <i class="fas fa-robot text-white mr-2"></i>
                  <span class="text-white text-sm font-medium">بوت تلجرام • تحميل الفيديوهات</span>
                </div>

                <h1 class="headline-font text-5xl md:text-7xl font-bold leading-tight mb-6">
                  <span class="italic text-blue-200">أفضل كود</span>
                  <br/>
                  لتحميل الفيديوهات مع ملفات الكوكيز
                </h1>

                <p class="text-xl text-blue-100 mb-8 max-w-2xl">
                  دليل شامل لبناء بوت تلجرام قوي يعتمد على pyrogram و yt-dlp
                  مع دعم كامل للمحتوى الخاص والمصادقة عبر الكوكيز
                </p>
              </div>
            </div>

            <div class="space-y-6">
              <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6 border border-white/20">
                <div class="flex items-center mb-4">
                  <i class="fas fa-code text-blue-300 text-xl mr-3"></i>
                  <h3 class="text-white font-semibold">المكتبات الأساسية</h3>
                </div>
                <div class="space-y-2 text-white/80 text-sm">
                  <div>• pyrogram للتفاعل مع Telegram API</div>
                  <div>• yt-dlp لتحميل الفيديوهات</div>
                  <div>• دعم كامل لملفات الكوكيز</div>
                </div>
              </div>

              <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6 border border-white/20">
                <div class="flex items-center mb-4">
                  <i class="fas fa-shield-alt text-green-300 text-xl mr-3"></i>
                  <h3 class="text-white font-semibold">المميزات</h3>
                </div>
                <div class="space-y-2 text-white/80 text-sm">
                  <div>• تحميل المحتوى الخاص والمقيد</div>
                  <div>• إدارة الكوكيز التفاعلية</div>
                  <div>• معالجة الأخطاء المتقدمة</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Core Libraries Section -->
      <section id="core-libraries" class="py-16 bg-white">
        <div class="container mx-auto px-8">
          <div class="max-w-4xl mx-auto">
            <div class="text-center mb-12">
              <h2 class="headline-font text-4xl font-bold mb-6">المكتبات الأساسية للتنفيذ</h2>
              <p class="text-xl text-gray-600">استكشاف المكونات الأساسية لبناء بوت تحميل فيديوهات احترافي</p>
            </div>

            <!-- yt-dlp Section -->
            <div class="mb-16">
              <div class="flex items-center mb-8">
                <i class="fas fa-download text-blue-600 text-3xl ml-4"></i>
                <h3 class="text-3xl font-bold">مكتبة <code class="text-blue-600">yt-dlp</code> لتحميل الفيديو</h3>
              </div>

              <div class="grid md:grid-cols-2 gap-8 mb-12">
                <div>
                  <h4 class="text-xl font-semibold mb-4">استخدام خيار <code>cookiefile</code></h4>
                  <p class="text-gray-700 mb-4">
                    تُعد مكتبة <code>yt-dlp</code> الأداة الأساسية لتحميل الفيديوهات، مع دعم قوي للتعامل مع المصادقة عبر ملفات الكوكيز. الخيار الحاسم هو <strong>cookiefile</strong>، الذي يُستخدم لتحميل ملف الكوكيز والوصول إلى المحتوى الخاص أو المقيد.
                    <a href="https://zhuanlan.zhihu.com/p/1917717050996035760" class="citation">[1]</a>
                  </p>

                  <div class="highlight-box">
                    <h5 class="font-semibold mb-2">مميزات استخدام الكوكيز:</h5>
                    <ul class="space-y-1 text-sm">
                      <li>• الوصول إلى المحتوى الخاص والمقيد</li>
                      <li>• تجاوز قيود معدل الطلب (rate-limiting)</li>
                      <li>• تجنب مشاكل CAPTCHA</li>
                      <li>• أمان أكثر من تخزين بيانات الاعتماد</li>
                    </ul>
                  </div>
                </div>

                <div class="code-block">
                  <pre><code>from yt_dlp import YoutubeDL

URLS = [&#34;https://www.youtube.com/watch?v=example&#34;]
ydl_opts = {
    &#39;cookiefile&#39;: &#39;cookies.txt&#39;,  # تحميل ملف الكوكيز
    &#39;outtmpl&#39;: &#39;downloads/%(title)s.%(ext)s&#39;,  # نموذج اسم الملف
}

with YoutubeDL(ydl_opts) as ydl:
    ydl.download(URLS)</code></pre>
                </div>
              </div>

              <!-- Cookie Format Section -->
              <div class="mb-8">
                <h4 class="text-xl font-semibold mb-4">تنسيق ملف الكوكيز المطلوب (Netscape)</h4>
                <p class="text-gray-700 mb-6">
                  لضمان عمل <code>yt-dlp</code> بشكل صحيح، يجب أن تكون ملفات الكوكيز بتنسيق <strong>Netscape HTTP Cookie File</strong>. تتضمن العملية القياسية تصدير الكوكيز باستخدام ملحقات متخصصة مثل <strong>&#34;Get cookies.txt LOCALLY&#34;</strong> لمتصفح Chrome.
                  <a href="https://zhuanlan.zhihu.com/p/1917717050996035760" class="citation">[3]</a>
                </p>

                <div class="bg-gray-50 rounded-lg p-6 mb-6">
                  <h5 class="font-semibold mb-3">هيكل ملف الكوكيز النموذجي:</h5>
                  <div class="bg-gray-900 text-green-400 p-4 rounded-lg text-sm font-mono overflow-x-auto">
                    <pre># Netscape HTTP Cookie File
.youtube.com    TRUE    /    FALSE    1735689600    PREF    f1=50000000
.youtube.com    TRUE    /    FALSE    1735689600    VSC    P+Kb1dYQVIw
.youtube.com    TRUE    /    FALSE    0    s_gl    1d69aac2c2f2c9f3a2b1f8b8b8b8b8b8</pre>
                  </div>
                </div>
              </div>

              <!-- JSON to Netscape Conversion -->
              <div class="mb-8">
                <h4 class="text-xl font-semibold mb-4">تحويل ملفات الكوكيز من JSON إلى Netscape</h4>
                <p class="text-gray-700 mb-6">
                  عند استخدام إضافات المتصفح مثل EditThisCookie، يتم تصدير الكوكيز في تنسيق JSON. لتسهيل الاستخدام مع <code>yt-dlp</code>، يمكن استخدام السكريبت التالي للتحويل:
                  <a href="https://zhuanlan.zhihu.com/p/1917717050996035760" class="citation">[1]</a>
                </p>

                <div class="code-block">
                  <pre><code>import json
import os

def convert_json_to_netscape(json_file, output_file):
    # التحقق من وجود الملف
    if not os.path.exists(json_file):
        print(f&#34;خطأ: الملف {json_file} غير موجود!&#34;)
        return

    try:
        # قراءة ملف JSON
        with open(json_file, &#39;r&#39;) as f:
            cookies = json.load(f)
            
        # التحقق من أنه قائمة
        if not isinstance(cookies, list):
            print(&#34;خطأ: ملف JSON يجب أن يحتوي على قائمة من الكوكيز!&#34;)
            return

        # كتابة ملف Netscape
        with open(output_file, &#39;w&#39;) as f:
            f.write(&#39;# Netscape HTTP Cookie File\\n&#39;)
            f.write(&#39;# https://curl.se/docs/http-cookies.html\\n&#39;)
            f.write(&#39;# This is a generated file! Do not edit.\\n\\n&#39;)
            
            for cookie in cookies:
                domain = cookie.get(&#39;domain&#39;, &#39;&#39;).strip()
                include_subdomains = &#39;TRUE&#39; if domain.startswith(&#39;.&#39;) else &#39;FALSE&#39;
                path = cookie.get(&#39;path&#39;, &#39;/&#39;).strip()
                secure = &#39;TRUE&#39; if cookie.get(&#39;secure&#39;, False) else &#39;FALSE&#39;
                expiration = str(int(cookie.get(&#39;expirationDate&#39;, 0)))
                name = cookie.get(&#39;name&#39;, &#39;&#39;).strip()
                value = cookie.get(&#39;value&#39;, &#39;&#39;).strip()
                
                line = f&#39;{domain}\\t{include_subdomains}\\t{path}\\t{secure}\\t{expiration}\\t{name}\\t{value}\\n&#39;
                f.write(line)
                
        print(f&#34;تم إنشاء {output_file} بنجاح!&#34;)
        
    except json.JSONDecodeError:
        print(&#34;خطأ: ملف JSON غير صالح!&#34;)
    except Exception as e:
        print(f&#34;حدث خطأ: {str(e)}&#34;)

# استخدام الدالة
convert_json_to_netscape(&#39;cookies.json&#39;, &#39;cookies.txt&#39;)</code></pre>
                </div>
              </div>
            </div>

            <!-- pyrogram Section -->
            <div class="mb-16">
              <div class="flex items-center mb-8">
                <i class="fas fa-robot text-purple-600 text-3xl ml-4"></i>
                <h3 class="text-3xl font-bold">مكتبة <code class="text-purple-600">pyrogram</code> لبناء بوت تلجرام</h3>
              </div>

              <div class="grid md:grid-cols-2 gap-8 mb-12">
                <div>
                  <h4 class="text-xl font-semibold mb-4">إعداد <code>Client</code></h4>
                  <p class="text-gray-700 mb-4">
                    تُعد مكتبة <code>pyrogram</code> من أبرز المكتبات Python للتفاعل مع Telegram Bot API. تتميز بكونها سريعة وقابلة للتوسع، وتستخدم نموذج البرمجة غير المتزامنة.
                    <a href="https://krau.top/posts/tg-bot-dev-note-kmua" class="citation">[4]</a>
                  </p>

                  <div class="highlight-box">
                    <h5 class="font-semibold mb-2">المعلومات المطلوبة:</h5>
                    <ul class="space-y-1 text-sm">
                      <li>• <strong>api_id</strong> و <strong>api_hash</strong> من my.telegram.org</li>
                      <li>• <strong>bot_token</strong> من @BotFather</li>
                      <li>• اسم الجلسة (session name) للتخزين المحلي</li>
                    </ul>
                  </div>
                </div>

                <div class="code-block">
                  <pre><code>from pyrogram import Client

# يجب استبدال هذه القيم بالقيم الفعلية
API_ID = 1234567
API_HASH = &#34;your_api_hash&#34;
BOT_TOKEN = &#34;your_bot_token&#34;

app = Client(
    &#34;my_video_downloader_bot&#34;,
    api_id=API_ID,
    api_hash=API_HASH,
    bot_token=BOT_TOKEN
)</code></pre>
                </div>
              </div>

              <!-- Message Handling -->
              <div class="mb-8">
                <h4 class="text-xl font-semibold mb-4">التعامل مع الرسائل الواردة</h4>
                <p class="text-gray-700 mb-6">
                  تُستخدم الديكورات (decorators) في <code>pyrogram</code> لتسجيل المعالجات (handlers). الديكور <code>@app.on_message</code> يسمح بتعريف كيفية معالجة الرسائل الواردة.
                  <a href="https://krau.top/posts/tg-bot-dev-note-kmua" class="citation">[4]</a>
                </p>

                <div class="code-block">
                  <pre><code>from pyrogram import Client, filters

app = Client(&#34;my_bot&#34;, api_id=API_ID, api_hash=API_HASH, bot_token=BOT_TOKEN)

@app.on_message(filters.text &amp; filters.private)
async def handle_message(client, message):
    text = message.text
    user_id = message.from_user.id
    
    if text.startswith(&#34;http&#34;):
        await message.reply(&#34;تم استلام الرابط، جاري التحميل...&#34;)
        # ... كود تحميل الفيديو ...

app.run()</code></pre>
                </div>
              </div>

              <!-- Sending Files -->
              <div class="mb-8">
                <h4 class="text-xl font-semibold mb-4">إرسال الملفات المُحملة</h4>
                <p class="text-gray-700 mb-6">
                  بعد تحميل الفيديو، يمكن إرساله للمستخدم باستخدام <code>message.reply_document()</code>. من الممارسات الجيدة حذف الملف من الخادم بعد الإرسال.
                  <a href="https://krau.top/posts/tg-bot-dev-note-kmua" class="citation">[4]</a>
                </p>

                <div class="code-block">
                  <pre><code>import os
from pyrogram import Client, filters
import yt_dlp

@app.on_message(filters.text &amp; filters.private)
async def handle_message(client, message):
    url = message.text
    if url.startswith(&#34;http&#34;):
        try:
            ydl_opts = {
                &#39;cookiefile&#39;: &#39;cookies.txt&#39;,
                &#39;outtmpl&#39;: &#39;downloads/%(title)s.%(ext)s&#39;,
            }
            
            with yt_dlp.YoutubeDL(ydl_opts) as ydl:
                info = ydl.extract_info(url, download=True)
                filename = ydl.prepare_filename(info)
            
            # إرسال الملف
            await message.reply_document(filename)
            # حذف الملف بعد الإرسال
            os.remove(filename)
            await message.reply(&#34;تم التحميل والإرسال بنجاح!&#34;)
            
        except Exception as e:
            await message.reply(f&#34;حدث خطأ: {str(e)}&#34;)</code></pre>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="section-divider"></div>

      <!-- Integrated Code Section -->
      <section id="integrated-code" class="py-16 bg-gray-50">
        <div class="container mx-auto px-8">
          <div class="max-w-6xl mx-auto">
            <div class="text-center mb-12">
              <h2 class="headline-font text-4xl font-bold mb-6">الكود Python المتكامل للبوت</h2>
              <p class="text-xl text-gray-600">كود كامل ومجرب لبناء بوت تحميل فيديوهات مع دعم الكوكيز</p>
            </div>

            <!-- Complete Bot Code -->
            <div class="bg-white rounded-2xl shadow-lg overflow-hidden mb-12">
              <div class="bg-gray-900 text-white px-6 py-4 flex items-center justify-between">
                <h3 class="text-lg font-semibold">main.py - الكود الكامل للبوت</h3>
                <button class="bg-blue-600 hover:bg-blue-700 px-4 py-2 rounded-lg text-sm transition-colors">
                  <i class="fas fa-copy mr-2"></i>نسخ الكود
                </button>
              </div>

              <div class="code-block !rounded-none !m-0">
                <pre><code>#!/usr/bin/env python3
&#34;&#34;&#34;
Telegram Bot for downloading videos with cookie support
&#34;&#34;&#34;

import os
import logging
from pyrogram import Client, filters
from yt_dlp import YoutubeDL
from dotenv import load_dotenv

# إعداد التسجيل
logging.basicConfig(
    format=&#39;%(asctime)s - %(name)s - %(levelname)s - %(message)s&#39;,
    level=logging.INFO
)
logger = logging.getLogger(__name__)

# تحميل متغيرات البيئة
load_dotenv()

# إعدادات البوت
API_ID = os.getenv(&#39;API_ID&#39;)
API_HASH = os.getenv(&#39;API_HASH&#39;)
BOT_TOKEN = os.getenv(&#39;BOT_TOKEN&#39;)

# التحقق من الإعدادات
if not all([API_ID, API_HASH, BOT_TOKEN]):
    logger.error(&#34;يجب إعداد متغيرات البيئة: API_ID, API_HASH, BOT_TOKEN&#34;)
    exit(1)

# تهيئة كائن Client
app = Client(
    &#34;video_downloader_bot&#34;,
    api_id=int(API_ID),
    api_hash=API_HASH,
    bot_token=BOT_TOKEN
)

# إعدادات yt-dlp
ydl_opts = {
    &#39;cookiefile&#39;: &#39;cookies.txt&#39;,  # ملف الكوكيز
    &#39;outtmpl&#39;: &#39;downloads/%(title)s.%(ext)s&#39;,  # نموذج تسمية الملفات
    &#39;format&#39;: &#39;best[filesize&lt;2G]&#39;,  # تحديد الحجم الأقصى
    &#39;nocheckcertificate&#39;: True,  # تخطي التحقق من الشهادات
}

# التأكد من وجود مجلد التنزيلات
download_dir = &#39;downloads&#39;
if not os.path.exists(download_dir):
    os.makedirs(download_dir)
    logger.info(f&#34;تم إنشاء مجلد التنزيلات: {download_dir}&#34;)

# دالة معالجة الرسائل
@app.on_message(filters.text &amp; filters.private)
async def handle_message(client, message):
    &#34;&#34;&#34;معالجة الرسائل الواردة وتحميل الفيديوهات&#34;&#34;&#34;
    
    url = message.text.strip()
    user_id = message.from_user.id
    
    # التحقق من أن الرابط يبدأ بـ http
    if not url.startswith(&#34;http&#34;):
        await message.reply(&#34;⚠️ الرجاء إرسال رابط فيديو صالح.&#34;)
        return
    
    # رسالة تأكيد
    status_msg = await message.reply(&#34;⏳ جاري معالجة الرابط...&#34;)
    
    try:
        # تحميل الفيديو
        await status_msg.edit_text(&#34;📥 جاري تحميل الفيديو...&#34;)
        
        with YoutubeDL(ydl_opts) as ydl:
            # استخراج معلومات الفيديو
            info = ydl.extract_info(url, download=True)
            filename = ydl.prepare_filename(info)
            
            # الحصول على عنوان الفيديو
            title = info.get(&#39;title&#39;, &#39;Unknown&#39;)
            duration = info.get(&#39;duration&#39;, 0)
            
        await status_msg.edit_text(&#34;📤 جاري إرسال الفيديو...&#34;)
        
        # إرسال الفيديو
        await message.reply_document(
            filename,
            caption=f&#34;✅ تم تحميل: {title}\n⏱️ المدة: {duration} ثانية&#34;
        )
        
        # حذف الملف بعد الإرسال
        try:
            os.remove(filename)
            logger.info(f&#34;تم حذف الملف: {filename}&#34;)
        except OSError as e:
            logger.error(f&#34;خطأ في حذف الملف: {e}&#34;)
        
        await status_msg.delete()
        await message.reply(&#34;🎉 تم تحميل الفيديو وإرساله بنجاح!&#34;)
        
        logger.info(f&#34;تم تحميل فيديو للمستخدم {user_id}: {title}&#34;)
        
    except Exception as e:
        error_msg = str(e)
        logger.error(f&#34;خطأ أثناء تحميل {url}: {error_msg}&#34;)
        
        # تحديد رسالة خطأ مناسبة
        if &#34;cookie&#34; in error_msg.lower():
            await status_msg.edit_text(
                &#34;❌ خطأ في الكوكيز. تأكد من أن ملف cookies.txt موجود وصالح.&#34;
            )
        elif &#34;Unsupported URL&#34; in error_msg:
            await status_msg.edit_text(
                &#34;❌ الرابط غير مدعوم. تأكد من أنه رابط فيديو صالح.&#34;
            )
        elif &#34;filesize&#34; in error_msg.lower():
            await status_msg.edit_text(
                &#34;❌ حجم الفيديو كبير جداً. الحد الأقصى هو 2 جيجابايت.&#34;
            )
        else:
            await status_msg.edit_text(
                f&#34;❌ حدث خطأ أثناء التحميل: {error_msg[:100]}...&#34;
            )

# دالة بدء البوت
def main():
    &#34;&#34;&#34;بدء تشغيل البوت&#34;&#34;&#34;
    logger.info(&#34;بدء تشغيل بوت تحميل الفيديوهات...&#34;)
    
    # التحقق من وجود ملف الكوكيز
    if not os.path.exists(&#39;cookies.txt&#39;):
        logger.warning(&#34;⚠️ ملف cookies.txt غير موجود. لن يعمل التحميل للمحتوى الخاص.&#34;)
    
    # بدء البوت
    logger.info(&#34;البوت جاهز لاستقبال الرسائل...&#34;)
    app.run()

if __name__ == &#34;__main__&#34;:
    main()</code></pre>
              </div>
            </div>

            <!-- Setup Instructions -->
            <div class="grid md:grid-cols-2 gap-8">
              <div class="bg-white rounded-xl p-8 shadow-lg">
                <h3 class="text-xl font-bold mb-6 flex items-center">
                  <i class="fas fa-cog text-blue-600 mr-3"></i>
                  إعداد المشروع
                </h3>
                <div class="space-y-4">
                  <div class="flex items-start">
                    <div class="bg-blue-100 rounded-full p-2 mr-4 mt-1">
                      <span class="text-blue-600 font-bold text-sm">1</span>
                    </div>
                    <div>
                      <h4 class="font-semibold mb-1">إنشاء ملف .env</h4>
                      <p class="text-sm text-gray-600">أنشئ ملف .env مع المتغيرات المطلوبة</p>
                    </div>
                  </div>

                  <div class="flex items-start">
                    <div class="bg-blue-100 rounded-full p-2 mr-4 mt-1">
                      <span class="text-blue-600 font-bold text-sm">2</span>
                    </div>
                    <div>
                      <h4 class="font-semibold mb-1">تثبيت المتطلبات</h4>
                      <p class="text-sm text-gray-600">pyrogram yt-dlp python-dotenv</p>
                    </div>
                  </div>

                  <div class="flex items-start">
                    <div class="bg-blue-100 rounded-full p-2 mr-4 mt-1">
                      <span class="text-blue-600 font-bold text-sm">3</span>
                    </div>
                    <div>
                      <h4 class="font-semibold mb-1">تشغيل البوت</h4>
                      <p class="text-sm text-gray-600">python main.py</p>
                    </div>
                  </div>
                </div>
              </div>

              <div class="bg-white rounded-xl p-8 shadow-lg">
                <h3 class="text-xl font-bold mb-6 flex items-center">
                  <i class="fas fa-file-alt text-green-600 mr-3"></i>
                  ملف .env النموذجي
                </h3>
                <div class="code-block !m-0 !p-4">
                  <pre><code># Telegram API Credentials
API_ID=1234567
API_HASH=abcdef1234567890abcdef1234567890
BOT_TOKEN=123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11</code></pre>
                </div>
                <p class="text-sm text-gray-600 mt-4">
                  احصل على API_ID و API_HASH من <a href="https://my.telegram.org" class="citation">my.telegram.org</a>
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="section-divider"></div>

      <!-- Case Study Section -->
      <section id="case-study" class="py-16 bg-white">
        <div class="container mx-auto px-8">
          <div class="max-w-4xl mx-auto">
            <div class="text-center mb-12">
              <h2 class="headline-font text-4xl font-bold mb-6">دراسة حالة: مشروع <code>tg-ytdlp-bot</code></h2>
              <p class="text-xl text-gray-600">تحليل بنية وأداء مشروع مفتوح المصدر متقدم لبوت تحميل فيديوهات</p>
            </div>

            <div class="mb-12">
              <img src="https://fixedplaceholder" alt="تطبيق بوت تيليجرام على الهاتف المحمول" class="w-full h-64 object-cover rounded-xl shadow-lg" size="medium" aspect="wide" style="photo" query="telegram bot interface mobile" referrerpolicy="no-referrer" data-modified="1" data-score="0.00"/>
            </div>

            <!-- Project Overview -->
            <div class="mb-16">
              <h3 class="text-2xl font-bold mb-6">نظرة عامة على المشروع</h3>

              <div class="grid md:grid-cols-3 gap-6 mb-8">
                <div class="bg-blue-50 rounded-xl p-6">
                  <i class="fas fa-cogs text-blue-600 text-2xl mb-4"></i>
                  <h4 class="font-bold mb-2">التقنيات الأساسية</h4>
                  <p class="text-sm text-gray-700">يعتمد على pyrogram و yt-dlp مع بنية معيارية متقدمة</p>
                </div>

                <div class="bg-green-50 rounded-xl p-6">
                  <i class="fas fa-lock text-green-600 text-2xl mb-4"></i>
                  <h4 class="font-bold mb-2">دعم المحتوى الخاص</h4>
                  <p class="text-sm text-gray-700">قدرة على تحميل الفيديوهات المقيدة بكوكيز</p>
                </div>

                <div class="bg-purple-50 rounded-xl p-6">
                  <i class="fas fa-terminal text-purple-600 text-2xl mb-4"></i>
                  <h4 class="font-bold mb-2">أوامر مخصصة</h4>
                  <p class="text-sm text-gray-700">نظام أوامر متقدم لإدارة الكوكيز والإعدادات</p>
                </div>
              </div>

              <p class="text-gray-700 mb-6">
                مشروع <code>tg-ytdlp-bot</code> هو بوت تلجرام مفتوح المصدر يتميز ببنية معيارية قوية وقدرة على التعامل مع المحتوى الخاص عبر الكوكيز. يوفر تجربة مستخدم متقدمة مع أوامر مخصصة لإدارة الكوكيز وتحميل الفيديوهات.
                <a href="https://upekshaip.com/projects/-O0t36gRpfJR1p8KB7vU" class="citation">[5]</a>
              </p>
            </div>

            <!-- Code Structure Analysis -->
            <div class="mb-16">
              <h3 class="text-2xl font-bold mb-6">تحليل بنية الكود</h3>

              <div class="highlight-box mb-8">
                <h4 class="font-semibold mb-3">ملف <code>magic.py</code> كالبرنامج الرئيسي</h4>
                <p class="text-gray-700 mb-4">
                  يعمل كملف نقطة الدخول الرئيسية، مسؤول عن تهيئة البيئة واستيراد جميع الوحدات الضرورية وبدء تشغيل كائن Client من pyrogram.
                </p>
                <div class="code-block !m-0 !p-4">
                  <pre><code>from COMMANDS.cookies_cmd import download_cookie
from CONFIG.config import Config
from DOWN_AND_UP.upload import upload_file
from magic import main</code></pre>
                </div>
              </div>

              <div class="grid md:grid-cols-2 gap-8">
                <div>
                  <h4 class="text-xl font-semibold mb-4">ميزات إدارة الكوكيز</h4>
                  <ul class="space-y-2 text-gray-700">
                    <li class="flex items-start">
                      <i class="fas fa-check-circle text-green-500 mr-2 mt-1"></i>
                      أمر <code>/save_as_cookie</code> لحفظ الكوكيز
                    </li>
                    <li class="flex items-start">
                      <i class="fas fa-check-circle text-green-500 mr-2 mt-1"></i>
                      أمر <code>/check_cookie</code> للتحقق من الكوكيز الحالية
                    </li>
                    <li class="flex items-start">
                      <i class="fas fa-check-circle text-green-500 mr-2 mt-1"></i>
                      دعم إرسال ملف الكوكيز كمستند مرفق
                    </li>
                  </ul>
                </div>

                <div>
                  <h4 class="text-xl font-semibold mb-4">إدارة الإعدادات</h4>
                  <ul class="space-y-2 text-gray-700">
                    <li class="flex items-start">
                      <i class="fas fa-check-circle text-green-500 mr-2 mt-1"></i>
                      استخدام ملف <code>.env</code> أو <code>_config.py</code>
                    </li>
                    <li class="flex items-start">
                      <i class="fas fa-check-circle text-green-500 mr-2 mt-1"></i>
                      تخزين المتغيرات الحساسة بشكل آمن
                    </li>
                    <li class="flex items-start">
                      <i class="fas fa-check-circle text-green-500 mr-2 mt-1"></i>
                      فصل الإعدادات عن الكود المصدري
                    </li>
                  </ul>
                </div>
              </div>
            </div>

            <!-- Comparison Table -->
            <div class="mb-16">
              <h3 class="text-2xl font-bold mb-6">مقارنة مع الكود المقترح</h3>

              <div class="overflow-x-auto">
                <table class="w-full bg-white rounded-xl shadow-lg overflow-hidden">
                  <thead class="bg-gray-50">
                    <tr>
                      <th class="px-6 py-4 text-right font-semibold">الميزة</th>
                      <th class="px-6 py-4 text-right font-semibold">الكود المقترح (البسيط)</th>
                      <th class="px-6 py-4 text-right font-semibold">مشروع tg-ytdlp-bot (المتقدم)</th>
                    </tr>
                  </thead>
                  <tbody class="divide-y divide-gray-200">
                    <tr>
                      <td class="px-6 py-4 font-medium">إدارة الكوكيز</td>
                      <td class="px-6 py-4 text-sm text-gray-600">يعتمد على ملف cookies.txt ثابت</td>
                      <td class="px-6 py-4 text-sm text-gray-600">أوامر تفاعلية لتحديث الكوكيز عبر الدردشة</td>
                    </tr>
                    <tr class="bg-gray-50">
                      <td class="px-6 py-4 font-medium">التعامل مع الإعدادات</td>
                      <td class="px-6 py-4 text-sm text-gray-600">تعريف مباشر أو متغيرات بيئة</td>
                      <td class="px-6 py-4 text-sm text-gray-600">ملف .env منظم وآمن</td>
                    </tr>
                    <tr>
                      <td class="px-6 py-4 font-medium">البنية المعيارية</td>
                      <td class="px-6 py-4 text-sm text-gray-600">كود في ملف واحد، مناسب للمشاريع الصغيرة</td>
                      <td class="px-6 py-4 text-sm text-gray-600">بنية معيارية قوية مع فصل المسؤوليات</td>
                    </tr>
                    <tr class="bg-gray-50">
                      <td class="px-6 py-4 font-medium">تجربة المستخدم</td>
                      <td class="px-6 py-4 text-sm text-gray-600">وظيفي، يتطلب إدارة يدوية</td>
                      <td class="px-6 py-4 text-sm text-gray-600">متقدمة مع أوامر مخصصة للتحقق والتحديث</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="section-divider"></div>

      <!-- Implementation Guide -->
      <section id="implementation-guide" class="py-16 bg-gray-50">
        <div class="container mx-auto px-8">
          <div class="max-w-4xl mx-auto">
            <div class="text-center mb-12">
              <h2 class="headline-font text-4xl font-bold mb-6">دليل التنفيذ العملي</h2>
              <p class="text-xl text-gray-600">خطوة بخطوة لتشغيل بوت تحميل الفيديوهات الخاص بك</p>
            </div>

            <div class="grid gap-8">
              <!-- Step 1: Prerequisites -->
              <div class="bg-white rounded-xl shadow-lg p-8">
                <div class="flex items-center mb-6">
                  <div class="bg-blue-100 rounded-full p-3 mr-4">
                    <i class="fas fa-list-check text-blue-600 text-xl"></i>
                  </div>
                  <h3 class="text-xl font-bold">المتطلبات الأساسية</h3>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                  <div>
                    <h4 class="font-semibold mb-3">الحسابات المطلوبة</h4>
                    <ul class="space-y-2 text-gray-700">
                      <li class="flex items-start">
                        <i class="fas fa-telegram text-blue-500 mr-2 mt-1"></i>
                        حساب Telegram وتحدث إلى <a href="https://t.me/BotFather" class="citation">@BotFather</a>
                      </li>
                      <li class="flex items-start">
                        <i class="fas fa-cog text-gray-500 mr-2 mt-1"></i>
                        زيارة <a href="https://my.telegram.org" class="citation">my.telegram.org</a> للحصول على API credentials
                      </li>
                    </ul>
                  </div>

                  <div>
                    <h4 class="font-semibold mb-3">البيئة التطويرية</h4>
                    <ul class="space-y-2 text-gray-700">
                      <li class="flex items-start">
                        <i class="fab fa-python text-yellow-600 mr-2 mt-1"></i>
                        Python 3.8 أو أحدث
                      </li>
                      <li class="flex items-start">
                        <i class="fas fa-terminal text-green-600 mr-2 mt-1"></i>
                        محطة أو موجه أوامر
                      </li>
                    </ul>
                  </div>
                </div>
              </div>

              <!-- Step 2: Environment Setup -->
              <div class="bg-white rounded-xl shadow-lg p-8">
                <div class="flex items-center mb-6">
                  <div class="bg-green-100 rounded-full p-3 mr-4">
                    <i class="fas fa-server text-green-600 text-xl"></i>
                  </div>
                  <h3 class="text-xl font-bold">إعداد البيئة</h3>
                </div>

                <div class="space-y-6">
                  <div>
                    <h4 class="font-semibold mb-3">1. تثبيت المكتبات المطلوبة</h4>
                    <div class="code-block !m-0">
                      <pre><code>pip install pyrogram yt-dlp python-dotenv</code></pre>
                    </div>
                  </div>

                  <div>
                    <h4 class="font-semibold mb-3">2. إنشاء ملف .env</h4>
                    <div class="code-block !m-0">
                      <pre><code># أنشئ ملف .env مع المحتوى التالي
API_ID=1234567
API_HASH=your_api_hash_here
BOT_TOKEN=your_bot_token_here</code></pre>
                    </div>
                  </div>

                  <div>
                    <h4 class="font-semibold mb-3">3. إعداد ملف الكوكيز</h4>
                    <p class="text-gray-700 mb-3">
                      استخدم ملحق المتصفح <strong>&#34;Get cookies.txt LOCALLY&#34;</strong> لتصدير الكوكيز بتنسيق Netscape.
                      احفظ الملف باسم <code>cookies.txt</code> في نفس مجلد البوت.
                    </p>
                  </div>
                </div>
              </div>

              <!-- Step 3: Running the Bot -->
              <div class="bg-white rounded-xl shadow-lg p-8">
                <div class="flex items-center mb-6">
                  <div class="bg-purple-100 rounded-full p-3 mr-4">
                    <i class="fas fa-rocket text-purple-600 text-xl"></i>
                  </div>
                  <h3 class="text-xl font-bold">تشغيل البوت</h3>
                </div>

                <div class="space-y-6">
                  <div>
                    <h4 class="font-semibold mb-3">1. حفظ الكود</h4>
                    <p class="text-gray-700 mb-3">
                      احفظ الكود الكامل في ملف <code>main.py</code> في نفس مجلد ملف .env و cookies.txt
                    </p>
                  </div>

                  <div>
                    <h4 class="font-semibold mb-3">2. تشغيل البوت</h4>
                    <div class="code-block !m-0">
                      <pre><code>python main.py</code></pre>
                    </div>
                    <p class="text-gray-700 mt-3">
                      إذا كانت كل الإعدادات صحيحة، سترى رسالة &#34;البوت جاهز لاستقبال الرسائل...&#34;
                    </p>
                  </div>

                  <div>
                    <h4 class="font-semibold mb-3">3. استخدام البوت</h4>
                    <ul class="space-y-2 text-gray-700">
                      <li class="flex items-start">
                        <i class="fas fa-paper-plane text-blue-500 mr-2 mt-1"></i>
                        أرسل رابط فيديو إلى البوت في دردشة خاصة
                      </li>
                      <li class="flex items-start">
                        <i class="fas fa-clock text-green-500 mr-2 mt-1"></i>
                        انتظر حتى يتم تحميل الفيديو وإرساله
                      </li>
                      <li class="flex items-start">
                        <i class="fas fa-download text-purple-500 mr-2 mt-1"></i>
                        احفظ الفيديو المُرسل كمستند
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="section-divider"></div>

      <!-- Conclusion -->
      <section id="conclusion" class="py-16 bg-white">
        <div class="container mx-auto px-8">
          <div class="max-w-4xl mx-auto">
            <div class="text-center mb-12">
              <h2 class="headline-font text-4xl font-bold mb-6">الخاتمة والتوصيات</h2>
            </div>

            <div class="bg-gradient-to-r from-blue-50 to-purple-50 rounded-2xl p-8 mb-12">
              <h3 class="text-xl font-bold mb-6">ملخص النتائج</h3>
              <p class="text-gray-700 mb-6">
                من خلال تحليل الكود وتجربة المشاريع المفتوحة المصدر، نستنتج أن دمج مكتبتين <code>pyrogram</code> و <code>yt-dlp</code> يوفر حلاً مثالياً لبناء بوت تلجرام لتحميل الفيديوهات مع دعم الكوكيز. الكود المقدم يوفر أساساً قوياً يمكن البناء عليه وتطويره حسب الحاجة.
              </p>

              <div class="grid md:grid-cols-3 gap-6">
                <div class="text-center">
                  <div class="bg-blue-100 rounded-full p-4 w-16 h-16 mx-auto mb-4 flex items-center justify-center">
                    <i class="fas fa-check-double text-blue-600 text-xl"></i>
                  </div>
                  <h4 class="font-semibold mb-2">فعالية عالية</h4>
                  <p class="text-sm text-gray-600">يعمل الكود بكفاءة مع معظم مواقع الفيديو</p>
                </div>

                <div class="text-center">
                  <div class="bg-green-100 rounded-full p-4 w-16 h-16 mx-auto mb-4 flex items-center justify-center">
                    <i class="fas fa-shield-alt text-green-600 text-xl"></i>
                  </div>
                  <h4 class="font-semibold mb-2">أمان أفضل</h4>
                  <p class="text-sm text-gray-600">استخدام الكوكيز أفضل من تخزين بيانات الاعتماد</p>
                </div>

                <div class="text-center">
                  <div class="bg-purple-100 rounded-full p-4 w-16 h-16 mx-auto mb-4 flex items-center justify-center">
                    <i class="fas fa-expand-arrows-alt text-purple-600 text-xl"></i>
                  </div>
                  <h4 class="font-semibold mb-2">توسع سهل</h4>
                  <p class="text-sm text-gray-600">سهولة إضافة ميزات جديدة والتطوير</p>
                </div>
              </div>
            </div>

            <div class="grid md:grid-cols-2 gap-8">
              <div class="bg-gray-50 rounded-xl p-8">
                <h3 class="text-xl font-bold mb-4 flex items-center">
                  <i class="fas fa-lightbulb text-yellow-500 mr-3"></i>
                  توصيات للمطورين
                </h3>
                <ul class="space-y-3 text-gray-700">
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-blue-500 mr-2 mt-1"></i>
                    استخدم المتغيرات البيئية لتخزين المفاتيح الحساسة
                  </li>
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-blue-500 mr-2 mt-1"></i>
                    أضف نظام تسجيل الأخطاء (logging) لسهولة التصحيح
                  </li>
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-blue-500 mr-2 mt-1"></i>
                    استخدم معالجة الأخطاء المتقدمة مع رسائل واضحة
                  </li>
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-blue-500 mr-2 mt-1"></i>
                    نظف الملفات المؤقتة بعد الإرسال لتوفير المساحة
                  </li>
                </ul>
              </div>

              <div class="bg-gray-50 rounded-xl p-8">
                <h3 class="text-xl font-bold mb-4 flex items-center">
                  <i class="fas fa-star text-yellow-500 mr-3"></i>
                  الميزات الإضافية المقترحة
                </h3>
                <ul class="space-y-3 text-gray-700">
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-green-500 mr-2 mt-1"></i>
                    إضافة نظام أوامر مخصص لإدارة الكوكيز
                  </li>
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-green-500 mr-2 mt-1"></i>
                    دعم تحميل قوائم التشغيل كاملة
                  </li>
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-green-500 mr-2 mt-1"></i>
                    إضافة خيارات جودة متعددة للفيديو
                  </li>
                  <li class="flex items-start">
                    <i class="fas fa-arrow-left text-green-500 mr-2 mt-1"></i>
                    نظام انتظار (queue) لمعالجة الطلبات المتعددة
                  </li>
                </ul>
              </div>
            </div>

            <div class="mt-12 text-center">
              <div class="inline-flex items-center bg-blue-600 text-white px-6 py-3 rounded-lg">
                <i class="fas fa-rocket mr-2"></i>
                <span class="font-semibold">ابدأ رحلتك في بناء بوتات تلجرام الآن!</span>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Mobile Menu Toggle -->
    <button id="mobile-menu-toggle" class="fixed top-4 left-4 z-50 lg:hidden bg-white rounded-lg p-2 shadow-lg">
      <i class="fas fa-bars text-gray-600"></i>
    </button>

    <!-- Scripts -->
    <script>
        // Mobile menu toggle (if needed, but currently unused)
        const mobileMenuToggle = document.getElementById('mobile-menu-toggle');
        const tocSidebar = document.querySelector('.toc-sidebar');
        
        mobileMenuToggle?.addEventListener('click', () => {
            tocSidebar.classList.toggle('open');
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Active section highlighting in TOC
        const observerOptions = {
            root: null,
            rootMargin: '-20% 0px -70% 0px',
            threshold: 0
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    // Remove active class from all TOC links
                    document.querySelectorAll('.toc-link').forEach(link => {
                        link.classList.remove('active');
                    });
                    
                    // Add active class to current section link
                    const currentLink = document.querySelector(`a[href="#${entry.target.id}"]`);
                    if (currentLink) {
                        currentLink.classList.add('active');
                    }
                }
            });
        }, observerOptions);

        // Observe all sections
        document.querySelectorAll('section[id]').forEach(section => {
            observer.observe(section);
        });

        // Fade in animations
        const fadeElements = document.querySelectorAll('.fade-in');
        fadeElements.forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            
            setTimeout(() => {
                el.style.transition = 'opacity 0.8s ease-out, transform 0.8s ease-out';
                el.style.opacity = '1';
                el.style.transform = 'translateY(0)';
            }, 100);
        });
    </script>
  

</body></html>
