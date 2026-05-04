layout: page
title: "Submit Page"
permalink: /submit/

[submit.html](https://github.com/user-attachments/files/27374927/submit.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Submit a Support Request</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #0d0d0b;
  --surface: #161614;
  --surface-2: #1e1e1b;
  --border: #2a2a26;
  --border-hover: #3a3a35;
  --text: #f0efe8;
  --text-2: #9a9890;
  --text-3: #5a5955;
  --accent: #d4a853;
  --accent-dim: rgba(212,168,83,0.12);
  --accent-border: rgba(212,168,83,0.3);
  --green: #4ade80;
  --green-bg: rgba(74,222,128,0.08);
  --red: #f87171;
  --font-serif: 'Instrument Serif', Georgia, serif;
  --font-sans: 'DM Sans', sans-serif;
  --font-mono: 'DM Mono', monospace;
  --radius: 10px;
  --radius-lg: 16px;
}

html { scroll-behavior: smooth; }

body {
  font-family: var(--font-sans);
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 40px 20px;
  position: relative;
  overflow-x: hidden;
}

/* Background texture */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background:
    radial-gradient(ellipse 80% 50% at 20% 10%, rgba(212,168,83,0.06) 0%, transparent 60%),
    radial-gradient(ellipse 60% 40% at 80% 80%, rgba(212,168,83,0.04) 0%, transparent 50%);
  pointer-events: none;
  z-index: 0;
}

.grain {
  position: fixed;
  inset: -50%;
  width: 200%;
  height: 200%;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='1'/%3E%3C/svg%3E");
  opacity: 0.025;
  pointer-events: none;
  z-index: 0;
}

.container {
  width: 100%;
  max-width: 520px;
  position: relative;
  z-index: 1;
  animation: fade-up 0.6s ease-out both;
}

@keyframes fade-up {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Header */
.header {
  text-align: center;
  margin-bottom: 40px;
}

.logo {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 28px;
}

.logo-mark {
  width: 38px;
  height: 38px;
  background: var(--accent);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-mono);
  font-size: 13px;
  font-weight: 500;
  color: #0d0d0b;
  letter-spacing: 0.05em;
}

.logo-name {
  font-family: var(--font-mono);
  font-size: 13px;
  color: var(--text-2);
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

.header h1 {
  font-family: var(--font-serif);
  font-size: clamp(32px, 6vw, 44px);
  font-weight: 400;
  line-height: 1.15;
  letter-spacing: -0.01em;
  margin-bottom: 12px;
  color: var(--text);
}

.header h1 em {
  font-style: italic;
  color: var(--accent);
}

.header p {
  font-size: 14px;
  color: var(--text-2);
  line-height: 1.6;
  max-width: 380px;
  margin: 0 auto;
}

/* Card */
.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 32px;
  backdrop-filter: blur(20px);
}

/* Fields */
.field {
  margin-bottom: 20px;
}

.field label {
  display: block;
  font-size: 11px;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-3);
  margin-bottom: 7px;
}

.field input,
.field select,
.field textarea {
  width: 100%;
  padding: 12px 14px;
  background: var(--surface-2);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  font-size: 14px;
  font-family: var(--font-sans);
  color: var(--text);
  outline: none;
  transition: border-color 0.15s, background 0.15s, box-shadow 0.15s;
  -webkit-appearance: none;
}

.field input::placeholder,
.field textarea::placeholder { color: var(--text-3); }

.field input:focus,
.field select:focus,
.field textarea:focus {
  border-color: var(--accent-border);
  background: #1a1a17;
  box-shadow: 0 0 0 3px var(--accent-dim);
}

