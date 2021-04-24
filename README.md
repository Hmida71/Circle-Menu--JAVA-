#-------------------Circle-Menu--JAVA-------------------#

<img src="https://raw.githubusercontent.com/Ramotion/circle-menu-android/master/preview.gif" alt="circle" width="480px" height="360px" />

#a-simple-elegant-ui-menu-with-a-circular-layout-and-material-design-animations !!
<hr/>
<ul>
<li>Android 4.1 Jelly Bean (API lvl 16) or greater</li>
<li>Your favorite IDE</li>
</ul>
<hr/>
# Installation :
​Just download the package from here and add it to your project classpath, or just use the maven repo:

Gradle:
<pre>implementation <span class="pl-s"><span class="pl-pds">'</span>com.ramotion.circlemenu:circle-menu:0.3.2<span class="pl-pds">'</span></span></pre>
SBT:
<pre>libraryDependencies <span class="pl-k">+</span><span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>com.ramotion.circlemenu<span class="pl-pds">"</span></span> <span class="pl-k">%</span> <span class="pl-s"><span class="pl-pds">"</span>circle-menu<span class="pl-pds">"</span></span> <span class="pl-k">%</span> <span class="pl-s"><span class="pl-pds">"</span>0.3.2<span class="pl-pds">"</span></span></pre>
Maven:
<pre>&lt;<span class="pl-ent">dependency</span>&gt;
	&lt;<span class="pl-ent">groupId</span>&gt;com.ramotion.circlemenu&lt;/<span class="pl-ent">groupId</span>&gt;
	&lt;<span class="pl-ent">artifactId</span>&gt;circle-menu&lt;/<span class="pl-ent">artifactId</span>&gt;
	&lt;<span class="pl-ent">version</span>&gt;0.3.2&lt;/<span class="pl-ent">version</span>&gt;
&lt;/<span class="pl-ent">dependency</span>&gt;</pre>

<hr/>
# Basic usage :

Place the CircleMenuView in your layout and set the icons and colors of the buttons, as shown below.
<pre>app:button_colors="@array/colors"
app:button_icons="@array/icons"</pre>
<p>Example of arrays <code>colors</code> and <code>icons</code> in <code>res\values\buttons.xml</code>:</p>
<pre>&lt;?<span class="pl-ent">xml</span><span class="pl-e"> version</span>=<span class="pl-s"><span class="pl-pds">"</span>1.0<span class="pl-pds">"</span></span><span class="pl-e"> encoding</span>=<span class="pl-s"><span class="pl-pds">"</span>utf-8<span class="pl-pds">"</span></span>?&gt;
&lt;<span class="pl-ent">resources</span>&gt;
    &lt;<span class="pl-ent">array</span> <span class="pl-e">name</span>=<span class="pl-s"><span class="pl-pds">"</span>icons<span class="pl-pds">"</span></span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@drawable/ic_home_white_24dp&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@drawable/ic_search_white_24dp&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@drawable/ic_notifications_white_24dp&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@drawable/ic_settings_white_24dp&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@drawable/ic_place_white_24dp&lt;/<span class="pl-ent">item</span>&gt;
    &lt;/<span class="pl-ent">array</span>&gt;
    &lt;<span class="pl-ent">array</span> <span class="pl-e">name</span>=<span class="pl-s"><span class="pl-pds">"</span>colors<span class="pl-pds">"</span></span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@android:color/holo_blue_light&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@android:color/holo_green_dark&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@android:color/holo_red_light&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@android:color/holo_purple&lt;/<span class="pl-ent">item</span>&gt;
        &lt;<span class="pl-ent">item</span>&gt;@android:color/holo_orange_light&lt;/<span class="pl-ent">item</span>&gt;
    &lt;/<span class="pl-ent">array</span>&gt;
&lt;/<span class="pl-ent">resources</span>&gt;</pre>
Or use the constructor

<pre>CircleMenuView(<span class="pl-k">@NonNull</span> <span class="pl-smi">Context</span> context, <span class="pl-k">@NonNull</span> <span class="pl-k">List&lt;<span class="pl-smi">Integer</span>&gt;</span> icons, <span class="pl-k">@NonNull</span> <span class="pl-k">List&lt;<span class="pl-smi">Integer</span>&gt;</span> colors)</pre>
to add CircleMenuView and configure the buttons programmatically (in the code).

