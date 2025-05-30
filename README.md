<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Học HTML, CSS & JavaScript - Tiếng Việt</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #4895ef;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --warning: #f72585;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #1a2a6c);
            color: var(--light);
            line-height: 1.6;
            min-height: 100vh;
            padding-bottom: 60px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            padding: 40px 20px;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 15px;
            margin: 20px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        header h1 {
            font-size: 2.8rem;
            margin-bottom: 15px;
            background: linear-gradient(to right, #4facfe, #00f2fe);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
        }
        
        header p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 25px;
            color: #e9ecef;
        }
        
        .language-tabs {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
            flex-wrap: wrap;
        }
        
        .tab {
            padding: 15px 30px;
            background: rgba(67, 97, 238, 0.2);
            border: 2px solid var(--accent);
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .tab:hover {
            background: rgba(67, 97, 238, 0.4);
            transform: translateY(-3px);
        }
        
        .tab.active {
            background: var(--primary);
            border-color: var(--success);
            box-shadow: 0 0 15px rgba(76, 201, 240, 0.5);
        }
        
        .content-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            margin-top: 20px;
        }
        
        @media (max-width: 900px) {
            .content-container {
                grid-template-columns: 1fr;
            }
        }
        
        .content-box {
            background: rgba(25, 25, 35, 0.85);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(76, 201, 240, 0.3);
            transition: transform 0.3s ease;
        }
        
        .content-box:hover {
            transform: translateY(-5px);
        }
        
        .content-box h2 {
            color: var(--success);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--accent);
            font-size: 1.8rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .content-box h3 {
            color: var(--accent);
            margin: 20px 0 10px;
            font-size: 1.4rem;
        }
        
        .content-box p {
            margin-bottom: 15px;
            color: #e9ecef;
        }
        
        .example {
            background: rgba(10, 15, 30, 0.7);
            border-left: 4px solid var(--success);
            padding: 15px;
            margin: 20px 0;
            border-radius: 0 8px 8px 0;
            overflow-x: auto;
        }
        
        .example-title {
            color: var(--success);
            font-weight: 600;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .code {
            font-family: 'Courier New', monospace;
            background: rgba(0, 0, 0, 0.4);
            padding: 15px;
            border-radius: 8px;
            overflow-x: auto;
            margin: 15px 0;
            color: #f8f9fa;
            line-height: 1.8;
        }
        
        .code-comment {
            color: #6c757d;
        }
        
        .code-tag {
            color: #e06c75;
        }
        
        .code-attr {
            color: #d19a66;
        }
        
        .code-value {
            color: #98c379;
        }
        
        .practice-area {
            background: rgba(15, 20, 40, 0.9);
            padding: 25px;
            border-radius: 15px;
            margin-top: 30px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
        }
        
        .practice-area h2 {
            text-align: center;
            margin-bottom: 25px;
            color: var(--accent);
            font-size: 2rem;
        }
        
        .editor-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            height: 400px;
        }
        
        @media (max-width: 768px) {
            .editor-container {
                grid-template-columns: 1fr;
                height: auto;
            }
        }
        
        .code-editor {
            background: #1e1e1e;
            border-radius: 8px;
            padding: 15px;
            font-family: 'Courier New', monospace;
            color: #d4d4d4;
            overflow: auto;
            line-height: 1.5;
        }
        
        .preview {
            background: white;
            border-radius: 8px;
            padding: 20px;
            overflow: auto;
            color: #333;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            margin: 10px 5px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .btn-run {
            background: var(--success);
            margin-top: 15px;
        }
        
        .btn-run:hover {
            background: #3aa9d4;
        }
        
        .resources {
            margin-top: 40px;
            background: rgba(25, 25, 35, 0.85);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
        }
        
        .resources h2 {
            text-align: center;
            margin-bottom: 25px;
            color: var(--accent);
            font-size: 2rem;
        }
        
        .resource-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .resource-card {
            background: rgba(15, 20, 40, 0.7);
            border-radius: 10px;
            padding: 20px;
            transition: all 0.3s ease;
            border: 1px solid rgba(76, 201, 240, 0.2);
        }
        
        .resource-card:hover {
            transform: translateY(-5px);
            border-color: var(--success);
            box-shadow: 0 5px 15px rgba(76, 201, 240, 0.2);
        }
        
        .resource-card h3 {
            color: var(--accent);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .resource-card a {
            color: var(--success);
            text-decoration: none;
            display: block;
            margin: 8px 0;
            transition: color 0.2s;
        }
        
        .resource-card a:hover {
            color: #3aa9d4;
            text-decoration: underline;
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: #e9ecef;
            font-size: 0.9rem;
        }
        
        .highlight {
            color: var(--success);
            font-weight: bold;
        }
        
        .roadmap {
            margin: 30px 0;
            padding: 20px;
            background: rgba(15, 20, 40, 0.7);
            border-radius: 15px;
        }
        
        .roadmap h2 {
            text-align: center;
            margin-bottom: 25px;
            color: var(--accent);
            font-size: 1.8rem;
        }
        
        .roadmap-steps {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }
        
        .step {
            background: rgba(67, 97, 238, 0.15);
            border: 1px solid var(--accent);
            border-radius: 10px;
            padding: 20px;
            width: 180px;
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .step:hover {
            transform: scale(1.05);
            background: rgba(67, 97, 238, 0.25);
        }
        
        .step i {
            font-size: 2.5rem;
            color: var(--success);
            margin-bottom: 15px;
        }
        
        .step h3 {
            color: white;
            font-size: 1.1rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-code"></i> Học Lập Trình Web Cơ Bản</h1>
            <p>Trang web này sẽ hướng dẫn bạn từng bước học HTML, CSS và JavaScript bằng tiếng Việt dễ hiểu, kèm ví dụ thực hành trực quan</p>
            <div class="language-tabs">
                <div class="tab active" data-lang="html"><i class="fab fa-html5"></i> HTML</div>
                <div class="tab" data-lang="css"><i class="fab fa-css3-alt"></i> CSS</div>
                <div class="tab" data-lang="js"><i class="fab fa-js-square"></i> JavaScript</div>
            </div>
        </header>
        
        <div class="roadmap">
            <h2><i class="fas fa-road"></i> Lộ Trình Học Tập</h2>
            <div class="roadmap-steps">
                <div class="step">
                    <i class="fab fa-html5"></i>
                    <h3>HTML Cơ Bản</h3>
                </div>
                <div class="step">
                    <i class="fab fa-css3-alt"></i>
                    <h3>CSS Cơ Bản</h3>
                </div>
                <div class="step">
                    <i class="fas fa-mobile-alt"></i>
                    <h3>Responsive</h3>
                </div>
                <div class="step">
                    <i class="fab fa-js"></i>
                    <h3>JavaScript</h3>
                </div>
                <div class="step">
                    <i class="fas fa-project-diagram"></i>
                    <h3>Dự Án Thực Tế</h3>
                </div>
            </div>
        </div>
        
        <div class="content-container">
            <div class="content-box">
                <h2><i class="fas fa-info-circle"></i> Giới Thiệu Ngôn Ngữ</h2>
                
                <div class="lang-content" id="html-content">
                    <h3>HTML là gì?</h3>
                    <p><span class="highlight">HTML (HyperText Markup Language)</span> là ngôn ngữ đánh dấu tiêu chuẩn để tạo các trang web. Nó xác định cấu trúc và nội dung của trang web.</p>
                    
                    <div class="example">
                        <div class="example-title"><i class="fas fa-code"></i> Ví dụ HTML cơ bản:</div>
                        <div class="code">
                            <span class="code-tag">&lt;!DOCTYPE html&gt;</span><br>
                            <span class="code-tag">&lt;html&gt;</span><br>
                            <span class="code-tag">&lt;head&gt;</span><br>
                            &nbsp;&nbsp;<span class="code-tag">&lt;title&gt;</span>Tiêu đề trang<span class="code-tag">&lt;/title&gt;</span><br>
                            <span class="code-tag">&lt;/head&gt;</span><br>
                            <span class="code-tag">&lt;body&gt;</span><br>
                            &nbsp;&nbsp;<span class="code-tag">&lt;h1&gt;</span>Đây là tiêu đề<span class="code-tag">&lt;/h1&gt;</span><br>
                            &nbsp;&nbsp;<span class="code-tag">&lt;p&gt;</span>Đây là đoạn văn bản.<span class="code-tag">&lt;/p&gt;</span><br>
                            <span class="code-tag">&lt;/body&gt;</span><br>
                            <span class="code-tag">&lt;/html&gt;</span>
                        </div>
                    </div>
                    
                    <h3>Các thẻ HTML quan trọng:</h3>
                    <ul>
                        <li><span class="highlight">&lt;h1&gt; đến &lt;h6&gt;</span>: Tiêu đề (heading)</li>
                        <li><span class="highlight">&lt;p&gt;</span>: Đoạn văn (paragraph)</li>
                        <li><span class="highlight">&lt;a&gt;</span>: Liên kết (anchor)</li>
                        <li><span class="highlight">&lt;img&gt;</span>: Hình ảnh (image)</li>
                        <li><span class="highlight">&lt;div&gt;</span>: Khối (division)</li>
                        <li><span class="highlight">&lt;span&gt;</span>: Phạm vi nội tuyến (inline span)</li>
                    </ul>
                </div>
                
                <div class="lang-content" id="css-content" style="display:none">
                    <h3>CSS là gì?</h3>
                    <p><span class="highlight">CSS (Cascading Style Sheets)</span> là ngôn ngữ dùng để mô tả giao diện của trang web. CSS kiểm soát màu sắc, bố cục, font chữ và nhiều yếu tố khác.</p>
                    
                    <div class="example">
                        <div class="example-title"><i class="fas fa-code"></i> Ví dụ CSS cơ bản:</div>
                        <div class="code">
                            <span class="code-comment">/* Chọn tất cả thẻ &lt;p&gt; */</span><br>
                            p {<br>
                            &nbsp;&nbsp;color: <span class="code-value">blue</span>;<br>
                            &nbsp;&nbsp;font-size: <span class="code-value">16px</span>;<br>
                            &nbsp;&nbsp;font-family: <span class="code-value">Arial, sans-serif</span>;<br>
                            }<br><br>
                            
                            <span class="code-comment">/* Chọn phần tử có id="header" */</span><br>
                            <span class="code-tag">#header</span> {<br>
                            &nbsp;&nbsp;background-color: <span class="code-value">#f0f0f0</span>;<br>
                            &nbsp;&nbsp;padding: <span class="code-value">20px</span>;<br>
                            }
                        </div>
                    </div>
                    
                    <h3>Các khái niệm CSS quan trọng:</h3>
                    <ul>
                        <li><span class="highlight">Bộ chọn (Selector)</span>: Cách chọn phần tử HTML để áp dụng kiểu</li>
                        <li><span class="highlight">Thuộc tính (Property)</span>: Đặc điểm cần thay đổi (màu sắc, kích thước...)</li>
                        <li><span class="highlight">Giá trị (Value)</span>: Giá trị cụ thể cho thuộc tính</li>
                        <li><span class="highlight">Box Model</span>: Mô hình hộp gồm content, padding, border, margin</li>
                        <li><span class="highlight">Flexbox & Grid</span>: Hệ thống bố cục hiện đại</li>
                    </ul>
                </div>
                
                <div class="lang-content" id="js-content" style="display:none">
                    <h3>JavaScript là gì?</h3>
                    <p><span class="highlight">JavaScript</span> là ngôn ngữ lập trình giúp tạo các trang web động và tương tác. JS có thể thay đổi nội dung, kiểm soát đa phương tiện, xử lý dữ liệu và nhiều hơn nữa.</p>
                    
                    <div class="example">
                        <div class="example-title"><i class="fas fa-code"></i> Ví dụ JavaScript cơ bản:</div>
                        <div class="code">
                            <span class="code-comment">// Hiển thị thông báo khi trang được tải</span><br>
                            window.onload = function() {<br>
                            &nbsp;&nbsp;alert(<span class="code-value">'Chào mừng đến với trang web!'</span>);<br>
                            };<br><br>
                            
                            <span class="code-comment">// Thay đổi nội dung phần tử</span><br>
                            document.getElementById(<span class="code-value">'demo'</span>).innerHTML = <br>
                            &nbsp;&nbsp;<span class="code-value">'Xin chào JavaScript!'</span>;<br><br>
                            
                            <span class="code-comment">// Xử lý sự kiện click</span><br>
                            document.querySelector(<span class="code-value">'button'</span>).addEventListener(<br>
                            &nbsp;&nbsp;<span class="code-value">'click'</span>, function() {<br>
                            &nbsp;&nbsp;&nbsp;&nbsp;alert(<span class="code-value">'Bạn đã nhấn nút!'</span>);<br>
                            &nbsp;&nbsp;}<br>
                            );
                        </div>
                    </div>
                    
                    <h3>Các khái niệm JavaScript quan trọng:</h3>
                    <ul>
                        <li><span class="highlight">Biến (Variables)</span>: Lưu trữ dữ liệu</li>
                        <li><span class="highlight">Hàm (Functions)</span>: Khối mã thực hiện tác vụ</li>
                        <li><span class="highlight">Sự kiện (Events)</span>: Hành động người dùng (click, di chuột...)</li>
                        <li><span class="highlight">DOM Manipulation</span>: Thay đổi nội dung và cấu trúc trang web</li>
                        <li><span class="highlight">AJAX & Fetch API</span>: Giao tiếp với máy chủ không cần tải lại trang</li>
                    </ul>
                </div>
            </div>
            
            <div class="content-box">
                <h2><i class="fas fa-lightbulb"></i> Mẹo Học Hiệu Quả</h2>
                
                <h3><i class="fas fa-check-circle"></i> Nguyên tắc học lập trình:</h3>
                <p>1. <span class="highlight">Học qua thực hành</span>: Code mỗi ngày, dù chỉ 30 phút</p>
                <p>2. <span class="highlight">Bắt đầu từ nhỏ</span>: Xây dựng dự án đơn giản trước</p>
                <p>3. <span class="highlight">Tìm hiểu nguyên nhân</span>: Đừng chỉ copy code, hãy hiểu tại sao</p>
                <p>4. <span class="highlight">Sử dụng Google</span>: Đây là công cụ quan trọng nhất của lập trình viên</p>
                <p>5. <span class="highlight">Kiên nhẫn</span>: Ai cũng bắt đầu từ con số 0</p>
                
                <h3><i class="fas fa-project-diagram"></i> Dự án thực hành đầu tiên:</h3>
                <p>Hãy tạo một trang giới thiệu bản thân đơn giản:</p>
                <ol>
                    <li>Tạo file <span class="highlight">index.html</span></li>
                    <li>Thêm tiêu đề với tên của bạn</li>
                    <li>Chèn ảnh của bạn hoặc avatar</li>
                    <li>Viết một đoạn giới thiệu ngắn</li>
                    <li>Tạo danh sách sở thích của bạn</li>
                    <li>Thêm liên kết đến mạng xã hội</li>
                </ol>
                
                <h3><i class="fas fa-bug"></i> Cách gỡ lỗi (debug) hiệu quả:</h3>
                <p>- Kiểm tra console trong trình duyệt (F12)</p>
                <p>- Sử dụng console.log() để kiểm tra giá trị</p>
                <p>- Kiểm tra từng phần nhỏ của code</p>
                <p>- Tìm kiếm thông báo lỗi trên Google</p>
                <p>- Nghỉ ngơi nếu bị kẹt quá lâu</p>
                
                <div class="example">
                    <div class="example-title"><i class="fas fa-question-circle"></i> Lời khuyên:</div>
                    <p>"Đừng cố ghi nhớ mọi thứ. Quan trọng là hiểu khái niệm và biết cách tìm thông tin khi cần."</p>
                </div>
            </div>
        </div>
        
        <div class="practice-area">
            <h2><i class="fas fa-laptop-code"></i> Khu Vực Thực Hành</h2>
            <p>Thử sửa đổi code và xem kết quả thay đổi thế nào:</p>
            
            <div class="editor-container">
                <div class="code-editor">
                    &lt;!DOCTYPE html&gt;<br>
                    &lt;html&gt;<br>
                    &lt;head&gt;<br>
                    &nbsp;&nbsp;&lt;title&gt;Trang của tôi&lt;/title&gt;<br>
                    &nbsp;&nbsp;&lt;style&gt;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;body {<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;font-family: Arial, sans-serif;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;background-color: #f0f8ff;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;text-align: center;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;padding: 50px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
                    <br>
                    &nbsp;&nbsp;&nbsp;&nbsp;h1 {<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;color: #2e86c1;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
                    <br>
                    &nbsp;&nbsp;&nbsp;&nbsp;.container {<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;background: white;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;border-radius: 10px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;padding: 30px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;box-shadow: 0 0 10px rgba(0,0,0,0.1);<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;max-width: 600px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;margin: 0 auto;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
                    <br>
                    &nbsp;&nbsp;&nbsp;&nbsp;button {<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;background: #3498db;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;color: white;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;border: none;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;padding: 12px 25px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;border-radius: 5px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cursor: pointer;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;font-size: 16px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;margin-top: 20px;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
                    <br>
                    &nbsp;&nbsp;&lt;/style&gt;<br>
                    &lt;/head&gt;<br>
                    &lt;body&gt;<br>
                    &nbsp;&nbsp;&lt;div class="container"&gt;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&lt;h1&gt;Xin chào!&lt;/h1&gt;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&lt;p id="message"&gt;Hãy nhấn nút bên dưới&lt;/p&gt;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&lt;button onclick="changeMessage()"&gt;Nhấn vào tôi&lt;/button&gt;<br>
                    &nbsp;&nbsp;&lt;/div&gt;<br>
                    <br>
                    &nbsp;&nbsp;&lt;script&gt;<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;function changeMessage() {<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;document.getElementById('message').innerHTML = <br>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'Bạn đã học được cách sử dụng JavaScript!';<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
                    &nbsp;&nbsp;&lt;/script&gt;<br>
                    &lt;/body&gt;<br>
                    &lt;/html&gt;
                </div>
                
                <div class="preview">
                    <h1>Xin chào!</h1>
                    <p id="message">Hãy nhấn nút bên dưới</p>
                    <button onclick="changeMessage()">Nhấn vào tôi</button>
                </div>
            </div>
            
            <button class="btn btn-run" onclick="runCode()"><i class="fas fa-play"></i> Chạy Thử Code</button>
        </div>
        
        <div class="resources">
            <h2><i class="fas fa-book"></i> Tài Nguyên Học Tập Tiếng Việt</h2>
            
            <div class="resource-list">
                <div class="resource-card">
                    <h3><i class="fab fa-html5"></i> HTML</h3>
                    <a href="https://www.w3schools.com/html/" target="_blank">W3Schools HTML Tutorial</a>
                    <a href="https://webcoban.vn/html" target="_blank">Web Cơ Bản - HTML</a>
                    <a href="https://developer.mozilla.org/vi/docs/Web/HTML" target="_blank">MDN Web Docs (tiếng Việt)</a>
                </div>
                
                <div class="resource-card">
                    <h3><i class="fab fa-css3-alt"></i> CSS</h3>
                    <a href="https://www.w3schools.com/css/" target="_blank">W3Schools CSS Tutorial</a>
                    <a href="https://webcoban.vn/css" target="_blank">Web Cơ Bản - CSS</a>
                    <a href="https://css-tricks.com/" target="_blank">CSS Tricks (có dịch tiếng Việt)</a>
                </div>
                
                <div class="resource-card">
                    <h3><i class="fab fa-js"></i> JavaScript</h3>
                    <a href="https://www.w3schools.com/js/" target="_blank">W3Schools JavaScript Tutorial</a>
                    <a href="https://webcoban.vn/javascript" target="_blank">Web Cơ Bản - JavaScript</a>
                    <a href="https://developer.mozilla.org/vi/docs/Web/JavaScript" target="_blank">MDN JavaScript Guide</a>
                </div>
                
                <div class="resource-card">
                    <h3><i class="fas fa-graduation-cap"></i> Khóa Học</h3>
                    <a href="https://fullstack.edu.vn/" target="_blank">F8 Fullstack (miễn phí)</a>
                    <a href="https://www.udemy.com/course/html-css-javascript-tieng-viet/" target="_blank">Udemy - Web cơ bản</a>
                    <a href="https://www.youtube.com/c/Th%C3%A1ngDev" target="_blank">Kênh YouTube Tháng Dev</a>
                </div>
            </div>
        </div>
        
        <footer>
            <p>© 2023 Trang Học Lập Trình Web - Dành cho người mới bắt đầu | Tạo bởi [Tên của bạn]</p>
            <p>Bạn có thể sử dụng và chỉnh sửa trang này tự do cho mục đích học tập</p>
        </footer>
    </div>

    <script>
        // Chuyển đổi tab ngôn ngữ
        const tabs = document.querySelectorAll('.tab');
        const contents = document.querySelectorAll('.lang-content');
        
        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                // Xóa active class từ tất cả các tab
                tabs.forEach(t => t.classList.remove('active'));
                
                // Thêm active class vào tab được click
                tab.classList.add('active');
                
                // Ẩn tất cả nội dung
                contents.forEach(content => {
                    content.style.display = 'none';
                });
                
                // Hiển thị nội dung tương ứng
                const lang = tab.getAttribute('data-lang');
                document.getElementById(`${lang}-content`).style.display = 'block';
            });
        });
        
        // Chạy code trong khu vực thực hành
        function runCode() {
            alert('Trong môi trường thực tế, bạn sẽ thấy kết quả thay đổi ngay lập tức!\n\nHãy thử nhấn nút "Nhấn vào tôi" trong phần Preview.');
            
            // Trong thực tế, đây là nơi bạn sẽ chạy và hiển thị kết quả code
            // Đối với mục đích minh họa, chúng ta chỉ hiển thị thông báo
        }
        
        // Hàm cho nút trong phần preview
        function changeMessage() {
            document.getElementById('message').innerHTML = 
                'Bạn đã học được cách sử dụng JavaScript! 🎉';
        }
    </script>
</body>
</html>
