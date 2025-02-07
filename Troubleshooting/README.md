# Troubleshooting Instructions

<img src="../images/Data Science Thumbnail.png">

<!DOCTYPE html>
<html><body><h1>TROUBLESHOOTING LESSONS (Copy of LP)</h1><br><h2>Table of Contents:</h2><ol>1. Jupyter Missing "Python (dojo-env)" in kernels<br>2. conda activate error - GitBash<br>3. "code" Command Not Working (Mac)<br>4. GitBash Error: Could Not Fork Child Process<br>5. Installing Graphviz (Windows)<br>6. Reinstalling Dojo-Env<br>7. Uninstalling Anaconda (Completely)<br></ol><br><hr></hr><br><h1>1. Jupyter Missing "Python (dojo-env)" in kernels</h1>
<h2>PROBLEM:</h2>
<ul>
	<li><strong>If "Python&nbsp;(dojo-env)" doesn't show up in Jupyter Notebook in&nbsp;EITHER:</strong>
		<ul>
			<li>The "New" menu on the Files tab in Jupyter.<br>
				<p><br></p>
				<figure><img
						src="../images/lp/missing_kernel_new.png"
						style="width: 620px; height: 277px;" width="620" height="277"><br><br></figure>
			</li>
			<li>
				<p>or the Kernel &gt;&nbsp;Change Kernel menu inside a Jupyter Notebook:<br></p>
				<figure><img
						src="../images/lp/missing_kernel_notebook.png"
						style="width: 519px; height: 323px;" width="519" height="323"><span></span></figure>
			</li>
		</ul>
	</li>
</ul>
<h2>Solution</h2>
<ul>
	<li>You missed a command after running the conda env create command during step 2, so let's rerun the command.</li>
</ul>
<ul>
	<li><strong>In your terminal/GitBash, make sure it says (dojo-env) above or next to your terminal prompt.</strong>
		<ul>
			<li>if not, on Mac run:&nbsp;<ul>
					<li>"conda activate dojo-env"</li>
				</ul>
			</li>
			<li>on Windows run:<ul>
					<li>"source activate dojo-env"</li>
				</ul>
			</li>
		</ul>
	</li>
	<li><strong>Then run the command below to install dojo-env as a kernel in jupyter:</strong></li>
</ul>
<pre>python -m ipykernel install --user --name dojo-env --display-name "Python (dojo-env)"</pre><br><hr></hr><br><h1>2. conda activate error - GitBash</h1>
<h2>PROBLEM:</h2>
<ul>
	<li>You see the following error message in GitBash:</li>
</ul>
<pre>CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.
To initialize your shell, run
    $ conda init &lt;shell_name&gt;
Currently supported shells are:
  - bash
  - fish
  - tcsh
  - xonsh
  - zsh
  - powershell
See 'conda init --help' for more information and options.&lt;/shell_name&gt;
</pre>
<h3>Solution 1:</h3>
<ul>
	<li>For your computer,&nbsp; run "source activate dojo-env" instead of conda activate.<ul>
			<li>ANYTIME you see a set of instructions that says to run&nbsp;"conda activate" you should ALWAYS replace
				the word "conda" with "source".&nbsp;</li>
		</ul>
	</li>
</ul>
<pre class="active_pre">source activate dojo-env</pre>
<div>
	<h3>PROBLEM - V2:&nbsp;</h3>
</div>
<div>
	<ul>
		<li>If you are seeing this message EVERY time you open a new GitBash Window.&nbsp;</li>
	</ul>
	<p>Solution 2:&nbsp;</p>
	<ul>
		<li>During step 2, you were told to run the following echo conda activate command but your computer requires you
			to use "source activate" instead of "conda activate"</li>
	</ul>
	<pre>## INCORRECT What you&nbsp;ran previously
echo "conda activate dojo-env" &gt;&gt; ~/.bash_profile</pre>
	<ul>
		<li><strong>Step 1) To fix this, you need to open the hidden file ".bash_profile" in VS Code to fix the
				command</strong>.<ul>
				<li>In GitBash run the following command to open the file in VS Code.</li>
			</ul>
		</li>
	</ul>
	<pre>code ~/.bash_profile</pre>
	<ul>
		<li><strong>If this doesn't work and says file not found,</strong> change the "~./" to your full file path to
			your user folder:<ul>
				<li>In the example below, replace&nbsp;&lt;USERFOLDER&gt; with your actual User account name.<br>
					<ul>
						<li>Note: if you do not know your username, run the "whoami" command in GitBash.&nbsp;The text
							displayed is your &lt;USERFOLDER&gt;</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
	<pre class="active_pre">code /c/Users/&lt;USERFOLDER&gt;/.bash_profile</pre>
	<p><br></p>
	<ul>
		<li><strong>Step 2) in the vs code window that opens, you should see the 3 lines of text
				below.&nbsp;<br></strong></li>
	</ul>
	<pre>conda activate dojo-envalias jnb="jupyter notebook"alias lab="jupyter lab"</pre>
	<ul>
		<li>Replace the word "conda" with "source" and then&nbsp;click on&nbsp;File &gt; Save.</li>
		<ul>
			<li>So your final .bash_profile should now say:&nbsp;</li>
		</ul>
	</ul>
	<pre>source activate dojo-env
