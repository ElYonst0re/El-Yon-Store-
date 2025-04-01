<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>El-Yon Store</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f8f9fa;
        }
        .header {
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            padding: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
            color: white;
        }
        .parallax {
            background-image: url('https://source.unsplash.com/1600x900/?store,accessories');
            height: 300px;
            background-attachment: fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
        }
        .container {
            text-align: center;
            padding: 20px;
        }
        .product {
            display: inline-block;
            margin: 15px;
            padding: 10px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        .product img {
            width: 150px;
            height: 150px;
            border-radius: 8px;
        }
        .buy-btn {
            display: block;
            margin: 10px auto;
            padding: 8px 15px;
            background-color: #ff6f61;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .buy-btn:hover {
            background-color: #e65c50;
        }
        .payment-form {
            text-align: center;
            margin-top: 20px;
            display: none;
        }
        .payment-form input {
            padding: 8px;
            margin: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .payment-form button {
            padding: 8px 15px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .payment-form button:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>
    <div class="header">El-Yon Store</div>
    <div class="parallax"></div>
    <div class="container">
        <h2>منتجاتنا</h2>
        <div id="products-container"></div>
    </div>
    
    <div class="payment-form" id="payment-form">
        <h3>إتمام الدفع عبر فودافون كاش</h3>
        <p>قم بتحويل المبلغ إلى رقم المحفظة: <strong>01012345678</strong></p>
        <p>ثم أدخل رقم التحويل أدناه:</p>
        <input type="text" id="transaction-id" placeholder="رقم التحويل">
        <button onclick="confirmPayment()">تأكيد الدفع</button>
    </div>

    <script>
        const sheetUrl = 'YOUR_GOOGLE_SHEET_JSON_URL'; // ضع رابط Google Sheets JSON هنا

        async function fetchProducts() {
            try {
                let response = await fetch(sheetUrl);
                let data = await response.json();
                let products = data.products; // يفترض أن يكون لديك صفحة "Products" في Google Sheets
                let container = document.getElementById("products-container");
                container.innerHTML = "";
                products.forEach(product => {
                    container.innerHTML += `
                        <div class="product">
                            <img src="${product.image}" alt="${product.name}">
                            <p>${product.name}</p>
                            <button class="buy-btn" onclick="showPaymentForm()">شراء</button>
                        </div>
                    `;
                });
            } catch (error) {
                console.error("Error fetching products:", error);
            }
        }

        function showPaymentForm() {
            document.getElementById("payment-form").style.display = "block";
        }
        function confirmPayment() {
            let transactionId = document.getElementById("transaction-id").value;
            if (transactionId) {
                alert("تم استلام رقم التحويل: " + transactionId + "\nسنقوم بمراجعة الطلب.");
            } else {
                alert("يرجى إدخال رقم التحويل.");
            }
        }

        fetchProducts();
    </script>
</body>
</html>
