---
title: Highlighter demo
layout: default
---

highlight-lisp demo
===================

HI!! Tired of *boring and outdated* looking Lisp code scaring away your website's
visitors, costing you millions per year? Is the wife nagging you endlessly? Did
some schmuck get *your* promotion at work?

Worry no more, your Common Lisp code highlighting woes are over!

<!--
<input
 type="button"
 value="Click to CHANGE YOUR LIFE FOREVER!"
 id="highlight_btn"
 onclick="do_highlight();"
/> **!!!WARNING!!!** There is no going back!
-->

<ul class="themes clear">
    <li><strong>Themes</strong></li>
    <li><a href="#github" onclick="switch_theme('github');">Github</a></li>
    <li><a href="#dark" onclick="switch_theme('dark');">Dark</a></li>
</ul>

<pre><code class="lisp">;; known globals
*read-base*
(let* ((*package* nil)) 'random-symbol)   ; let/let*/lambda are "special"

;; known functions, unknown globals
(when (<= 17.69 (get-value))
  (incf *my-global-lol*))

;; number tests
;; all have class "number", but depending on type have integer, float, hex, binary
'(80 -69.4 +5 822342.287 #xf40d #b0101)

;; t/nil + strings
(format t "highlight-lisp.js sucksp: ~a~%" nil)

;; testing lambda-list specials (&key, &body, etc), multi-line strings,
;; constants, symbols, keywords
(defun test-me (lol &key omg (lol 'wtf))
  (let ((*global* 'ur-mom)
        (strings "r pretty kewl LOL")
        (multi-line-strings "can be kewl
            as well")
        (+my-constant+ "wait, constants don't change!!"))
    (make-instance 'error :message "OMG ERROR!!!")))

;; known vs unknown #'functions
(make-hash-table :test #'equal)
(make-hash-table :test #'equalzz)

;; testing known keywords (have class "known" as well as "keyword")
(loop for x being the :hash-keys of my-hash-table collect x)</code></pre>

<script type="text/javascript">
function do_highlight() {
    HighlightLisp.highlight_auto();
    document.getElementById('highlight_btn').disabled=true;
}
function switch_theme(name) {
    var style = document.getElementById('hl-theme');
    if(!style) return;
    style.href = '/highlight-lisp/js/highlight-lisp/themes/'+name+'.css';
}
do_highlight();
</script>