alias jnb="jupyter notebook"
alias lab="jupyter lab"</pre>
	<p>&nbsp;(Note: it is okay if there is additional text in this file. Whats important is that you change the conda
		activate command to source activate.)&nbsp;</p>
	<p><br></p>
	<ul>
		<li><strong>Step 3)&nbsp;Open a NEW GitBash window and the message should no longer appear!</strong></li>
	</ul>
</div><br><hr></hr><br><h1>3. "code" Command Not Working (Mac)</h1>
<p><br></p>
<figure><img
		src="../images/lp/code_not_found.png"
		style="width: 383px; height: 79px;" width="383" height="79"></figure>
<p><br></p>
<ul>
	<li>If you are trying to open&nbsp;VS Code using the "code" command in your Terminal and&nbsp;receive an error
		message that says&nbsp;</li>
</ul>
<pre>command not found: code</pre>
<ul>
	<li><strong>Open VS Code manually</strong> (check the&nbsp;Applications folder or use Spotlight Search)</li>
	<li>Open the Command Palette.&nbsp;<ul>
			<li>On the menu bar (top of the screen), select "View" &gt; and then select "Command Palette"</li>
		</ul>
	</li>
</ul>
<figure><img
		src="../images/lp/command_palette.png"
		style="width: 590px; height: 476px;" width="590" height="476"></figure>
<ul>
	<li>A popup window will appear with a "&gt;" prompt.&nbsp;</li>
</ul>
<figure><img
		src="../images/lp/command_palette_popup.png"
		style="width: 465px; height: 252px;" width="465" height="252"></figure>
<p><br></p>
<ul>
	<li>Start typing "install code" and you should see the option appear for "Shell Command: Install 'code' command in
		PATH".&nbsp;<ul>
			<li>Click on this option.</li>
		</ul>
	</li>
</ul>
<figure><img
		src="../images/lp/install_code_command.png"
		style="width: 568px; height: 84px;" width="568" height="84"></figure>
<ul>
	<li>It will then notify you that you will be prompted to give "osascript" administrative privileges.</li>
</ul>
<p><br></p>
<figure><img
		src="../images/lp/code_command_prompt.png"
		style="width: 246px; height: 214px;" width="246" height="214"></figure>
<p><br></p>
<ul>
	<li>&nbsp;Click OK and then on the next pop-up window, enter your normal password for your Mac.<ul>
			<li>You should see a success message like the one below.&nbsp;</li>
		</ul>
	</li>
</ul>
<figure><img
		src="../images/lp/success_code_command.png"
		style="width: 322px; height: 241px;" width="322" height="241"></figure>
<p></p>
<ul>
	<li>You are all set! Try the code command again.</li>
</ul>
<p><br></p>
<ul>
	<li><strong>NOTE: if you get an error message when running the install code command:</strong>
		<ul>
			<li>First UNinstall the code command (which is counter-intuitive).<figure><img
						src="../images/lp/uninstall_code.png"
						style="width: 576px; height: 76px;" width="576" height="76"></figure>
			</li>
			<li>Then rerun the install code command.</li>
		</ul>
	</li>
