<?php
$file = "posts.txt";

// 파일이 없으면 생성
if (!file_exists($file)) {
    file_put_contents($file, "");
}

// 글 저장 처리
if ($_SERVER["REQUEST_METHOD"] === "POST") {
    $name = trim($_POST["name"] ?? "");
    $title = trim($_POST["title"] ?? "");
    $content = trim($_POST["content"] ?? "");

    if ($name !== "" && $title !== "" && $content !== "") {
        $date = date("Y-m-d H:i:s");

        // 줄바꿈/구분자 충돌 최소화용 치환
        $name = str_replace(["\r", "\n", "|"], [" ", " ", "/"], $name);
        $title = str_replace(["\r", "\n", "|"], [" ", " ", "/"], $title);
        $content = str_replace(["\r\n", "\r", "\n", "|"], ["<br>", "<br>", "<br>", "/"], $content);

        $line = $date . "|" . $name . "|" . $title . "|" . $content . PHP_EOL;

        file_put_contents($file, $line, FILE_APPEND | LOCK_EX);
    }

    // 새로고침 중복 저장 방지
    header("Location: " . $_SERVER["PHP_SELF"]);
    exit;
}

// 파일 읽기
$posts = file($file, FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
$posts = array_reverse($posts); // 최신글이 위로 오게
?>
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>텍스트 공유 게시판</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f4f6f8;
            color: #222;
        }

        .wrap {
            max-width: 900px;
            margin: 40px auto;
            padding: 20px;
        }

        h1 {
            text-align: center;
            margin-bottom: 10px;
        }

        p.desc {
            text-align: center;
            color: #666;
            margin-bottom: 30px;
        }

        .card {
            background: white;
            padding: 20px;
            border-radius: 14px;
            box-shadow: 0 4px 16px rgba(0,0,0,0.07);
            margin-bottom: 20px;
        }

        input, textarea, button {
            width: 100%;
            padding: 12px;
            margin-top: 8px;
            margin-bottom: 14px;
            border: 1px solid #d0d7de;
            border-radius: 10px;
            font-size: 14px;
        }

        textarea {
            min-height: 120px;
            resize: vertical;
        }

        button {
            background: #111827;
            color: white;
            border: none;
            cursor: pointer;
            font-weight: bold;
        }

        button:hover {
            opacity: 0.92;
        }

        .post {
            border: 1px solid #e5e7eb;
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 14px;
            background: #fcfcfc;
        }

        .meta {
            font-size: 13px;
            color: #666;
            margin-bottom: 10px;
        }

        .title {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .content {
            line-height: 1.6;
            word-break: break-word;
        }

        .empty {
            text-align: center;
            color: #888;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <h1>텍스트 공유 게시판</h1>
        <p class="desc">글을 작성하면 텍스트 파일에 저장되고, 접속한 사람 모두가 볼 수 있습니다.</p>

        <div class="card">
            <form method="post">
                <label>작성자</label>
                <input type="text" name="name" placeholder="이름 입력" required>

                <label>제목</label>
                <input type="text" name="title" placeholder="제목 입력" required>

                <label>내용</label>
                <textarea name="content" placeholder="내용 입력" required></textarea>

                <button type="submit">저장하기</button>
            </form>
        </div>

        <div class="card">
            <h2>등록된 글</h2>

            <?php if (empty($posts)): ?>
                <div class="empty">아직 등록된 글이 없습니다.</div>
            <?php else: ?>
                <?php foreach ($posts as $post): ?>
                    <?php
                    $parts = explode("|", $post, 4);
                    if (count($parts) === 4) {
                        [$date, $name, $title, $content] = $parts;
                    } else {
                        continue;
                    }
                    ?>
                    <div class="post">
                        <div class="meta">
                            작성자: <?= htmlspecialchars($name, ENT_QUOTES, 'UTF-8') ?> |
                            작성일: <?= htmlspecialchars($date, ENT_QUOTES, 'UTF-8') ?>
                        </div>
                        <div class="title">
                            <?= htmlspecialchars($title, ENT_QUOTES, 'UTF-8') ?>
                        </div>
                        <div class="content">
                            <?= $content ?>
                        </div>
                    </div>
                <?php endforeach; ?>
            <?php endif; ?>
        </div>
    </div>
</body>
</html>