---
hide:
  - navigation
---
# Getting Started

If you are new to climate science or <a href="../models/">ACCESS models</a>, and you want to:

- Run your own experiment
- Get model outputs
- Evaluate model performance
- Perform other tasks involving ACCESS Models

You will need to follow these steps to get started with any of the tasks above.
<hr>

## Create an NCI user account
Most of the data and models you will need are available at the <a href="https://nci.org.au/about-us/who-we-are" target="_blank">National Computing Infrastructure (NCI) </a>.
To be able to access them, you need an NCI account.
<br>
<a href="https://my.nci.org.au/mancini/signup/0" target="_blank">Sign up here</a> if you don't have one yet.
<div class="note">
  You will need an institutional email address with an organisation that allows access to NCI (e.g. an Australian university, ACCESS-NRI, CSIRO, CLEX, etc.).
  <br>
  If you don't think you possess an email address with such institution, please <a href="https://www.access-nri.org.au/contact/" target="_blank">get in contact</a>. 
</div>
<br>
Once you sign up, you will be assigned a <i>username</i> (e.g. `ab1234`).
<hr>

## Join relevant NCI projects

NCI is hosting a large amount of data for the climate community on its supercomputer <i>Gadi</i>. The access to this storage as well as to computing resources to run models and evaluate them is organised in *projects*.

To be able to perform computations yourself, you need to join a project with computing resources. This project code will be provided by your supervisor, research project or institution.

To join a project, search for it on <a href="https://my.nci.org.au/mancini/project-search" target="_blank">NCI website</a> and request membership.

Every project has an ID (e.g. `xp65`). This ID is what the term <i>project</i> actually refers to.
<br>
The first project that you join will become your default one.
<br>
If you want to change your default project, please check <a href="#change-default-project-on-gadi">how to change your default project on Gadi</a>.

There are several NCI projects that may be relevant to you, depending on the tasks you want to carry out.
<br>
Even though we recommend you have a chat with your supervisor to identify the relevant projects for your needs, the table below has a list of some useful climate-related projects at NCI:

| Project | Description | Type | 
|:------- |:----------- |:----- |
| xp65 | <a href="https://my.nci.org.au/mancini/project/xp65" target="_blank">ACCESS-NRI code environments</a> | ACCESS-NRI code environment |
| hh5  | <a href="https://my.nci.org.au/mancini/project/hh5"  target="_blank">Climate-LIEF code environment </a> | Code environment |
| access | <a href="https://my.nci.org.au/mancini/project/access" target="_blank">ACCESS software sharing</a> | ACCESS code environment |
| ik11 | <a href="https://my.nci.org.au/mancini/project/ik11" target="_blank">COSIMA shared working space</a> | Data storage |

<hr>

## Log in to Gadi
Operations such as model runs and output data I/O take place on the <a href="https://nci.org.au/our-systems/hpc-systems" target="_blank">Gadi supercomputer</a>.

To log in to <i>Gadi</i> you need a few pre-requisites:
<ul>
  <li><b>Internet connection</b></li>
  <li>
    <b>UNIX-like terminal</b>
    <br>
    Operative Systems such as Linux or MacOS already have a built-in UNIX-like terminal.
    <br>
    Windows users can install <a href="https://learn.microsoft.com/en-us/windows/wsl" target="_blank">Windows Subsystems for Linux (WSL)</a>, or log in through <a href="https://are.nci.org.au/pun/sys/shell/ssh/gadi.nci.org.au" target="_blank">ARE's Gadi Terminal</a>.
    <div class="note">
      If you choose to log in through <i>ARE's Gadi Terminal</i>, you don't need to follow the next steps as you would already be connected to <i>Gadi</i>.
      <br>
      However, we do suggest you to follow through, as setting up a connection to <i>Gadi</i> from your local machine (without the need for ARE) is the suggested workflow.
    </div>
  </li>
</ul>