Next, connect the event handler CircleMenuView.EventListener as shown below, and override the methods you need.
<pre><span class="pl-k">final</span> <span class="pl-smi">CircleMenuView</span> menu <span class="pl-k">=</span> (<span class="pl-smi">CircleMenuView</span>) findViewById(<span class="pl-smi">R</span><span class="pl-k">.</span>id<span class="pl-k">.</span>circle_menu);
menu<span class="pl-k">.</span>setEventListener(<span class="pl-k">new</span> <span class="pl-smi">CircleMenuView</span>.<span class="pl-smi">EventListener</span>() {
    <span class="pl-k">@Override</span>
    <span class="pl-k">public</span> <span class="pl-k">void</span> <span class="pl-en">onMenuOpenAnimationStart</span>(<span class="pl-k">@NonNull</span> <span class="pl-smi">CircleMenuView</span> <span class="pl-v">view</span>) {
        <span class="pl-smi">Log</span><span class="pl-k">.</span>d(<span class="pl-s"><span class="pl-pds">"</span>D<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>onMenuOpenAnimationStart<span class="pl-pds">"</span></span>);
    }

    <span class="pl-k">@Override</span>
    <span class="pl-k">public</span> <span class="pl-k">void</span> <span class="pl-en">onMenuOpenAnimationEnd</span>(<span class="pl-k">@NonNull</span> <span class="pl-smi">CircleMenuView</span> <span class="pl-v">view</span>) {
        <span class="pl-smi">Log</span><span class="pl-k">.</span>d(<span class="pl-s"><span class="pl-pds">"</span>D<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>onMenuOpenAnimationEnd<span class="pl-pds">"</span></span>);
    }

    <span class="pl-k">@Override</span>
    <span class="pl-k">public</span> <span class="pl-k">void</span> <span class="pl-en">onMenuCloseAnimationStart</span>(<span class="pl-k">@NonNull</span> <span class="pl-smi">CircleMenuView</span> <span class="pl-v">view</span>) {
        <span class="pl-smi">Log</span><span class="pl-k">.</span>d(<span class="pl-s"><span class="pl-pds">"</span>D<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>onMenuCloseAnimationStart<span class="pl-pds">"</span></span>);
    }

    <span class="pl-k">@Override</span>
    <span class="pl-k">public</span> <span class="pl-k">void</span> <span class="pl-en">onMenuCloseAnimationEnd</span>(<span class="pl-k">@NonNull</span> <span class="pl-smi">CircleMenuView</span> <span class="pl-v">view</span>) {
        <span class="pl-smi">Log</span><span class="pl-k">.</span>d(<span class="pl-s"><span class="pl-pds">"</span>D<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>onMenuCloseAnimationEnd<span class="pl-pds">"</span></span>);
    }

    <span class="pl-k">@Override</span>
    <span class="pl-k">public</span> <span class="pl-k">void</span> <span class="pl-en">onButtonClickAnimationStart</span>(<span class="pl-k">@NonNull</span> <span class="pl-smi">CircleMenuView</span> <span class="pl-v">view</span>, <span class="pl-k">int</span> <span class="pl-v">index</span>) {
        <span class="pl-smi">Log</span><span class="pl-k">.</span>d(<span class="pl-s"><span class="pl-pds">"</span>D<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>onButtonClickAnimationStart| index: <span class="pl-pds">"</span></span> <span class="pl-k">+</span> index);
    }

    <span class="pl-k">@Override</span>
    <span class="pl-k">public</span> <span class="pl-k">void</span> <span class="pl-en">onButtonClickAnimationEnd</span>(<span class="pl-k">@NonNull</span> <span class="pl-smi">CircleMenuView</span> <span class="pl-v">view</span>, <span class="pl-k">int</span> <span class="pl-v">index</span>) {
        <span class="pl-smi">Log</span><span class="pl-k">.</span>d(<span class="pl-s"><span class="pl-pds">"</span>D<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>onButtonClickAnimationEnd| index: <span class="pl-pds">"</span></span> <span class="pl-k">+</span> index);
    }
});</pre>
<p>You can use <code>open(boolean animate)</code> and <code>close(boolean animate)</code> methods,
to open and close menu programmatically</p>
<p>Here are the attributes you can specify through XML or related setters:</p>
<ul>
<li><code>button_icons</code> - Array of buttons icons.</li>
<li><code>button_colors</code> - Array of buttons colors.</li>
<li><code>icon_menu</code> - Menu default icon.</li>
<li><code>icon_close</code> - Menu closed icon.</li>
<li><code>icon_color</code> - Menu icon color.</li>
<li><code>duration_ring</code> - Ring effect duration.</li>
<li><code>duration_open</code> - Menu opening animation duration.</li>
<li><code>duration_close</code> - Menu closing animation duration.</li>
<li><code>distance</code> - Distance between center button and buttons</li>
</ul>

