<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DuoHacker - Duolingo Farming Tool</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%);
            color: #e0e0e0;
            line-height: 1.8;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 60px;
            padding: 40px 20px;
        }

        .logo-section {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .logo {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #1E88E5 0%, #0D47A1 100%);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            box-shadow: 0 10px 30px rgba(30, 136, 229, 0.3);
        }

        h1 {
            font-size: 3.5em;
            background: linear-gradient(135deg, #64B5F6 0%, #1E88E5 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }

        .tagline {
            font-size: 1.3em;
            color: #90caf9;
            margin-bottom: 20px;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .badge {
            background: rgba(30, 136, 229, 0.2);
            border: 1px solid #1E88E5;
            color: #64B5F6;
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9em;
            font-weight: 600;
        }

        section {
            background: rgba(26, 31, 58, 0.5);
            border: 1px solid rgba(30, 136, 229, 0.2);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 25px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        section:hover {
            border-color: rgba(30, 136, 229, 0.4);
            box-shadow: 0 10px 30px rgba(30, 136, 229, 0.1);
        }

        h2 {
            color: #64B5F6;
            font-size: 2em;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        h3 {
            color: #1E88E5;
            font-size: 1.4em;
            margin: 20px 0 10px 0;
        }

        p {
            color: #b0bec5;
            margin-bottom: 15px;
            font-size: 1.05em;
        }

        ul, ol {
            margin: 20px 0 20px 30px;
            color: #b0bec5;
        }

        li {
            margin-bottom: 12px;
            font-size: 1.05em;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 25px 0;
        }

        .feature-card {
            background: rgba(30, 136, 229, 0.08);
            border: 1px solid rgba(30, 136, 229, 0.2);
            border-radius: 12px;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            border-color: #1E88E5;
            box-shadow: 0 10px 25px rgba(30, 136, 229, 0.15);
        }

        .feature-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .feature-card h4 {
            color: #64B5F6;
            margin-bottom: 10px;
            font-size: 1.2em;
        }

        .feature-card p {
            font-size: 0.95em;
            margin: 0;
        }

        code {
            background: rgba(0, 0, 0, 0.3);
            padding: 2px 6px;
            border-radius: 4px;
            color: #81c784;
            font-family: 'Courier New', monospace;
        }

        .code-block {
            background: rgba(0, 0, 0, 0.4);
            border-left: 3px solid #1E88E5;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            margin: 20px 0;
        }

        .code-block code {
            color: #90caf9;
            padding: 0;
            background: none;
        }

        .button-group {
            display: flex;
            gap: 15px;
            margin-top: 25px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1em;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #1E88E5 0%, #0D47A1 100%);
            color: white;
            box-shadow: 0 5px 15px rgba(30, 136, 229, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(30, 136, 229, 0.4);
        }

        .btn-secondary {
            background: rgba(30, 136, 229, 0.1);
            color: #64B5F6;
            border: 1px solid #1E88E5;
        }

        .btn-secondary:hover {
            background: rgba(30, 136, 229, 0.2);
        }

        .warning-box {
            background: rgba(251, 140, 0, 0.1);
            border-left: 4px solid #FB8C00;
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
        }

        .warning-box strong {
            color: #FFB74D;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        th {
            background: rgba(30, 136, 229, 0.2);
            color: #64B5F6;
            padding: 12px;
            text-align: left;
            border-bottom: 2px solid #1E88E5;
        }

        td {
            padding: 12px;
            border-bottom: 1px solid rgba(30, 136, 229, 0.1);
        }

        tr:hover {
            background: rgba(30, 136, 229, 0.05);
        }

        footer {
            text-align: center;
            padding: 30px 20px;
            color: #78909c;
            border-top: 1px solid rgba(30, 136, 229, 0.2);
            margin-top: 50px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 15px 0;
        }

        .social-links a {
            color: #64B5F6;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            color: #1E88E5;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5em;
            }

            h2 {
                font-size: 1.6em;
            }

            .logo-section {
                flex-direction: column;
            }

            section {
                padding: 20px;
            }

            .feature-grid {
                grid-template-columns: 1fr;
            }

            .button-group {
                flex-direction: column;
            }

            .btn {
                justify-content: center;
                width: 100%;
            }
        }

        .mode-showcase {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .mode-box {
            background: rgba(30, 136, 229, 0.08);
            border: 1px solid rgba(30, 136, 229, 0.2);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
        }

        .mode-box .icon {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .mode-box h4 {
            color: #64B5F6;
            margin-bottom: 8px;
        }

        .mode-box p {
            font-size: 0.9em;
            margin: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo-section">
                <div class="logo">🦉</div>
                <div>
                    <h1>DuoHacker</h1>
                    <p class="tagline">⚡ Advanced Duolingo Farming Tool with Safe Mode</p>
                </div>
            </div>
            <div class="badges">
                <span class="badge">v2.2</span>
                <span class="badge">✅ Safe Mode</span>
                <span class="badge">📱 Multi-Account</span>
                <span class="badge">🚀 High Performance</span>
            </div>
        </header>

        <section>
            <h2>🎯 Overview</h2>
            <p><strong>DuoHacker</strong> is a comprehensive Duolingo farming tool designed with both functionality and safety in mind. Automate your XP, gem collection, and streak farming with intelligent modes that minimize detection risks.</p>
            <p style="color: #81c784; font-weight: 500;">✨ The most advanced free-to-use Duolingo automation tool with new safety features!</p>
        </section>

        <section>
            <h2>✨ Key Features</h2>
            <div class="feature-grid">
                <div class="feature-card">
                    <div class="feature-icon">🛡️</div>
                    <h4>Safe Mode</h4>
                    <p>Undetectable farming with 2-second delays between actions</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <h4>Fast Mode</h4>
                    <p>Quick farming with 0.3s delays for experienced users</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💎</div>
                    <h4>Multi-Currency Farming</h4>
                    <p>Farm XP, Gems, and Streaks simultaneously</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">👥</div>
                    <h4>Multi-Account Manager</h4>
                    <p>Save and switch between multiple accounts instantly</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔥</div>
                    <h4>Streak Repair & Farming</h4>
                    <p>Automatically repair frozen streaks and farm new ones</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎓</div>
                    <h4>Auto-Solve Lessons</h4>
                    <p>Automatically complete lessons with zero interaction</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎨</div>
                    <h4>Dark/Light Theme</h4>
                    <p>Beautiful UI with toggle between dark and light modes</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h4>Live Statistics</h4>
                    <p>Real-time farming stats and activity logging</p>
                </div>
            </div>
        </section>

        <section>
            <h2>🚀 Installation</h2>
            <h3>Prerequisites</h3>
            <ul>
                <li>A browser with Tampermonkey or Greasemonkey installed</li>
                <li>Active Duolingo account</li>
                <li>Latest browser version</li>
            </ul>

            <h3>Steps:</h3>
            <ol>
                <li>Install <strong>Tampermonkey</strong> extension for your browser:
                    <ul>
                        <li><a href="https://chrome.google.com/webstore" style="color: #64B5F6;">Chrome</a></li>
                        <li><a href="https://addons.mozilla.org" style="color: #64B5F6;">Firefox</a></li>
                        <li><a href="https://apps.apple.com" style="color: #64B5F6;">Safari</a></li>
                    </ul>
                </li>
                <li>Visit <a href="https://greasyfork.org/en/scripts/551444" style="color: #64B5F6;"><strong>Greasyfork Script Page</strong></a></li>
                <li>Click <strong>"Install this script"</strong></li>
                <li>Confirm installation in Tampermonkey popup</li>
                <li>Go to <strong>duolingo.com</strong> and click the 🔧 icon in bottom-right</li>
            </ol>
        </section>

        <section>
            <h2>📖 How to Use</h2>
            <h3>1. Initial Setup</h3>
            <ol>
                <li>Open Duolingo and log in to your account</li>
                <li>Click the floating 🔧 icon in the bottom-right corner</li>
                <li>Join our community to unlock all features (free)</li>
                <li>Allow time for user data to load</li>
            </ol>

            <h3>2. Select Your Farming Mode</h3>
            <div class="mode-showcase">
                <div class="mode-box">
                    <div class="icon">🛡️</div>
                    <h4>Safe Mode</h4>
                    <p><strong>2s delay</strong><br>100% undetectable</p>
                </div>
                <div class="mode-box">
                    <div class="icon">⚡</div>
                    <h4>Fast Mode</h4>
                    <p><strong>0.3s delay</strong><br>Use with caution</p>
                </div>
            </div>

            <h3>3. Choose Farming Option</h3>
            <ul>
                <li><strong>Farm XP</strong> - Earn XP continuously</li>
                <li><strong>Farm Gems</strong> - Collect gems (30 per action)</li>
                <li><strong>Repair Streak</strong> - Fix frozen streaks</li>
                <li><strong>Farm Streak</strong> - Increase current streak</li>
                <li><strong>Solve Lesson</strong> - Auto-complete lessons</li>
                <li><strong>Farm All</strong> - Combine all farming methods</li>
            </ul>

            <h3>4. Start Farming</h3>
            <p>Click <strong>"Start Farming"</strong> and watch the live statistics update in real-time!</p>
        </section>

        <section>
            <h2>⚙️ Advanced Features</h2>
            <h3>Account Manager</h3>
            <p>Save multiple accounts and switch between them instantly:</p>
            <ul>
                <li>Click the 👥 button to open Account Manager</li>
                <li>Click 💾 to save current account with custom nickname</li>
                <li>Switch accounts with one click</li>
                <li>Automatic login to selected account</li>
            </ul>

            <h3>Duolingo Max Features</h3>
            <p>Unlock premium features with one toggle:</p>
            <ul>
                <li>Unlimited hearts</li>
                <li>Remove ads</li>
                <li>Advanced lessons</li>
            </ul>

            <h3>Privacy Settings</h3>
            <ul>
                <li>Toggle between public and private profile</li>
                <li>One-click privacy management</li>
            </ul>

            <h3>Auto-Solve (Beta)</h3>
            <p>Automatically solve lessons when navigating to lesson pages. Enable in settings.</p>
        </section>

        <section>
            <h2>⚡ Farming Modes Explained</h2>
            <table>
                <tr>
                    <th>Mode</th>
                    <th>Delay</th>
                    <th>Detection Risk</th>
                    <th>Best For</th>
                </tr>
                <tr>
                    <td><strong>Safe Mode</strong></td>
                    <td>2 seconds</td>
                    <td>🟢 Very Low</td>
                    <td>Long-term farming, main accounts</td>
                </tr>
                <tr>
                    <td><strong>Fast Mode</strong></td>
                    <td>0.3 seconds</td>
                    <td>🟡 Moderate</td>
                    <td>Alt accounts, quick tests</td>
                </tr>
            </table>
        </section>

        <section>
            <h2>🔐 Safety & Legal</h2>
            <div class="warning-box">
                <strong>⚠️ Important:</strong> DuoHacker is designed with safety in mind, but use at your own risk. We recommend:
            </div>
            <ul>
                <li>✅ Use <strong>Safe Mode</strong> for your main account</li>
                <li>✅ Never farm excessively in short periods</li>
                <li>✅ Test on alt accounts first</li>
                <li>✅ Keep reasonable farming intervals</li>
                <li>❌ Don't use on educational/institutional accounts</li>
                <li>❌ Don't share your accounts or farming patterns</li>
            </ul>
            <p><strong>Disclaimer:</strong> This tool is for educational purposes. Users are responsible for their account safety and adherence to Duolingo's Terms of Service.</p>
        </section>

        <section>
            <h2>🐛 Troubleshooting</h2>
            <h3>Script Not Working?</h3>
            <ul>
                <li>Ensure Tampermonkey is enabled</li>
                <li>Check if script is installed (check Tampermonkey dashboard)</li>
                <li>Try clearing browser cache and cookies</li>
                <li>Reload Duolingo page</li>
                <li>Use latest Chrome/Firefox version</li>
            </ul>

            <h3>Not Farming?</h3>
            <ul>
                <li>Ensure you're logged into Duolingo</li>
                <li>Wait for user data to load completely</li>
                <li>Check if farming option is selected</li>
                <li>Check console for error messages (F12 → Console)</li>
            </ul>

            <h3>Account Errors?</h3>
            <ul>
                <li>Re-login to your Duolingo account</li>
                <li>Clear saved accounts and re-add them</li>
                <li>Check JWT token validity</li>
            </ul>
        </section>

        <section>
            <h2>💡 Tips & Tricks</h2>
            <ul>
                <li><strong>Streak Farming:</strong> Farm small streak increments regularly rather than large amounts at once</li>
                <li><strong>XP Farming:</strong> Combine with other farming types for optimal results</li>
                <li><strong>Account Switching:</strong> Use multi-account feature to distribute farming load</li>
                <li><strong>Night Farming:</strong> Consider farming during off-peak hours for lower detection risk</li>
                <li><strong>Vary Patterns:</strong> Mix safe and fast modes, vary farming times</li>
            </ul>
        </section>

        <section>
            <h2>📞 Support & Community</h2>
            <p>Join our thriving community for support, updates, and exclusive features:</p>
            <div class="button-group">
                <a href="https://discord.gg/Gvmd7deFtS" class="btn btn-primary">
                    <span>💬</span> Join Discord Community
                </a>
                <a href="https://greasyfork.org/en/scripts/551444" class="btn btn-secondary">
                    <span>📥</span> Visit Script Page
                </a>
            </div>
        </section>

        <section>
            <h2>📝 Changelog</h2>
            <h3>v2.2 (Latest)</h3>
            <ul>
                <li>✨ Enhanced Multi-Account Manager</li>
                <li>🛡️ Improved Safe Mode detection avoidance</li>
                <li>🎨 New beautiful UI with dark/light themes</li>
                <li>🐛 Bug fixes and performance improvements</li>
                <li>📱 Better mobile responsiveness</li>
            </ul>
        </section>

        <footer>
            <p><strong>DuoHacker v2.2</strong> - Built with ❤️ by the DuoHacker Community</p>
            <p>© 2025 All Rights Reserved | MIT License</p>
            <div class="social-links">
                <a href="https://discord.gg/Gvmd7deFtS">Discord</a>
                <a href="https://greasyfork.org/en/scripts/551444">Greasyfork</a>
                <a href="https://twisk.fun">Website</a>
            </div>
        </footer>
    </div>
</body>
</html>