To log in to <i>Gadi</i> we use <a href="https://en.wikipedia.org/wiki/Secure_Shell" target="_blank">SSH</a>.
The basic command is:
<pre><code>ssh &lt;your-NCI-username&gt;@gadi.nci.org.au</code></pre>
You will be asked for your NCI password and then you will get connected to <i>Gadi</i>:
<terminal-window lineDelay=0>
  <terminal-line data="input" lineDelay=300>ssh &lt;your-NCI-username&gt;@gadi.nci.org.au</terminal-line>
  <terminal-line lineDelay=300>&lt;NCI-username&gt;@gadi.nci.org.au's password: <i class="icon-key" style="display: inline-block; font-size: 0.4em; transform: rotate(-90deg);"></i></terminal-line>
  <terminal-line lineDelay=3000>###############################################################################</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Welcome to the NCI National Facility!&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;#</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;This service is for authorised clients only. It is a criminal&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;#</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;offence to:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Obtain access to data without permission;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&emsp;#</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Damage, delete, alter or insert data without permission;&emsp;&nbsp;#</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;Use of this system requires acceptance of the Conditions of Use;&emsp;&emsp;&emsp;&emsp;#</terminal-line>
  <terminal-line>#&emsp;&emsp;&emsp;&emsp;published at http://nci.org.au/users/nci-terms-and-conditions-access;&emsp;#</terminal-line>
  <terminal-line>###############################################################################</terminal-line>
  <terminal-line>|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;gadi.nci.org.au - 260,760 processor InfiniBand x86_64 cluster&emsp;&emsp;&nbsp;&nbsp;&nbsp;|</terminal-line>
  <terminal-line>===============================================================================</terminal-line>
  <terminal-line>===============================================================================</terminal-line>
  <terminal-line data="input" lineDelay=200></terminal-line>
</terminal-window>

### Automate the log in step
To simplify the log in step and avoid having to always insert your NCI password, there are a few steps we suggest you to follow:

