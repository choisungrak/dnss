<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>총 길이 및 중량 계산기</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            height: 100vh;
            margin: 0;
            padding-top: 20px;
            background-color: #f4f4f4;
            user-select: none;
        }
        .calculator {
            border: 1px solid #ccc;
            padding: 8px;
            background: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            width: 100%;
            max-width: 900px;
            text-align: center;
            margin-bottom: 40px;
        }
        .calculator h1 {
            color: red;
            margin-bottom: 32px;
            font-size: 1.68em;
        }
        .calculator h2 {
            color: black;
            margin-bottom: 20px;
            font-size: 1.008em;
            text-align: center;
            line-height: 1.5;
        }
        .input-group {
            display: flex;
            align-items: center;
            margin-bottom: 12px;
            justify-content: center;
        }
        .input-group label {
            margin-right: 5px;
        }
        .input-group .length-input,
        .input-group .quantity-input {
            padding: 6px;
            font-size: 1em;
            border: 1px solid #ccc;
            border-radius: 5px;
            margin-right: 8px;
        }
        .input-group .length-input {
            width: 90px;
        }
        .input-group .quantity-input {
            width: 50px;
        }
        .input-group .thickness-select,
        .input-group .material-select {
            padding: 6px;
            font-size: 1em;
            border: 1px solid #ccc;
            border-radius: 5px;
            width: 200px;
        }
        .button {
            padding: 6px 12px;
            font-size: 1.2em;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
            background: #007bff;
            color: #fff;
            text-align: center;
            display: inline-block;
            width: 100%;
            max-width: 300px;
        }
        .result-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
        }
        .result-group {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 10px;
            border: 3px solid #ccc;
            border-radius: 5px;
            width: 78%;
            max-width: 624px;
            margin-bottom: 20px;
        }
        .result, .weight-result, .sub-result {
            margin-top: 6px;
            font-size: 1.56em;
            color: black;
            padding: 6px;
            text-align: center;
            width: 100%;
        }
        .sub-result.red {
            color: red;
        }
        .material-image {
            display: flex;
            justify-content: center;
            margin-bottom: 50px;
        }
        .material-image div {
            margin: 0;
        }
        .material-image img {
            width: 150px;
            height: auto;
            cursor: pointer;
            border: 2px solid transparent;
            border-radius: 5px;
            margin: 0 4px;
        }
        .material-image img.selected {
            border: 2px solid blue;
        }
        img.responsive {
            width: 100%;
            max-width: 500px;
            height: auto;
        }
        @media (max-width: 768px) {
            .calculator {
                width: 100%;
                padding: 16px;
            }
            .pipe-size-group {
                width: 100%;
            }
            .input-group .length-input,
            .input-group .quantity-input {
                width: 70px;
            }
            .input-group .thickness-select,
            .input-group .material-select {
                width: 150px;
            }
            .material-image img {
                width: 100px;
            }
            img.responsive {
                width: 100%;
                height: auto;
            }
            .result-group .sub-result {
                font-size: 1em;
                white-space: nowrap;
            }
        }
    </style>
</head>
<body>
<div class="calculator">
    <h1>디엔에스스틸 주문방법 계산기</h1>
    <h2>1. 각파이프의 종류를 선택해 주세요.</h2>
    <div class="material-image">
        <div>
            <img src="https://gi.esmplus.com/dnssteel/%EC%95%84%EC%97%B0%EA%B0%81%ED%8C%8C%EC%9D%B4%ED%94%84.jpg" alt="아연각파이프" onclick="selectMaterial(this, '아연 각파이프')">
        </div>
        <div>
            <img src="https://gi.esmplus.com/dnssteel/%EC%B9%BC%EB%9D%BC%EA%B0%81%ED%8C%8C%EC%9D%B4%ED%94%84.jpg" alt="칼라각파이프" onclick="selectMaterial(this, '칼라 각파이프')">
        </div>
        <div>
            <img src="https://gi.esmplus.com/dnssteel/%ED%9D%91%EA%B4%80%EA%B0%81%ED%8C%8C%EC%9D%B4%ED%94%84.jpg" alt="흑관각파이프" onclick="selectMaterial(this, '흑관 각파이프')">
        </div>
    </div>
    <h2>2. 각파이프 사이즈를 입력한 후 두께를 선택해주세요.</h2>
    <form id="calculatorForm">
        <div class="input-group">
            <label for="material">종류:</label>
            <select id="material" class="material-select">
                <option value="">선택하세요</option>
                <option value="아연 각파이프">아연 각파이프</option>
                <option value="칼라 각파이프">칼라 각파이프</option>
                <option value="흑관 각파이프">흑관 각파이프</option>
            </select>
        </div>
        <h2>3. 계산을 시작하세요.</h2>
        <button class="button" onclick="calculateTotalLengthAndWeight()">계산하기</button>
    </form>
</div>
<script>
    // JavaScript Code
</script>
</body>
</html>
