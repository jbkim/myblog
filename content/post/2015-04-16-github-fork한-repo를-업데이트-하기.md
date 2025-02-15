---
title: 'Github – Fork한  repo를 업데이트 하기'
author: openmicrolab
type: post
date: 2015-04-16T07:55:25+00:00
url: /github-fork한-repo를-업데이트-하기/
categories:
  - Infomation
  - Development
tags:
  - github

---
<p style="text-align: justify;">
  Github에서  Fork한  repo를 원본과 싱크를 맞추어 업데이트하려면&#8230; Fork한 repo를 셋업하고 local clone을 만든다.
</p>

<pre class="command-line"><span class="command">$ git clone https://github.com/<em>YOUR-USERNAME</em>/xxxx.git</span></pre>

<p style="text-align: justify;">
  그리고 이것을 original과 sync하려면 먼저 리모트 설정하고 패치를 하면 된다. local clone의 위치로 이동을 하고..
</p>

<pre class="command-line"><span class="command">$ git remote add upstream https://github.com/xxxx/xxxx.git
</span></pre>

확인

<pre class="command-line"><span class="command">$ git remote -v</span>
<span class="output"># origin    https://github.com/<em>YOUR_USERNAME</em>/<em>YOUR_FORK</em>.git (fetch)</span>
<span class="output"># origin    https://github.com/<em>YOUR_USERNAME</em>/<em>YOUR_FORK</em>.git (push)</span>
<span class="output"># upstream  https://github.com/<em>ORIGINAL_OWNER</em>/<em>ORIGINAL_REPOSITORY</em>.git (fetch)</span>
<span class="output"># upstream  https://github.com/<em>ORIGINAL_OWNER</em>/<em>ORIGINAL_REPOSITORY</em>.git (push)
</span></pre>

패치

<pre class="command-line"><span class="command">$ git fetch upstream</span>
<span class="output"># remote: Counting objects: 75, done.</span>
<span class="output"># remote: Compressing objects: 100% (53/53), done.</span>
<span class="output"># remote: Total 62 (delta 27), reused 44 (delta 9)</span>
<span class="output"># Unpacking objects: 100% (62/62), done.</span>
<span class="output"># From https://github.com/<em>ORIGINAL_OWNER</em>/<em>ORIGINAL_REPOSITORY</em></span>
<span class="output">#  * [new branch]      master     -&gt; upstream/master
</span></pre>

체크아웃

<pre class="command-line"><span class="command">$ git checkout -b master</span>
<span class="output"># Switched to branch 'master'</span></pre>

참고

<a href="https://help.github.com/articles/fork-a-repo/" target="_blank">https://help.github.com/articles/fork-a-repo/</a>

<a href="https://help.github.com/articles/syncing-a-fork/" target="_blank">https://help.github.com/articles/syncing-a-fork/</a>