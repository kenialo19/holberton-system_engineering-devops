# 0x1A. Application server
<h2>Concepts</h2>

  <div class="panel panel-default">
    <div class="panel-body">
      <p>
        <em>For this project, students are expected to look at these concepts:</em>
      </p>

<ul>
          <li>
            <a href="/concepts/17">Web Server</a>
          </li>
          <li>
            <a href="/concepts/67">Server</a>
          </li>
          <li>
            <a href="/concepts/68">Web stack debugging</a>
          </li>
      </ul>
    </div>
  </div>


<div class="well clean" id="project-description">
  <p><img src="https://holbertonintranet.s3.amazonaws.com/uploads/medias/2018/9/c7d1ed0a2e10d1b4e9b3.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOU5BHMTQX4%2F20220223%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220223T224851Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=2c433a838e1ff2c81b352ee186d341eadfea207b02f1e06d49554deffa40a82a" alt="" style="" /></p>

<h2>Background Context</h2>

<p><a href="https://youtu.be/pSrKT7m4Ego" target="_blank"><img src="https://holbertonintranet.s3.amazonaws.com/uploads/medias/2019/6/2ea1058f813d42c61f48.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOU5BHMTQX4%2F20220223%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220223T224851Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=647ece1fd8058e4979c03edfbe323bb6ccd96b3274017d8524ee2e3b2287f8ac" alt="" style="" /></a></p>

<p>Your web infrastructure is already serving web pages via <code>Nginx</code> that you installed in your <a href="/rltoken/RrbqMLWOJUyVaWdXsnpvXw" title="first web stack project" target="_blank">first web stack project</a>. While a web server can also serve dynamic content, this task is usually given to an application server. In this project you will add this piece to your infrastructure, plug it to your <code>Nginx</code> and make is serve your Airbnb clone project.</p>

<h2>Resources</h2>

<p><strong>Read or watch</strong>:</p>

<ul>
<li><a href="/rltoken/RerpYBxsgrpIorHjbDgulw" title="Application server vs web server" target="_blank">Application server vs web server</a> </li>
<li><a href="/rltoken/uosy5QXdMbDPA1tFTR1eoA" title="How to Serve a Flask Application with Gunicorn and Nginx on Ubuntu 16.04" target="_blank">How to Serve a Flask Application with Gunicorn and Nginx on Ubuntu 16.04</a> (As mentioned in the video, do <strong>not</strong> install Gunicorn using <code>virtualenv</code>, just install everything globally)</li>
<li><a href="/rltoken/QTnnkj6vfQV9ovW_eYWWDQ" title="Running Gunicorn" target="_blank">Running Gunicorn</a> </li>
<li><a href="/rltoken/whE8do28ZiJJoJLyb1ACwA" title="Be careful with the way Flask manages slash" target="_blank">Be careful with the way Flask manages slash</a> in <a href="/rltoken/JLjrXD4MLS3rUkQr5QyxtA" title="route" target="_blank">route</a>  - <code>strict_slashes</code></li>
<li><a href="/rltoken/rldSTo2ZFS8clyTHH3SyBg" title="Upstart documentation" target="_blank">Upstart documentation</a> </li>
</ul>

<h2>Requirements</h2>

<h3>General</h3>

<ul>
<li>A <code>README.md</code> file, at the root of the folder of the project, is mandatory</li>
<li>Everything Python-related must be done using <code>python3</code></li>
<li>All config files must have comments</li>
</ul>

<h3>Bash Scripts</h3>

<ul>
<li>All your files will be interpreted on Ubuntu 16.04 LTS</li>
<li>All your files should end with a new line</li>
<li>All your Bash script files must be executable</li>
<li>Your Bash script must pass <code>Shellcheck</code> (version <code>0.3.7-5~ubuntu16.04.1</code> via <code>apt-get</code>) without any error</li>
<li>The first line of all your Bash scripts should be exactly <code>#!/usr/bin/env bash</code></li>
<li>The second line of all your Bash scripts should be a comment explaining what is the script doing</li>
</ul>

</div>