.field select {
  background-image: url("data:image/svg+xml,%3Csvg width='12' height='8' viewBox='0 0 12 8' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%235a5955' stroke-width='1.5' stroke-linecap='round'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 14px center;
  padding-right: 36px;
  cursor: pointer;
}

.field select option { background: #1e1e1b; }

.field textarea { resize: vertical; min-height: 110px; line-height: 1.6; }

.field-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
}

/* Priority pills */
.priority-group {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.priority-opt {
  flex: 1;
  min-width: 80px;
}

.priority-opt input { display: none; }

.priority-opt label {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 9px 10px;
  border-radius: var(--radius);
  border: 1px solid var(--border);
  background: var(--surface-2);
  font-size: 12px;
  font-weight: 500;
  font-family: var(--font-sans);
  letter-spacing: 0;
  text-transform: none;
  color: var(--text-2);
  cursor: pointer;
  transition: all 0.12s;
}

.priority-opt label:hover { border-color: var(--border-hover); color: var(--text); }

.priority-opt input:checked + label {
  border-color: var(--sel-color);
  background: var(--sel-bg);
  color: var(--sel-color);
}

.priority-opt.low  { --sel-color: #6ee7b7; --sel-bg: rgba(110,231,183,0.1); }
.priority-opt.med  { --sel-color: #93c5fd; --sel-bg: rgba(147,197,253,0.1); }
.priority-opt.high { --sel-color: #fbbf24; --sel-bg: rgba(251,191,36,0.1); }
.priority-opt.urg  { --sel-color: #f87171; --sel-bg: rgba(248,113,113,0.1); }

/* Divider */
.divider {
  height: 1px;
  background: var(--border);
  margin: 24px 0;
}

/* Submit button */
.btn-submit {
  width: 100%;
  padding: 14px;
  background: var(--accent);
  color: #0d0d0b;
  border: none;
  border-radius: var(--radius);
  font-size: 14px;
  font-weight: 500;
  font-family: var(--font-sans);
  letter-spacing: 0.01em;
  cursor: pointer;
  transition: opacity 0.15s, transform 0.1s;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  position: relative;
  overflow: hidden;
}

.btn-submit:hover { opacity: 0.9; }
.btn-submit:active { transform: scale(0.99); }
.btn-submit:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }

/* Success state */
.success-state {
  display: none;
  text-align: center;
  padding: 12px 0;
  animation: fade-up 0.4s ease-out both;
}

.success-icon {
  width: 56px;
  height: 56px;
  background: var(--green-bg);
  border: 1px solid rgba(74,222,128,0.2);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
}

.success-state h2 {
  font-family: var(--font-serif);
  font-size: 28px;
  font-weight: 400;
  margin-bottom: 10px;
}

.success-state p {
  font-size: 14px;
  color: var(--text-2);
  line-height: 1.6;
  margin-bottom: 8px;
}

.ticket-ref {
  display: inline-block;
  font-family: var(--font-mono);
  font-size: 13px;
  color: var(--accent);
  background: var(--accent-dim);
  border: 1px solid var(--accent-border);
  padding: 4px 12px;
  border-radius: 20px;
  margin: 8px 0 20px;
}

.btn-another {
  padding: 10px 20px;
  background: transparent;
  border: 1px solid var(--border);
  border-radius: var(--radius);
  font-size: 13px;
  font-family: var(--font-sans);
  color: var(--text-2);
  cursor: pointer;
  transition: border-color 0.12s, color 0.12s;
}

.btn-another:hover { border-color: var(--border-hover); color: var(--text); }

/* Error */
.form-error {
  display: none;
  padding: 10px 14px;
  background: rgba(248,113,113,0.08);
  border: 1px solid rgba(248,113,113,0.2);
  border-radius: var(--radius);
  font-size: 13px;
  color: var(--red);
  margin-bottom: 16px;
}

/* Footer */
.footer {
  text-align: center;
  margin-top: 28px;
  font-size: 12px;
  color: var(--text-3);
}

.footer a { color: var(--text-3); text-decoration: none; border-bottom: 1px solid var(--border); padding-bottom: 1px; }
.footer a:hover { color: var(--text-2); }

/* Spinner */
.spinner-sm {
  width: 16px;
  height: 16px;
  border: 2px solid rgba(13,13,11,0.3);
  border-top-color: #0d0d0b;
  border-radius: 50%;
  animation: spin 0.7s linear infinite;
  flex-shrink: 0;
}

@keyframes spin { to { transform: rotate(360deg); } }

@media (max-width: 480px) {
  .card { padding: 24px 20px; }
  .field-row { grid-template-columns: 1fr; }
}
</style>
</head>
<body>
<div class="grain"></div>

<div class="container">
  <div class="header">
    <div class="logo">
      <div class="logo-mark">HD</div>
      <div class="logo-name">HelpDesk</div>
    </div>
    <h1>How can we <em>help?</em></h1>
    <p>Submit a support request and our team will get back to you as soon as possible.</p>
  </div>

  <div class="card">
    <div id="form-view">
      <div class="form-error" id="form-error"></div>

      <div class="field">
        <label>Your name <span style="color:#f87171">*</span></label>
        <input type="text" id="f-name" placeholder="Full name" autocomplete="name">
      </div>

      <div class="field">
        <label>Email address <span style="color:#f87171">*</span></label>
        <input type="email" id="f-email" placeholder="you@company.com" autocomplete="email">
      </div>

      <div class="divider"></div>

      <div class="field">
        <label>Issue summary <span style="color:#f87171">*</span></label>
        <input type="text" id="f-title" placeholder="Brief description of the problem">
      </div>

      <div class="field-row">
        <div class="field">
          <label>Category</label>
          <select id="f-category">
            <option value="Other">Other</option>
            <option value="Hardware">Hardware</option>
            <option value="Software">Software</option>
            <option value="Network">Network</option>
            <option value="Account">Account</option>
          </select>
        </div>
        <div class="field">
          <label>Priority</label>
          <div class="priority-group">
            <div class="priority-opt low">
              <input type="radio" name="priority" id="p-low" value="Low">
              <label for="p-low">Low</label>
            </div>
            <div class="priority-opt med">
              <input type="radio" name="priority" id="p-med" value="Medium" checked>
              <label for="p-med">Medium</label>
            </div>
            <div class="priority-opt high">
              <input type="radio" name="priority" id="p-high" value="High">
              <label for="p-high">High</label>
            </div>
            <div class="priority-opt urg">
              <input type="radio" name="priority" id="p-urg" value="Urgent">
              <label for="p-urg">Urgent</label>
            </div>
          </div>
        </div>
      </div>

      <div class="field">
        <label>Description <span style="color:#f87171">*</span></label>
        <textarea id="f-desc" placeholder="Describe the issue in detail — what happened, what you expected, any error messages…"></textarea>
      </div>

      <button class="btn-submit" id="submit-btn" onclick="submitTicket()">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
        Submit Request
      </button>
    </div>

    <div class="success-state" id="success-view">
      <div class="success-icon">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#4ade80" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
      </div>
      <h2>Request received</h2>
      <p>Your ticket has been created.</p>
      <div class="ticket-ref" id="ticket-ref">TK-000</div>
      <p>Our team will review your request shortly. You'll hear from us at <strong id="confirm-email"></strong>.</p>
      <br>
      <button class="btn-another" onclick="resetForm()">Submit another request</button>
    </div>
  </div>

  <div class="footer">
    Powered by <a href="#">HelpDesk</a> &nbsp;·&nbsp; Average response time: &lt;4 hours
  </div>
</div>

<script>
const SUPABASE_URL = 'https://xphtitfasgstjvqkkdvs.supabase.co/rest/v1';
const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InhwaHRpdGZhc2dzdGp2cWtrZHZzIiwicm9sZSI6ImFub24iLCJpYXQiOjE3Nzc5MTQzMDQsImV4cCI6MjA5MzQ5MDMwNH0.sjjsfDCeiEWPih2f3eH5rShhvEZZXgS3ApcSy0B0S-M';

function showError(msg) {
  const el = document.getElementById('form-error');
  el.textContent = msg;
  el.style.display = 'block';
  el.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
}

function hideError() {
  document.getElementById('form-error').style.display = 'none';
}

async function getNextTicketId() {
  const resp = await fetch(`${SUPABASE_URL}/tickets?select=id`, {
    headers: { 'apikey': SUPABASE_KEY, 'Authorization': `Bearer ${SUPABASE_KEY}` }
  });
  const data = await resp.json();
  const nums = (data || []).map(t => parseInt((t.id || '').replace(/\D/g, ''))).filter(n => !isNaN(n));
  const next = nums.length ? Math.max(...nums) + 1 : 1;
  return 'TK-' + String(next).padStart(3, '0');
}

async function submitTicket() {
  hideError();

  const name     = document.getElementById('f-name').value.trim();
  const email    = document.getElementById('f-email').value.trim();
  const title    = document.getElementById('f-title').value.trim();
  const desc     = document.getElementById('f-desc').value.trim();
  const category = document.getElementById('f-category').value;
  const priority = document.querySelector('input[name="priority"]:checked')?.value || 'Medium';

  if (!name)  return showError('Please enter your name.');
  if (!email || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) return showError('Please enter a valid email address.');
  if (!title) return showError('Please describe your issue briefly.');
  if (!desc)  return showError('Please provide a detailed description.');

  const btn = document.getElementById('submit-btn');
  btn.disabled = true;
  btn.innerHTML = '<div class="spinner-sm"></div> Submitting…';

  try {
    const id = await getNextTicketId();

    const ticket = {
      id,
      title,
      requester: name,
      requester_email: email,
      priority,
      status: 'open',
      category,
      assigned: '',
      created: new Date().toISOString().slice(0, 10),
      description: desc,
      source: 'form'
    };

    const resp = await fetch(`${SUPABASE_URL}/tickets`, {
      method: 'POST',
      headers: {
        'apikey': SUPABASE_KEY,
        'Authorization': `Bearer ${SUPABASE_KEY}`,
        'Content-Type': 'application/json',
        'Prefer': 'return=minimal'
      },
      body: JSON.stringify(ticket)
    });

    if (!resp.ok) {
      const err = await resp.json().catch(() => ({}));
      throw new Error(err.message || 'Submission failed');
    }

    // Show success
    document.getElementById('ticket-ref').textContent = id;
    document.getElementById('confirm-email').textContent = email;
    document.getElementById('form-view').style.display = 'none';
    document.getElementById('success-view').style.display = 'block';

  } catch(e) {
    showError('Something went wrong: ' + e.message + '. Please try again.');
    btn.disabled = false;
    btn.innerHTML = '<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg> Submit Request';
  }
}

function resetForm() {
  document.getElementById('f-name').value = '';
  document.getElementById('f-email').value = '';
  document.getElementById('f-title').value = '';
  document.getElementById('f-desc').value = '';
  document.getElementById('f-category').value = 'Other';
  document.querySelector('input[value="Medium"]').checked = true;
  document.getElementById('form-view').style.display = 'block';
  document.getElementById('success-view').style.display = 'none';
  document.getElementById('submit-btn').disabled = false;
  document.getElementById('submit-btn').innerHTML = '<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg> Submit Request';
  hideError();
}

// Enter key on inputs moves to next field
document.addEventListener('keydown', e => {
  if (e.key === 'Enter' && e.target.tagName === 'INPUT') {
    e.preventDefault();
    const inputs = [...document.querySelectorAll('input:not([type=radio]), select, textarea')];
    const idx = inputs.indexOf(e.target);
    if (idx < inputs.length - 1) inputs[idx + 1].focus();
    else submitTicket();
  }
});
</script>
</body>
</html>