</ul><br><hr></hr><br><h1>4. GitBash Error: Could Not Fork Child Process</h1>
<h2>The Problem:&nbsp;</h2>
<h2>Opening a GitBash windows displays an error message "Could not fork child process"</h2>
<p><img src="https://i.stack.imgur.com/Tps5X.png" alt="enter image description here"></p>
<p><br></p>
<h2>The Solution</h2>
<p><strong>Solution 1:&nbsp;</strong>(adapted from:&nbsp;<a
		href="https://rotadev.com/git-bash-error-could-not-fork-child-process-there-are-no-available-terminals-1-dev/">https://rotadev.com/git-bash-error-could-not-fork-child-process-there-are-no-available-terminals-1-dev/</a>&nbsp;)
</p>
<ul>
	<li>The problem occurs on Windows with Git Bash when the Git Bash console is closed/killed without using ‘exit’.<ul>
			<li>1. Close all Git Bash windows.</li>
			<li>2. Open Task manager (Keyboard shortcut: Control + Shift + Escape.)</li>
			<li>3. Find the ‘Git for Windows’ process.<ul>
					<li>If you do not see any "Git for Windows" processes, look for:<ul>
							<li>python</li>
							<li>msys2</li>
						</ul>
					</li>
				</ul>
			</li>
			<li>4. Kill any processes that are running that meet the above criterion.</li>
			<li>5. Re-open Git Bash. The problem should be fixed.</li>
			<li>See the Prevention heading below for how to avoid this error in the future</li>
		</ul>
	</li>
</ul>
<p><strong>Solution 2&nbsp;(if #1 did not resolve the issue):</strong></p>
<ul>
	<li>The problem may also occur due to VS Code's integrated terminal.</li>
	<li>Close any Visual&nbsp;Studio Code windows&nbsp;</li>
	<li>Check Task Manager for any Visual&nbsp;Studio&nbsp;Code processes that are still running and kill them.</li>
	<li>Re-open Git Bash.&nbsp;The problem should be fixed.</li>
	<li>See the Prevention heading below for how to avoid this error in the future</li>
</ul>
<p><strong>Solution 3&nbsp;(will always work but not convenient)</strong></p>
<ul>
	<li>If neither solution worked, restart your computer.</li>
	<li>While not convenient, it will solve the issue. See the Prevention heading below for how to avoid this error in
		the future.</li>
</ul>
<p><br></p>
<h2>Prevention</h2>
<ul>
	<li>Always make sure to shut down jupyter notebook properly before closing.&nbsp;<ul>
			<li>From jupyter's file view:<ul>
					<li>Click&nbsp;Shutdown on the top right corner</li>
				</ul>
			</li>
			<li>From GitBash:<ul>
					<li>Press "Control + C" to quit jupyter server from the GitBash window that started jupyter
						notebook.<ul>
							<li>If asked y/n, answer "y".</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p><br></p>
<p></p>
<p><br></p><br><hr></hr><br><h1>5. Installing Graphviz (Windows)</h1>
<p></p>
<p>Graphivz is an optional package that will allow you to generate a more advanced version of scikit-learn decision tree
	plots.</p>
<ul>
	<li><strong>Please follow these instructions from Graphivz's Website:&nbsp;</strong><a
			href="https://forum.graphviz.org/t/new-simplified-installation-procedure-on-windows/224">https://forum.graphviz.org/t/new-simplified-installation-procedure-on-windows/224</a>&nbsp;
	</li>
	<li>You will be downloading the installer from&nbsp;<a
			href="https://graphviz.org/download/">https://graphviz.org/download/</a><span></span></li>
	<li><strong>Make sure to follow step "10 Select Add Graphviz to the system PATH for current user in this
			dialog:"</strong></li>
</ul>
<p><br></p>
<p><br></p>
<p><br></p><br><hr></hr><br><h1>6. Reinstalling Dojo-Env</h1>
<div><br></div>
<h2>What to do if your environment breaks and you need to re-install it.</h2>
<ul>
	<li>It is not uncommon to accidentally break our virtual environment by installing a new package or updating a
		pre-existing one.</li>
	<li>In the event that your environment stops working and it needs to be re-installed:<ol>
			<li>open your terminal/gitbash and deactivate your&nbsp;<code>dojo-env</code>:<ul>
					<li>Type&nbsp;<code>conda activate base</code>&nbsp;or&nbsp;<code>conda deactivate</code>&nbsp;and
						press enter.</li>
					<li>Your terminal should now say&nbsp;<code>(base)</code>&nbsp;with your prompt instead
						of&nbsp;<code>(dojo-env)</code>.</li>
				</ul>
			</li>
			<li>Remove the broken&nbsp;<code>dojo-env</code>&nbsp;using the command:<ul>
					<li><code>conda remove --name dojo-env --all</code></li>
					<li>enter&nbsp;<code>y</code>&nbsp;to approve the removal of the environment and hit enter.</li>
				</ul>
			</li>
			<li>Wait for the env to be removed.<ul>
					<li>This will delete all of the files associated with JUST our&nbsp;<code>dojo-env</code>. So
						anconda will still be installed, we will just need to re-install our&nbsp;<code>dojo-env</code>.
					</li>
				</ul>
			</li>
			<li>Once its completed, repeat the environment installation commands from step "2.3 Create the dojo-env
				environment"<ol>
					<li>Don't forget to run the python -m ipykernel command after creating the dojo-env in step 2.3!
					</li>
				</ol>
			</li>
		</ol>
	</li>
</ul><br><hr></hr><br><h1>7. Uninstalling Anaconda (Completely)</h1>
<p>When facing stubborn environment problems, sometimes the best course of action is to completely uninstall the
	environment AND Anaconda and to start over.&nbsp;</p>
<p><strong>Pre-Uninstallation Verification Step:</strong></p>
<ul>
	<li><strong>If you share your computer with another User who also uses Python:</strong>
		<ul>
			<li>Pause here and check with them BEFORE you uninstall anaconda.&nbsp;&nbsp;<strong>You will be removing
					all of their python environments too,</strong> even though they have a separate User account.</li>
		</ul>
	</li>
</ul>
<ul>
	<li><strong>If you share your computer with someone and they have concerns about uninstalling
			anaconda:&nbsp;</strong>
		<ul>
			<li><strong>Stop here (for now)</strong>.<ul>
					<li>Do not move forward with the instructions until you have spoken with your
						instructor.&nbsp;&nbsp;</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p>
	<font color="#505050" face="Gotham-Rounded-Medium"><br></font>
</p>
<h4>Official&nbsp;Steps for Fully Uninstalling Anaconda:</h4>
<p>The following steps are taken directly from the <a href="https://docs.anaconda.com/anaconda/install/uninstall/"
		target="_blank">Official&nbsp;Uninstalling Anaconda documentation page</a>, specifically "Option B. Full
	uninstall using Anaconda-Clean and simple remove."</p>
<ul>
	<li><strong>Install the Anaconda-Clean package from Anaconda Prompt (terminal on Linux or macOS):</strong></li>
</ul>
<pre data-language="ruby" class="rainbow active_pre">conda install anaconda-clean</pre>
<ul>
	<li>In the same window, run the following command:</li>
</ul>
<pre data-language="ruby" class="rainbow">anaconda-clean --yes</pre>
<ul>
	<li>Once the process has been completed, manually delete any "anaconda3" or "anaconda2" folders that still
		exist.&nbsp;<ul>
			<li>It may be located in one of several&nbsp;possible folders. Run the following "ls -a" commands until you
				see a folder called "anconda2" or "anaconda3".&nbsp;</li>
			<li><strong>Once you see an anaconda folder, take note of:</strong>
				<ul>
					<li><strong>&nbsp;Which command showed the folder.</strong>
						<ul>
							<li><strong>&nbsp;Specifically, what did the command say after "ls -a"&nbsp;</strong></li>
							<li>We will refer to this as your "base folder" in the final step.</li>
						</ul>
					</li>
					<li><strong>If the anaconda folder was "anconda2" or "anaconda3"</strong>
						<ul>
							<li>We will refer to this as your "anaconda folder" in the final step.</li>
						</ul>
					</li>
				</ul>
			</li>
			<li><strong>and j</strong>ump to the very last command at the bottom of the page, with those 2 pieces of
				information.</li>
		</ul>
	</li>
</ul>
<pre data-language="ruby" class="rainbow">ls -a ~/
			ls -a ~/opt/
			ls -a /opt/</pre>
<ul>
	<li>Run the final command to remove the anaconda folder once you've identified your "base folder" and "anaconda
		folder".<ul>
			<li>Replace {base_folder} with the actual folder name</li>
		</ul>
		<ul>
			<li>Replace {anaconda_folder} with the actual folder name.</li>
		</ul>
	</li>
</ul>
<pre data-language="ruby" class="rainbow">rm -rf {base_folder}{anaconda_folder}
			</pre>
<p><br></p>
<p>Once you've replaced the placeholder folder names with your actual folder names, the command should look something
	like this:</p>
<pre data-language="ruby" class="rainbow">rm -rf ~/opt/anaconda3
			# or 
			rm -rf ~/anaconda2
			# or 
			rm -rf ~/opt/anaconda3</pre>
<h4></h4>
<h4>Final Verification&nbsp;Step:</h4>
<ul>
	<li>Now, open a <strong>new</strong> terminal window and try running the "conda" command again. Your terminal should
		say that conda is not found.<ul>
			<li>If it says conda is not found, you are now ready to jump back up to the "Step 3 Commands" header above.
			</li>
		</ul>
		<ul>
			<li>If your computer still displays a list of conda commands, see the final portion of the <a
					href="https://docs.anaconda.com/anaconda/install/uninstall/#removing-anaconda-path-from-bash-profile"
					target="_blank">Official Uninstallation Instructions "Removing Anaconda from
					.bash_profile"</a>&nbsp; <strong>You may want to contact your instructor if you do not understand
					the final instructions in the official instructions.</strong></li>
		</ul>
	</li>
</ul>
<p> <br></p><br></body></html>