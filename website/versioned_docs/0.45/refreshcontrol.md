---
id: refreshcontrol
title: refreshcontrol
---
<a id="content"></a><h1><a class="anchor" name="refreshcontrol"></a>RefreshControl <a class="hash-link" href="docs/refreshcontrol.html#refreshcontrol">#</a></h1><div><div><p>This component is used inside a ScrollView or ListView to add pull to refresh
functionality. When the ScrollView is at <code>scrollY: 0</code>, swiping down
triggers an <code>onRefresh</code> event.</p><h3><a class="anchor" name="usage-example"></a>Usage example <a class="hash-link" href="docs/refreshcontrol.html#usage-example">#</a></h3><div class="prism language-javascript">class <span class="token class-name">RefreshableList</span> extends <span class="token class-name">Component</span> <span class="token punctuation">{</span>
  <span class="token function">constructor<span class="token punctuation">(</span></span>props<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token function">super<span class="token punctuation">(</span></span>props<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span>state <span class="token operator">=</span> <span class="token punctuation">{</span>
      refreshing<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span>
    <span class="token punctuation">}</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>

  <span class="token function">_onRefresh<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>refreshing<span class="token punctuation">:</span> <span class="token boolean">true</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token function">fetchData<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">then<span class="token punctuation">(</span></span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
      <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>refreshing<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;ListView
        refreshControl<span class="token operator">=</span><span class="token punctuation">{</span>
          &lt;RefreshControl
            refreshing<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>refreshing<span class="token punctuation">}</span>
            onRefresh<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onRefresh<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">)</span><span class="token punctuation">}</span>
          <span class="token operator">/</span><span class="token operator">&gt;</span>
        <span class="token punctuation">}</span>
        <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
      <span class="token operator">&gt;</span>
      <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
      &lt;<span class="token operator">/</span>ListView<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
  <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
<span class="token punctuation">}</span></div><p><strong>Note:</strong> <code>refreshing</code> is a controlled prop, this is why it needs to be set to true
in the <code>onRefresh</code> function otherwise the refresh indicator will stop immediately.</p></div><h3><a class="anchor" name="props"></a>Props <a class="hash-link" href="docs/refreshcontrol.html#props">#</a></h3><div class="props"><div class="prop"><h4 class="propTitle"><a class="anchor" name="viewproptypes"></a><a href="docs/viewproptypes.html#props">ViewPropTypes props...</a> <a class="hash-link" href="docs/refreshcontrol.html#viewproptypes">#</a></h4></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="onrefresh"></a>onRefresh?: <span class="propType">PropTypes.func</span> <a class="hash-link" href="docs/refreshcontrol.html#onrefresh">#</a></h4><div><p>Called when the view starts refreshing.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="refreshing"></a>refreshing?: <span class="propType">PropTypes.bool.isRequired</span> <a class="hash-link" href="docs/refreshcontrol.html#refreshing">#</a></h4><div><p>Whether the view should be indicating an active refresh.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="colors"></a><span class="platform">android</span>colors?: <span class="propType">PropTypes.arrayOf(ColorPropType)</span> <a class="hash-link" href="docs/refreshcontrol.html#colors">#</a></h4><div><p>The colors (at least one) that will be used to draw the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="enabled"></a><span class="platform">android</span>enabled?: <span class="propType">PropTypes.bool</span> <a class="hash-link" href="docs/refreshcontrol.html#enabled">#</a></h4><div><p>Whether the pull to refresh functionality is enabled.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="progressbackgroundcolor"></a><span class="platform">android</span>progressBackgroundColor?: <span class="propType"><a href="docs/colors.html">color</a></span> <a class="hash-link" href="docs/refreshcontrol.html#progressbackgroundcolor">#</a></h4><div><p>The background color of the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="progressviewoffset"></a><span class="platform">android</span>progressViewOffset?: <span class="propType">PropTypes.number</span> <a class="hash-link" href="docs/refreshcontrol.html#progressviewoffset">#</a></h4><div><p>Progress view top offset</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="size"></a><span class="platform">android</span>size?: <span class="propType">PropTypes.oneOf([RefreshLayoutConsts.SIZE.DEFAULT, RefreshLayoutConsts.SIZE.LARGE])</span> <a class="hash-link" href="docs/refreshcontrol.html#size">#</a></h4><div><p>Size of the refresh indicator, see RefreshControl.SIZE.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="tintcolor"></a><span class="platform">ios</span>tintColor?: <span class="propType"><a href="docs/colors.html">color</a></span> <a class="hash-link" href="docs/refreshcontrol.html#tintcolor">#</a></h4><div><p>The color of the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="title"></a><span class="platform">ios</span>title?: <span class="propType">PropTypes.string</span> <a class="hash-link" href="docs/refreshcontrol.html#title">#</a></h4><div><p>The title displayed under the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="titlecolor"></a><span class="platform">ios</span>titleColor?: <span class="propType"><a href="docs/colors.html">color</a></span> <a class="hash-link" href="docs/refreshcontrol.html#titlecolor">#</a></h4><div><p>Title color.</p></div></div></div></div><p class="edit-page-block">You can <a target="_blank" href="https://github.com/facebook/react-native/blob/master/Libraries/Components/RefreshControl/RefreshControl.js">edit the content above on GitHub</a> and send us a pull request!</p><div class="docs-prevnext"><a class="docs-prev" href="docs/progressviewios.html#content">← Prev</a><a class="docs-next" href="docs/scrollview.html#content">Next →</a></div>