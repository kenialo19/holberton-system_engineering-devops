# 0x0F. Load balancer
<h2>Concepts</h2>

  <div class="panel panel-default">
    <div class="panel-body">
      <p>
        <em>For this project, students are expected to look at these concepts:</em>
      </p>

<ul>
          <li>
            <a href="/concepts/46">Load balancer</a>
          </li>
          <li>
            <a href="/concepts/68">Web stack debugging</a>
          </li>
      </ul>
    </div>
  </div>


      <div class="well clean" id="project-description">
  <p><img src="https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/275/qfdked8.png" alt="" style="" /></p>

<h2>Background Context</h2>

<p>You have been given 2 additional servers:</p>

<ul>
<li>gc-[STUDENT_ID]-web-02-XXXXXXXXXX</li>
<li>gc-[STUDENT_ID]-lb-01-XXXXXXXXXX</li>
</ul>

<p>Let&rsquo;s improve our web stack so that there is <a href="/rltoken/QiOC_I-8BeV4aNExIucC9Q" title="redundancy" target="_blank">redundancy</a> for our web servers. This will allow us to be able to accept more traffic by doubling the number of web servers, and to make our infrastructure more reliable. If one web server fails, we will still have a second one to handle requests.</p>

<p>For this project, you will need to write Bash scripts to automate your work. All scripts must be designed to configure a brand new Ubuntu server to match the task requirements.</p>

<h2>Resources</h2>

<p><strong>Read or watch</strong>:</p>

<ul>
<li><a href="/rltoken/ngIXarEyu8jZwOL3Y30PLQ" title="Introduction to load-balancing and HAproxy" target="_blank">Introduction to load-balancing and HAproxy</a> </li>
<li><a href="/rltoken/v32JmcDrSiOnFBfqzXvs_Q" title="HTTP header" target="_blank">HTTP header</a> </li>
<li><a href="/rltoken/BXGrW_6ocecWaOJb7OK_WA" title="Debian/Ubuntu HAProxy packages" target="_blank">Debian/Ubuntu HAProxy packages</a></li>
</ul>

<h2>Requirements</h2>

<h3>General</h3>

<ul>
<li>Allowed editors: <code>vi</code>, <code>vim</code>, <code>emacs</code></li>
<li>All your files will be interpreted on Ubuntu 16.04 LTS</li>
<li>All your files should end with a new line</li>
<li>A <code>README.md</code> file, at the root of the folder of the project, is mandatory</li>
<li>All your Bash script files must be executable</li>
<li>Your Bash script must pass <code>Shellcheck</code> (version <code>0.3.7</code>) without any error</li>
<li>The first line of all your Bash scripts should be exactly <code>#!/usr/bin/env bash</code></li>
<li>The second line of all your Bash scripts should be a comment explaining what is the script doing</li>
</ul>

</div>


      

      

          <h2 class="gap">
    Your servers
  </h2>

  <div class="panel panel-default overflow_visible">
    <div class="panel-body">
      <table class="table table-striped">
  <thead>
    <tr>
      <th>Name</th>
      <th>Username</th>
      <th>IP</th>
      <th>State</th>
      <th></th>
    </tr>
  </thead>

  <tbody>
      <tr>
        <td>3396-web-01</td>
        <td><code>ubuntu</code></td>
        <td><code>104.196.35.48</code></td>
        <td>running</td>
        <td>
          <div class="btn-group">
            <button type="button" class="btn btn-sm btn-default dropdown-toggle" data-toggle="dropdown">
              Actions
              <span class="caret"></span>
              <span class="sr-only">Toggle Dropdown</span>
            </button>
            <ul class="dropdown-menu dropdown-menu-right">
                <li><a data-confirm="Are you sure to reboot 3396-web-01?" href="/servers/6789/soft_reboot">Soft reboot</a></li>
                  <li><a data-confirm="Are you sure to hard reboot 3396-web-01?" href="/servers/6789/hard_reboot">Hard reboot</a></li>

              <li role="separator" class="divider"></li>

                <li>
                  <a data-confirm="Are you sure you&#39;d like a new server?
- This server will be destroyed
- Did you update your public SSH key in your user profile yet?

This action can take time...
Please, be patient..." href="/servers/6789/ask_new">
                    Ask a new server
</a>                </li>
            </ul>
          </div>
        </td>
      </tr>
      <tr>
        <td>3396-web-02</td>
        <td><code>ubuntu</code></td>
        <td><code>3.80.32.63</code></td>
        <td>running</td>
        <td>
          <div class="btn-group">
            <button type="button" class="btn btn-sm btn-default dropdown-toggle" data-toggle="dropdown">
              Actions
              <span class="caret"></span>
              <span class="sr-only">Toggle Dropdown</span>
            </button>
            <ul class="dropdown-menu dropdown-menu-right">
                <li><a data-confirm="Are you sure to reboot 3396-web-02?" href="/servers/7065/soft_reboot">Soft reboot</a></li>
                  <li><a data-confirm="Are you sure to hard reboot 3396-web-02?" href="/servers/7065/hard_reboot">Hard reboot</a></li>

              <li role="separator" class="divider"></li>

                <li>
                  <a data-confirm="Are you sure you&#39;d like a new server?
- This server will be destroyed
- Did you update your public SSH key in your user profile yet?

This action can take time...
Please, be patient..." href="/servers/7065/ask_new">
                    Ask a new server
</a>                </li>
            </ul>
          </div>
        </td>
      </tr>
      <tr>
        <td>3396-lb-01</td>
        <td><code>ubuntu</code></td>
        <td><code>18.212.251.29</code></td>
        <td>running</td>
        <td>
          <div class="btn-group">
            <button type="button" class="btn btn-sm btn-default dropdown-toggle" data-toggle="dropdown">
              Actions
              <span class="caret"></span>
              <span class="sr-only">Toggle Dropdown</span>
            </button>
            <ul class="dropdown-menu dropdown-menu-right">
                <li><a data-confirm="Are you sure to reboot 3396-lb-01?" href="/servers/7066/soft_reboot">Soft reboot</a></li>
                  <li><a data-confirm="Are you sure to hard reboot 3396-lb-01?" href="/servers/7066/hard_reboot">Hard reboot</a></li>

              <li role="separator" class="divider"></li>

                <li>
                  <a data-confirm="Are you sure you&#39;d like a new server?
- This server will be destroyed
- Did you update your public SSH key in your user profile yet?

This action can take time...
Please, be patient..." href="/servers/7066/ask_new">
                    Ask a new server
</a>                </li>
            </ul>
          </div>
        </td>
      </tr>
    
  </tbody>
</table>

    </div>
  </div>