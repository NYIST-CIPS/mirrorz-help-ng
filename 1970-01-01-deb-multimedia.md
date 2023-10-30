---
category: help
layout: help
mirrorid: debian-multimedia
---

<!-- 本 markdown 从 tuna/mirrorz-help-ng 自动生成，如需修改请参阅该仓库 -->

<style>.z-help tmpl { display: none }</style>

<div class="z-wrap">
    <form class="z-form z-global" onchange="form_update(null)" onsubmit="return false">
        <div>
            <label for="e0a5cecb">线路选择</label>
            <select id="e0a5cecb" name="host">
                <option selected="selected" value="{{ site.url }}">自动</option>
                <option value="{{ site.urlv4 }}">IPv4</option>
                <option value="{{ site.urlv6 }}">IPv6</option>
            </select>
        </div>
        <div>
            <input id="144d763c" name="_scheme" type="checkbox" checked>
            <label for="144d763c">是否使用 HTTPS</label>
        </div>
        <div>
            <input id="4659e7da" name="_sudo" type="checkbox">
            <label for="4659e7da">是否使用 sudo</label>
        </div>
    </form>
</div>
{% raw %}
<div class="z-help"><h1>Deb Multimedia 软件仓库</h1>
<h2>项目简介</h2>
<p>本项目是 Debian 第三方多媒体软件源。</p>
<p>该项目以前的名字为 Debian Multimedia，现改名为 Deb Multimedia。注意这不是 Debian 官方项目，是为 deb-multimedia.org 的镜像，与 Debian 官方的 Multimedia 小组的区别见 https://wiki.debian.org/DebianMultimedia/FAQ 。</p>
<h2>使用方法</h2>
<p>在 <code>/etc/apt/sources.list</code> 中加入</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"><div><label for="1eeafc80" title>Debian 系统版本</label><select id="1eeafc80" name="release" title><option value="bookworm">Debian 12 (bookworm)</option><option value="bullseye">Debian 11 (bullseye)</option><option value="buster">Debian 10 (buster)</option><option value="stretch">Debian 9 (stretch)</option><option value="jessie">Debian 8 (jessie)</option><option value="testing">testing</option><option value="sid">sid</option></select></div><div><input id="26949fd4" name="src" title="源码源通常用于构建和调试，开启后影响更新速度" type="checkbox"/><label for="26949fd4" title="源码源通常用于构建和调试，开启后影响更新速度">启用源码源</label></div></form><pre class="z-code"></pre></div><tmpl z-append="" z-input="release src" z-path="/etc/apt/sources.list">
deb {{endpoint}}/ {{release}} main non-free
{{src}}deb-src {{endpoint}}/ {{release}} main non-free
{{#backports}}
deb {{endpoint}}/ {{release}}-backports main
{{src}}deb-src {{endpoint}}/ {{release}}-backports main
{{/backports}}
</tmpl>
<p>更改完 <code>sources.list</code> 文件后请导入 deb-multimedia-keyring ，然后更新索引以生效。</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
wget {{endpoint}}/pool/main/d/deb-multimedia-keyring/deb-multimedia-keyring_2016.8.1_all.deb
{{sudo}}dpkg -i deb-multimedia-keyring_2016.8.1_all.deb
{{sudo}}apt-get update
</tmpl><script id="z-config" type="application/x-mirrorz-help">eyJfIjogIkRlYiBNdWx0aW1lZGlhIFx1OGY2Zlx1NGVmNlx1NGVkM1x1NWU5MyIsICJibG9jayI6IFsiaW50cm8iLCAidXNhZ2UiXSwgImlucHV0IjogeyJyZWxlYXNlIjogeyJfIjogIkRlYmlhbiBcdTdjZmJcdTdlZGZcdTcyNDhcdTY3MmMiLCAib3B0aW9uIjogeyJib29rd29ybSI6IHsiXyI6ICJEZWJpYW4gMTIgKGJvb2t3b3JtKSJ9LCAiYnVsbHNleWUiOiB7Il8iOiAiRGViaWFuIDExIChidWxsc2V5ZSkiLCAiYmFja3BvcnRzIjogdHJ1ZX0sICJidXN0ZXIiOiB7Il8iOiAiRGViaWFuIDEwIChidXN0ZXIpIiwgImJhY2twb3J0cyI6IHRydWV9LCAic3RyZXRjaCI6IHsiXyI6ICJEZWJpYW4gOSAoc3RyZXRjaCkiLCAiYmFja3BvcnRzIjogdHJ1ZX0sICJqZXNzaWUiOiB7Il8iOiAiRGViaWFuIDggKGplc3NpZSkiLCAiYmFja3BvcnRzIjogdHJ1ZX0sICJ0ZXN0aW5nIjogbnVsbCwgInNpZCI6IG51bGx9fSwgInNyYyI6IHsiXyI6ICJcdTU0MmZcdTc1MjhcdTZlOTBcdTc4MDFcdTZlOTAiLCAibm90ZSI6ICJcdTZlOTBcdTc4MDFcdTZlOTBcdTkwMWFcdTVlMzhcdTc1MjhcdTRlOGVcdTY3ODRcdTVlZmFcdTU0OGNcdThjMDNcdThiZDVcdWZmMGNcdTVmMDBcdTU0MmZcdTU0MGVcdTVmNzFcdTU0Y2RcdTY2ZjRcdTY1YjBcdTkwMWZcdTVlYTYiLCAidHJ1ZSI6ICIiLCAiZmFsc2UiOiAiIyAifX0sICJtaXJyb3JpZCI6ICJkZWJpYW4tbXVsdGltZWRpYSIsICJuYW1lIjogImRlYi1tdWx0aW1lZGlhIn0=</script>
</div>

{% endraw %}

<script src="/static/js/mustache.js?{{ site.data['hash'] }}"></script>
<script src="/static/js/zdocs.js?{{ site.data['hash'] }}"></script>