<ol>
  <li>
    <b>Create an SSH key</b>
    <br>
    To create an SSH key, in your machine's local terminal, run:
    <pre><code>ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_gadi</code></pre>
    You will be asked to create a passphrase linked to the SSH key, and insert it twice:
    <terminal-window>
      <terminal-line data="input">ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_gadi</terminal-line>
      <terminal-line>Generating public/private rsa key pair.</terminal-line>
      <terminal-line>Enter passphrase (empty for no passphrase):</terminal-line>
      <terminal-line lineDelay=3000>Enter same passphrase again:</terminal-line>
      <terminal-line lineDelay=3000>Your identification has been saved in &lt;$HOME&gt;/.ssh/id_gadi</terminal-line>
      <terminal-line>Your public key has been saved in /Users/davide/.ssh/id_gadi.pub</terminal-line>
      <terminal-line lineDelay=0>The key fingerprint is:</terminal-line>
      <terminal-line lineDelay=0>SHA256:&lt;fingerprint-code&gt; &lt;$USER@hostname&gt;</terminal-line>
      <terminal-line lineDelay=0>The key's randomart image is:</terminal-line>
      <terminal-line lineDelay=0>+---[RSA 4096]----+</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>|xxxxxxxxxxxxxxxxx|</terminal-line>
      <terminal-line lineDelay=0>+----[SHA256]-----+</terminal-line>
    </terminal-window>
    <div class="note">
      We suggest you don't leave the passphrase empty for security reason.
      <br>
      As you will see in the next step, you will not need to insert the passphrase every time you log in to <i>Gadi</i>.
    </div>
  </li>
  <li>
    <b>Add the SSH key to the ssh-agent</b>
    <br>
    An ssh-agent is an SSH key manager that avoids you having to type a passphrase every time you connect to a server.
    <br>
    To add the SSH key to the ssh-agent:
    <!-- Tab labels -->
    <div class="tabLabels" label="systems">
      <button>MacOS</button>
      <button>Linux / Windows</button>
    </div>
    <!-- Tab content -->
    <div class="tabContents" label="systems">
      <!-- MacOS -->
      <div>
        <ol>
          <li>
            In your machine's local terminal, start the ssh-agent by running:
            <pre><code>eval "$(ssh-agent -s)"</code></pre>
            <terminal-window>
              <terminal-line data="input">eval "$(ssh-agent -s)"</terminal-line>
              <terminal-line>Agent pid &lt;agent-PID&gt;</terminal-line>
            </terminal-window>
          </li>
          <li>
            Add your SSH key to the ssh-agent by running:
            <pre><code>ssh-add --apple-use-keychain ~/.ssh/id_gadi</code></pre>
            You will be asked for the SSH key passphrase, which will be stored inside the ssh-agent:
            <terminal-window>
              <terminal-line data="input">ssh-add --apple-use-keychain ~/.ssh/id_gadi</terminal-line>
              <terminal-line>Enter passphrase for &lt;$HOME&gt;/.ssh/id_gadi:</terminal-line>
              <terminal-line lineDelay=3000>Identity added: &lt;$HOME&gt;/.ssh/id_gadi &lt;$USER@hostname&gt;</terminal-line>
            </terminal-window>
            <div class="note">
              If you are running a MacOS version prior to Monterey (12.0), the <code>--apple-use-keychain</code> flag needs to be substituted with <code>-K</code>.
            </div>
          </li>
        </ol>
      </div>
      <!-- Linux/Windows -->
      <div>
        <ol>
          <li>
            In your machine's local terminal, start the ssh-agent by running:
            <pre><code>eval "$(ssh-agent -s)"</code></pre>
            <terminal-window>
              <terminal-line data="input">eval "$(ssh-agent -s)"</terminal-line>
              <terminal-line>Agent pid &lt;agent-PID&gt;</terminal-line>
            </terminal-window>
          </li>
          <li>
            Add your SSH key to the ssh-agent by running:
            <pre><code>ssh-add ~/.ssh/id_gadi</code></pre>
            You will be asked for the SSH key passphrase, which will be stored inside the ssh-agent:
            <terminal-window>
              <terminal-line data="input">ssh-add ~/.ssh/id_gadi</terminal-line>
              <terminal-line>Enter passphrase for &lt;$HOME&gt;/.ssh/id_gadi:</terminal-line>
              <terminal-line lineDelay=3000>Identity added: &lt;$HOME&gt;/.ssh/id_gadi &lt;$USER@hostname&gt;</terminal-line>
            </terminal-window>
          </li>
        </ol>
      </div>
    </div>
    <!-- End of tab content -->
  </li>
  <li>
    <b>Create/Update the SSH config file</b>
    <br>
    The <code>~/.ssh/config</code> file is a file where you can store labelled SSH configurations for different servers so you don’t have to remember them.
    <br>
    To create your ssh config file, in your machine's local terminal, run:
    <pre><code>touch ~/.ssh/config</code></pre>
    <div class="note">
      If you already have an existing <code>~/.ssh/config</code> file, the command above will not have any effect.
    </div>
    To store the SSH configurations for <i>Gadi</i> in the SSH config file, you can add the following lines to your <code>~/.ssh/config</code> file:
    <pre><code>Host gadi
      &emsp;Hostname gadi.nci.org.au
      &emsp;User &lt;your-NCI-username&gt;
      &emsp;ForwardX11 true
      &emsp;ForwardX11Trusted yes
      &emsp;IdentityFile ~/.ssh/id_gadi
      &emsp;AddKeysToAgent yes
      &emsp;UseKeychain yes
    </code></pre>
  </li>
  <li>
    <b>Add the SSH key to the Authorized Keys</b>
    <br>
    To enable automatic connection to a server, that server needs to recognise the SSH key as an <i>authorized</i> one. The list of authorised keys for a certain server, is stored inside the file <code>~/.ssh/authorized_keys</code>.
    <br>
    To add the newly created SSH key as an <i>authorized</i> key for Gadi, in your local machine's terminal, run:
    <pre><code>var=$( cat ~/.ssh/id_gadi.pub ) && ssh gadi "echo $var >> .ssh/authorized_keys"</code></pre>
    <div class="note">
      Make sure you use double quotes (") in the previous command.
    </div>
    You will be asked for your password, and if you did all the previous steps correctly, this will be the last time you will have to insert it.
  </li>
</ol>
Once you complete all the above steps, you will be able to connect to <i>Gadi</i> simply by running:
<pre><code>ssh gadi</code></pre>

### Change default project on Gadi
It is recommended that you check what your default project on <i>Gadi</i> is set to. The default project should be set to the computational project you will most likely use to run simulations/forecasts and store data.
<br>
To check which is your default project, on <i>Gadi</i>, run:
<pre><code>echo $PROJECT</code></pre>
If you want to change your default project, on <i>Gadi</i> you should manually change the `PROJECT` field in the `~/.config/gadi-login.conf` file, exit from <i>Gadi</i>, and log back in.
<br>
Alternatively, on <i>Gadi</i> you can run:
<pre><code>sed "s/\(PROJECT \).*/\1&lt;new-default-project&gt;/" ~/.config/gadi-login.conf</code></pre>
exit from <i>Gadi</i>, and log back in.
<br>
For example, if you want to change your default project to `tm70`, on <i>Gadi</i>, run:
<terminal-window>
  <terminal-line data="input">echo $PROJECT</terminal-line>
  <terminal-line>&lt;old-default-project&gt;</terminal-line>
  <terminal-line data="input">sed "s/\(PROJECT \).*/\1tm70/" ~/.config/gadi-login.conf</terminal-line>
  <terminal-line data="input">exit</terminal-line>
  <terminal-line>logout</terminal-line>
  <terminal-line>Connection to gadi.nci.org.au closed.</terminal-line>
  <terminal-line data="input" PS1="<span style='color: #897a36;'>(User PC)$ </span>">ssh gadi</terminal-line>
  <terminal-line>###############################################################################</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Welcome to the NCI National Facility!&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;#</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;This service is for authorised clients only. It is a criminal&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;#</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;offence to:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Obtain access to data without permission;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&emsp;#</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Damage, delete, alter or insert data without permission;&emsp;&nbsp;#</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;Use of this system requires acceptance of the Conditions of Use;&emsp;&emsp;&emsp;&emsp;#</terminal-line>
  <terminal-line lineDelay=0>#&emsp;&emsp;&emsp;&emsp;published at http://nci.org.au/users/nci-terms-and-conditions-access;&emsp;#</terminal-line>
  <terminal-line lineDelay=0>###############################################################################</terminal-line>
  <terminal-line lineDelay=0>|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;gadi.nci.org.au - 260,760 processor InfiniBand x86_64 cluster&emsp;&emsp;&nbsp;&nbsp;&nbsp;|</terminal-line>
  <terminal-line lineDelay=0>===============================================================================</terminal-line>
  <terminal-line lineDelay=0>===============================================================================</terminal-line>
  <terminal-line data="input">echo $PROJECT</terminal-line>
  <terminal-line>tm70</terminal-line>
</terminal-window>
<hr>

<h6>References</h6>
<ul class="references">
    <li>
        <a href = "https://my.nci.org.au" target="_blank">https://nci.org.au</a>
    </li>
    <li>
        <a href = "https://opus.nci.org.au/display/Help/0.+Welcome+to+Gadi" target="_blank">https://opus.nci.org.au/display/Help/0.+Welcome+to+Gadi</a>
    </li>
    <li>
        <a href = "https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent" target="_blank">https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent</a>
    </li>
    <li>
        <a href = "https://linuxize.com/post/using-the-ssh-config-file/" target="_blank">https://linuxize.com/post/using-the-ssh-config-file</a>
    </li>
</ul>