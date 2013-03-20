---
title: Highlighter demo
layout: default
---

highlight-lisp demo
===================

<script type="text/javascript">
function do_highlight() {
    HighlightLisp.highlight_auto();
}
</script>
<input type="button" id="highlight_btn" value="Click me to highlight!" onclick="do_highlight()" />

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
;;
(defun test-me (lol &key omg (lol 'wtf))
  (let ((*global* 'ur-mom)
        (strings "r pretty kewl LOL")
        (multi-line-strings "can be badass
            as well")
        (+my-constant+ "wait, constants don't change!!"))
    (make-instance 'error :message "YOU SUCK!!!")))

;; known vs unknown #'functions
(make-hash-table :test #'equal)
(make-hash-table :test #'equalzz)

;; testing known keywords (have class "known" as well as "keyword")
(loop for x being the :hash-keys of my-hash-table collect x)</code></pre>

